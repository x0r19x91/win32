---
Description: Differences between c\_root multipoint sockets and regular point-to-point sockets.
ms.assetid: fbadfde8-44dc-41ac-bd93-1a22c76ca321
title: Semantic Differences Between Multipoint Sockets and Regular Sockets
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Semantic Differences Between Multipoint Sockets and Regular Sockets

In the control plane, there are some significant semantic differences between a c\_root socket and a regular point-to-point socket:

-   The c\_root socket can be used in [**WSAJoinLeaf**](/windows/win32/Winsock2/nf-winsock2-wsajoinleaf?branch=master) to join a new a leaf.
-   Placing a c\_root socket into listening mode (by calling [**listen**](/windows/win32/Winsock2/nf-winsock2-listen?branch=master)) does not preclude the c\_root socket from being used in a call to [**WSAJoinLeaf**](/windows/win32/Winsock2/nf-winsock2-wsajoinleaf?branch=master) to add a new leaf, or for sending and receiving multipoint data.
-   The closing of a c\_root socket causes all of the associated c\_leaf sockets to get FD\_CLOSE notification.

There are no semantic differences between a c\_leaf socket and a regular socket in the control plane, except that the c\_leaf socket can be used in [**WSAJoinLeaf**](/windows/win32/Winsock2/nf-winsock2-wsajoinleaf?branch=master), and the use of c\_leaf socket in [**listen**](/windows/win32/Winsock2/nf-winsock2-listen?branch=master) indicates that only multipoint connection requests should be accepted.

In the data plane, the semantic differences between the d\_root socket and a regular point-to-point socket are:

-   The data sent on the d\_root socket is delivered to all the leaves in the same multipoint session.
-   The data received on the d\_root socket may be from any of the leaves.

The d\_leaf socket in the rooted data plane has no semantic difference from the regular socket, however, in the nonrooted data plane, the data sent on the d\_leaf socket goes to all the other leaf nodes, and the data received could be from any other leaf nodes. As mentioned earlier, the information about whether the d\_leaf socket is in a rooted or nonrooted data plane is contained in the corresponding [**WSAPROTOCOL\_INFO**](/windows/win32/Winsock2/?branch=master) structure for the socket.

 

 


