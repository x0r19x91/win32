---
Description: CIM Schema Compatibility
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 3738914d-dd33-4999-b37f-b4bb94689cd4
ms.prod: windows-server-dev
ms.technology: windows-management-instrumentation
ms.tgt_platform: multiple
title: CIM Schema Compatibility
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# CIM Schema Compatibility

A key component of the Windows Management Instrumentation (WMI) infrastructure is an object-oriented model of the manageable entities in a system. The model conforms to a standard maintained by the Desktop Management Task Force ([DMTF](http://go.microsoft.com/fwlink/p/?linkid=67786)) and is known as the Common Information Model (CIM). The CIM schema provides a single data description mechanism for any data that they provide.

Starting in Windows 7, WMI is compatible with the CIM Schema version 2.17.1 ([http://www.dmtf.org/standards/cim/cim\_schema\_v2171/](http://go.microsoft.com/fwlink/p/?linkid=152369)). Users can now compile a DMTF defined schema on a Windows computer.

## Benefits of CIM Schema version 2.17.1 compatibility

-   When a user downloads CIM Schema version 2.17.1 or DMTF MOF files, they can be successfully compiled on the target Windows computer.
-   The CIM Schema version 2.17.1 added support for BIOS, printers, standard messages, operating system state, modern power management paradigms, virtualization and security.
-   CIM Schema version 2.1.7.1 offers additional profile support. For more information, see [Cross Namespace Association Traversal](cross-namespace-association-traversal.md)

 

 


