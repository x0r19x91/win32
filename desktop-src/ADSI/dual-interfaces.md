---
title: Dual Interfaces
description: Use COM interfaces to access the properties and methods on any provider ADSI objects.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: 6f3fd725-d660-4cc3-8de2-8ed7800b1141
ms.prod: windows-server-dev
ms.technology: active-directory-domain-services
ms.tgt_platform: multiple
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Dual Interfaces

Use COM interfaces to access the properties and methods on any provider ADSI objects. A read-only property maps to an interface entry of the form **get\_&lt;PropertyName&gt;**. A read/write property maps to two interface entries of the form **get\_&lt;PropertyName&gt;** and **put\_&lt;PropertyName&gt;**.

All methods on a COM interface must:

-   Return an HRESULT value to indicate success or failure. The **HRESULT** type is discussed in the COM specification.
-   On calls to **QueryInterface**, return **E\_NOINTERFACE** for unimplemented interfaces.
-   Return **E\_NOTIMPL** for unimplemented methods on interfaces that are otherwise implemented.
-   Return **E\_ADS\_PROPERTY\_NOT\_SUPPORTED** for interface properties that are not supported.

To retain compatibility with Automation controllers, all parameters and return types should be within the subset defined by the Automation VARIANT data type. For more information, see **VARIANT** and **VARIANTARG** in the Platform Software Development Kit (SDK).

A provider Active Directory object can expose interfaces that use data types other than those in the **VARIANT** subset. However, Automation controllers such as Visual Basic are not able to call those interfaces. Most ADSI provider interfaces are derived from [**IDispatch**](ebbff4bc-36b2-4861-9efa-ffa45e013eb5) and can be used as **IDispatch** interface pointers. However, the [**IDirectoryObject**](/windows/win32/Iads/nn-iads-idirectoryobject?branch=master), [**IDirectorySearch**](/windows/win32/Iads/nn-iads-idirectorysearch?branch=master), and [**IADsExtension**](/windows/win32/Iads/nn-iads-iadsextension?branch=master) ADSI interfaces are not derived from **IDispatch**.

 

 



