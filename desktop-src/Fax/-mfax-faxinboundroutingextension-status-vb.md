---
Description: The Status property is a value that indicates whether the fax routing extension loaded and initialized successfully.
ms.assetid: 73a12417-2b2e-40ad-b683-fc246ec389f6
title: FaxInboundRoutingExtension.Status property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxInboundRoutingExtension.Status property

The **Status** property is a value that indicates whether the fax routing extension loaded and initialized successfully.

This property is read-only.

## Syntax


```VB
Property Status As Integer
```



## Property value

A variable of type [**FAX\_PROVIDER\_STATUS\_ENUM**](/windows/previous-versions/FaxComex/ne-faxcomex-fax_provider_status_enum?branch=master) that receives the status. For possible values, see **FAX\_PROVIDER\_STATUS\_ENUM**.

## Remarks

If the extension did not load successfully, the property indicates the reason for the failure, and [**InitErrorCode**](-mfax-faxinboundroutingextension-initerrorcode-vb.md) holds the last error code value. For more information, see [**FAX\_PROVIDER\_STATUS\_ENUM**](/windows/previous-versions/FaxComex/ne-faxcomex-fax_provider_status_enum?branch=master).

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>FaxComex.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Fxscomex.dll</dt> </dl> |



## See also

<dl> <dt>

[Visual Basic Example](-mfax-managing-routing-extensions-and-routing-methods.md)
</dt> <dt>

[**FaxInboundRoutingExtension**](-mfax-faxinboundroutingextension.md)
</dt> <dt>

[**IFaxInboundRoutingExtension**](/windows/previous-versions/FaxComex/nn-faxcomex-ifaxinboundroutingextension?branch=master)
</dt> </dl>

 

 



