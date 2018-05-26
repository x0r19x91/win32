---
Description: Windows Sockets 2 introduces overlapped I/O and requires that all transport providers support this capability.
ms.assetid: 90d49171-e211-4426-aa56-88aaeac7c578
title: Overlapped Input/Output
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Overlapped Input/Output

Windows Sockets 2 introduces overlapped I/O and requires that all transport providers support this capability. Overlapped I/O can be performed only on sockets that were created through the [**WSPSocket**](/windows/win32/Ws2spi/nc-ws2spi-lpwspsocket?branch=master) function with the WSA\_FLAG\_OVERLAPPED flag set, and follow the model established in Windows.

For receiving, a client uses [**WSPRecv**](/windows/win32/Ws2spi/?branch=master) or [**WSPRecvFrom**](/windows/win32/Ws2spi/?branch=master) to supply buffers into which data is to be received. If one or more buffers are posted prior to the time when data has been received by the network, it is possible that data will be placed into the user's buffers immediately as it arrives and thereby avoid the copy operation that would otherwise occur. If data is already present when receive buffers are posted, it is copied immediately into the user's buffers. If data arrives when no receive buffers have been posted by the application, the service provider resorts to the synchronous style of operation where the incoming data is buffered internally until such time as the client issues a receive call and thereby supplies a buffer into which the data may be copied. An exception to this would be if the application used [**WSPSetSockOpt**](/windows/win32/Ws2spi/?branch=master) to set the size of the receive buffer to zero. In this instance, reliable protocols would only allow data to be received when application buffers had been posted, and data on unreliable protocols would be lost.

On the sending side, clients use [**WSPSend**](/windows/win32/Ws2spi/?branch=master) or [**WSPSendTo**](/windows/win32/Ws2spi/?branch=master) to supply pointers to filled buffers and then agree not to disturb the buffers in any way until the network has consumed the buffer's contents.

Overlapped send and receive calls return immediately. A return value of zero indicates that the I/O operation completed immediately and that the corresponding completion indication has already occurred. That is, the associated event object has been signaled, or the completion routine has been queued through [**WPUQueueApc**](/windows/win32/Ws2spi/nf-ws2spi-wpuqueueapc?branch=master). A return value of SOCKET\_ERROR coupled with an error code of WSA\_IO\_PENDING indicates that the overlapped operation has been successfully initiated and that a subsequent indication will be provided when send buffers have been consumed or when receive buffers are filled. Any other error code indicates that the overlapped operation was not successfully initiated and that no completion indication will be forthcoming.

Both send and receive operations can be overlapped. The receive functions may be invoked multiple times to post receive buffers in preparation for incoming data, and the send functions may be invoked multiple times to queue up multiple buffers to be sent. Note that while a series of overlapped send buffers will be sent in the order supplied, the corresponding completion indications may occur in a different order. Likewise, on the receiving side, buffers will be filled in the order they are supplied, but completion indications may occur in a different order.

The deferred completion feature of overlapped I/O is also available for [**WSPIoctl**](/windows/win32/Ws2spi/?branch=master).

## Delivering Completion Indications

Service providers have two ways to indicate overlapped completion: setting a client-specified event object, or invoking a client-specified completion routine. In both cases a data structure, [**WSAOVERLAPPED**](/windows/win32/Winsock2/ns-winsock2-_wsaoverlapped?branch=master), is associated with each overlapped operation. This structure is allocated by the client and used by it to indicate which event object (if any) is to be set when completion occurs. The **WSAOVERLAPPED** structure may be used by the service provider as a place to store a handle to the results (for example, number of bytes transferred, updated flags, error codes, etc.) for a particular overlapped operation. To obtain these results clients must invoke [**WSPGetOverlappedResult**](/windows/win32/Ws2spi/nc-ws2spi-lpwspgetoverlappedresult?branch=master), passing in a pointer to the corresponding overlapped structure.

