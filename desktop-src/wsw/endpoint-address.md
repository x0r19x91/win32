---
title: Endpoint Address
description: An endpoint address represents the address of a service on the network.
ms.assetid: 5df9c0da-6648-42a0-ae87-06844461042a
keywords:
- Endpoint Address Web Services for Windows
- WWSAPI
- WWS
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Endpoint Address

An endpoint address represents the address of a service on the network. When you open a [channel](channel.md), by calling the [**WsOpenChannel**](/windows/win32/WebServices/nf-webservices-wsopenchannel?branch=master) function, you need to provide the endpoint address of the service you which to communicate with, as well as specifying the channel you wish to open.

## 

An endpoint address consists of:

-   a [URL](url.md)
-   a set of headers (optional)
-   a set of extensions (optional)
-   an optional [identity](endpoint-identity.md) representing the security identity of the service.

When a message is addressed, the URL becomes the "To" header of the message. Any headers that are part of the endpoint address are also added to the message.

![](images/endpointaddress.png)

Channels automatically address any messages that are sent, using the [**WS\_ENDPOINT\_ADDRESS**](/windows/win32/WebServices/ns-webservices-_ws_endpoint_address?branch=master) structure that was passed to the [**WsOpenChannel**](/windows/win32/WebServices/nf-webservices-wsopenchannel?branch=master). You can also use the [**WsAddressMessage**](/windows/win32/WebServices/nf-webservices-wsaddressmessage?branch=master) function to override this default behavior.

When [**WS\_ENDPOINT\_ADDRESS**](/windows/win32/WebServices/ns-webservices-_ws_endpoint_address?branch=master) is passed as a parameter, the [**WsOpenChannel**](/windows/win32/WebServices/nf-webservices-wsopenchannel?branch=master) and [**WsOpenServiceProxy**](/windows/win32/WebServices/nf-webservices-wsopenserviceproxy?branch=master) functions create a copy of the **WS\_ENDPOINT\_ADDRESS** parameter in memory and its size is limited by 65536 bytes. [**WsAddressMessage**](/windows/win32/WebServices/nf-webservices-wsaddressmessage?branch=master) does not have this limitation because it does not require creating a copy of the **WS\_ENDPOINT\_ADDRESS** parameter.

The extensions specified in the **extensions** field of [**WS\_ENDPOINT\_ADDRESS**](/windows/win32/WebServices/ns-webservices-_ws_endpoint_address?branch=master) are not used for addressing the message but instead are an extensibility mechanism that can be used to provide additional information (for example, metadata) about the service. Common extensions can be read with the [**WsReadEndpointAddressExtension**](/windows/win32/WebServices/nf-webservices-wsreadendpointaddressextension?branch=master) function.

The optional identity field of the endpoint address can include, for example, the DNS name of the machine on which the service is running, or the UPN of the Windows account under which the service is running. The identity field is not used in addressing the message, but may be used for obtaining a security token for the service (for example, for obtaining a Kerberos ticket to the target UPN) and for verifying the identity of the service replies (for example, a DNS identity used for name checks on the service certificate returned during SSL).

Endpoint addresses can be read and written using [serialization](serialization.md) with the **WS\_ENDPOINT\_ADDRESS\_TYPE** enumeration value from [**WS\_TYPE**](/windows/win32/WebServices/ne-webservices-ws_type?branch=master). Note in order to serialize an endpoint address, you must know the version of the specification used for the addressing headers, as specified in the [**WS\_ADDRESSING\_VERSION**](/windows/win32/WebServices/ne-webservices-ws_addressing_version?branch=master) enumeration.

 

 



