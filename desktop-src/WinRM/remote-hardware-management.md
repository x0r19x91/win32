---
title: Remote Hardware Management
description: Remote Hardware Management
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 0ea6d075-6154-4ab9-adcb-e599e5aee614
ms.prod: windows-server-dev
ms.technology: windows-remote-management
ms.tgt_platform: multiple
keywords:
- Remote Hardware Management
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Remote Hardware Management

Windows Remote Management hardware management is intended to reduce overall IT administration costs by providing monitoring and control of remote hardware components, especially before the system is started and after an operating system failure.

Original Equipment Manufacturers (OEMs) have developed a common architecture to address the need for hardware management. An important piece of this architecture is the [*baseboard management controller*](windows-remote-management-glossary.md#winrm-gloss-baseboard-management-controller) (BMC). A BMC is a specialized device that monitors the state of the server computer. The BMC provides remote control of server hardware, retrieves status data, and receives notifications about critical errors and other hardware status changes. A script or application that is monitoring a remote server can obtain data from the server either [*in-band*](windows-remote-management-glossary.md#winrm-gloss-in-band), through the remote operating system, or [*out-of-band*](windows-remote-management-glossary.md#winrm-gloss-out-of-band), directly from the BMC.

A BMC has sensors that can detect, for example, when the server computer is overheating or when voltage is out of the acceptable range. Several standards exist to define the architecture of BMC. The [*Intelligent Platform Management Interface (IPMI)*](windows-remote-management-glossary.md#winrm-gloss-intelligent-platform-management-interface) is one such standard that is used frequently. However, despite the IPMI standard, management access to server hardware is proprietary and requires use of management tools supplied by OEMs. Also, remote access to a BMC is provided using a specialized wire protocol, Remote Management Control Protocol (RMCP), which has nonstandard security mechanisms for authentication of access.

The Microsoft [IPMI provider](https://msdn.microsoft.com/library/aa391402) and IPMI driver, allow you to obtain BMC data from remote server computers through a standard WMI provider with WMI [classes](https://msdn.microsoft.com/library/aa391402). While you can write a normal WMI script that obtains remote data through DCOM, in many cases the preferred method of obtaining IPMI data is through the **Winrm** command-line utility or the [WinRM Scripting API](winrm-scripting-api.md) or [WinRM C++ API](winrm-c---api.md). The Winrm utility and the WinRM service APIs rely on the WS-Management protocol and can obtain IPMI data either from local or remote computer without using DCOM.

The BMC also has an event database called the System Event Log (SEL) which records events in the monitored computer. You cannot subscribe to have these events delivered to a script as you can with WMI event classes. However, you can use the Wecutil.exe command-line tool to subscribe to them. For more information about how to use this tool, at a command prompt type **wecutil /?**.

## Related topics

<dl> <dt>

[WS-Management Protocol](ws-management-protocol.md)
</dt> <dt>

[About Windows Remote Management](about-windows-remote-management.md)
</dt> </dl>

 

 