If event based completion indication is selected for a particular overlapped I/O request, the [**WSPGetOverlappedResult**](/windows/win32/Ws2spi/nc-ws2spi-lpwspgetoverlappedresult?branch=master) routine may itself be used by clients to either poll or wait for completion of the overlapped operation. If completion-routine-based completion indication is selected for a particular overlapped I/O request, only the polling option of **WSPGetOverlappedResult** is available. A client may also use other means to wait (such as using [**WSAWaitForMultipleEvents**](/windows/win32/Winsock2/nf-winsock2-wsawaitformultipleevents?branch=master)) until the corresponding event object has been signaled or the specified completion routine has been invoked by the service provider. Once completion has been indicated, the client may invoke **WSPGetOverlappedResult**, with the expectation that the call will complete immediately.

## Invoking Socket I/O Completion Routines

If the *lpCompletionRoutine* parameter to an overlapped operation is not **NULL**, it is the service provider's responsibility to arrange for invocation of the client-specified completion routine when the overlapped operation completes. Since the completion routine must be executed in the context of the same thread that initiated the overlapped operation, it cannot be invoked directly from the service provider. The Ws2\_32.DLL offers an asynchronous procedure call (APC) mechanism to facilitate invocation of completion routines.

A service provider arranges for a function to be executed in the proper thread by calling [**WPUQueueApc**](/windows/win32/Ws2spi/nf-ws2spi-wpuqueueapc?branch=master). This function can be called from any process and thread context, even a context different from the thread and process that was used to initiate the overlapped operation.

[**WPUQueueApc**](/windows/win32/Ws2spi/nf-ws2spi-wpuqueueapc?branch=master) takes as input parameters a pointer to a [**WSATHREADID**](/windows/win32/Ws2spi/ns-ws2spi-_wsathreadid?branch=master) structure, a pointer to an APC function to be invoked, and a 32-bit context value that is subsequently passed to the APC function. Service providers are always supplied with a pointer to the proper **WSATHREADID** structure through the *lpThreadId* parameter to the overlapped function. The provider should store the **WSATHREADID** structure locally and supply a pointer to this copy of the **WSATHREADID** structure as an input parameter to **WPUQueueApc**. Once the **WPUQueueApc** function returns, the provider can dispose of its copy of the **WSATHREADID**.

The procedure [**WPUQueueApc**](/windows/win32/Ws2spi/nf-ws2spi-wpuqueueapc?branch=master) simply enqueues sufficient information to call the indicated APC function with the given parameters, but does not call it. When the target thread enters an alertable wait state, this information is dequeued and a call is made to the APC function in that target thread and process context. Because the APC mechanism supports only a single 32-bit context value, the APC function cannot itself be the client-specified completion routine, which involves more parameters. The service provider must instead supply a pointer to its own APC function which uses the supplied context value to access the needed result information for the overlapped operation, and then invokes the client-specified completion routine.

For service providers where a user-mode component implements overlapped I/O, a typical usage of the APC mechanism is as follows:

-   When the I/O operation completes, the provider allocates a small buffer and packs it with a pointer to the client-supplied completion procedure and parameter values to pass to the procedure.
-   It queues an APC, specifying the pointer to the buffer as the context value and its own intermediate procedure as the target procedure.
-   When the target thread eventually enters alertable wait state, the service provider's intermediate procedure is called in the proper thread context.
-   The intermediate procedure simply unpacks parameters, deallocates the buffer, and calls the client-supplied completion procedure.
-   For service providers where a kernel-mode component implements overlapped I/O, a typical implementation is similar, except that the implementation would use standard kernel interfaces to enqueue the APC.

Description of the relevant kernel interfaces is outside the scope of the Windows Sockets 2 specification.

> [!Note]  
> Service providers must allow Windows Sockets 2 clients to invoke send and receive operations from within the context of the socket I/O completion routine and guarantee that for a given socket, I/O completion routines will not be nested.

 

Under some circumstances, a layered service provider may need to initiate and complete overlapped operations from within an internal worker thread. In this case, a [**WSATHREADID**](/windows/win32/Ws2spi/ns-ws2spi-_wsathreadid?branch=master) would not be available from an incoming function call. The service provider interface provides an upcall, [**WPUOpenCurrentThread**](/windows/win32/Ws2spi/nf-ws2spi-wpuopencurrentthread?branch=master), to obtain a **WSATHREADID** for the current thread. When this **WSATHREADID** is no longer needed, its resources should be returned by calling [**WPUCloseThread**](/windows/win32/Ws2spi/nf-ws2spi-wpuclosethread?branch=master).

 

 


