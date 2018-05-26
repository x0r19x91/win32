---
title: ITSRemoteProgram2 RemoteApplicationName property
description: The name of the RemoteApp.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: e6bde351-dd4c-4b14-bb11-f155c526aced
ms.prod: windows-server-dev
ms.technology: remote-desktop-services
ms.tgt_platform: multiple
keywords:
- RemoteApplicationName property Remote Desktop Services
- RemoteApplicationName property Remote Desktop Services , ITSRemoteProgram2 interface
- ITSRemoteProgram2 interface Remote Desktop Services , RemoteApplicationName property
- RemoteApplicationName property Remote Desktop Services , ITSRemoteProgram3 interface
- ITSRemoteProgram3 interface Remote Desktop Services , RemoteApplicationName property
topic_type:
- apiref
api_name:
- ITSRemoteProgram2.RemoteApplicationName
- ITSRemoteProgram2.put_RemoteApplicationName
- ITSRemoteProgram3.RemoteApplicationName
- ITSRemoteProgram3.put_RemoteApplicationName
api_location:
- MsTscAx.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# ITSRemoteProgram2::RemoteApplicationName property

The name of the RemoteApp.

This property is write-only.

## Syntax


```C++
HRESULT put_RemoteApplicationName(
  [in] BSTR bstrRemoteApplicationName
);
```



## Property value

The RemoteApp name.

## Requirements



|                                     |                                                                                        |
|-------------------------------------|----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 7<br/>                                                                   |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                         |
| Type library<br/>             | <dl> <dt>MsTscAx.dll</dt> </dl> |
| DLL<br/>                      | <dl> <dt>MsTscAx.dll</dt> </dl> |



## See also

<dl> <dt>

[**ITSRemoteProgram3**](itsremoteprogram3.md)
</dt> <dt>

[**ITSRemoteProgram2**](itsremoteprogram2.md)
</dt> </dl>

 

 




