---
title: IVMSupportDriver Manufacturer property
description: The Manufacturer property contains the name of the drivers manufacturer.
ms.assetid: 7cf1ff56-8006-454b-898f-c1dedf01ad08
keywords:
- Manufacturer property Virtual Server
- Manufacturer property Virtual Server , IVMSupportDriver interface
- IVMSupportDriver interface Virtual Server , Manufacturer property
- Manufacturer property Virtual Server , VMSupportDriver interface
- VMSupportDriver interface Virtual Server , Manufacturer property
topic_type:
- apiref
api_name:
- IVMSupportDriver.Manufacturer
- IVMSupportDriver.get_Manufacturer
- VMSupportDriver.Manufacturer
api_location:
- VsComInterfaces.h
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IVMSupportDriver::Manufacturer property

The **Manufacturer** property contains the name of the driver's manufacturer.

This property is read-only.

## Syntax


```C++
HRESULT get_Manufacturer(
  [out] BSTR *manufacturer
);
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>VMSupportDriver.Manufacturer( _
  ByRef manufacturer _
)</code></pre></td>
</tr>
</tbody>
</table>



## Property value

The driver's manufacturer.

This property value is read-only.

## Error codes



| Name                                                                                          | Meaning                                                   |
|-----------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| <dl> <dt>S\_OK</dt> </dl>              | The property value was retrieved successfully.<br/> |
| <dl> <dt>E\_POINTER</dt> </dl>         | The *manufacturer* parameter is **NULL**.<br/>      |
| <dl> <dt>DISP\_E\_EXCEPTION</dt> </dl> | An unknown error has occurred.<br/>                 |



## Requirements



|                     |                                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------|
| Product<br/>  | Microsoft Virtual Server 2005 onWindows Server 2003<br/>                                    |
| Download<br/> | Microsoft Virtual Server 2005 R2 SP1 Update onWindows Server 2008orWindows Server 2003<br/> |
| Header<br/>   | <dl> <dt>VsComInterfaces.h</dt> </dl>      |



## See also

<dl> <dt>

[**IVMSupportDriver**](ivmsupportdriver.md)
</dt> </dl>

 

 




