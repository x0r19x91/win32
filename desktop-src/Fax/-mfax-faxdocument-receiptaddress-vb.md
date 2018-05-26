---
Description: The ReceiptAddress property is a null-terminated string that indicates the email address to which the fax service should send a delivery receipt when the fax job reaches a final state.
ms.assetid: ad532f2e-66da-4dc1-856d-6cc65dadf71d
title: FaxDocument.ReceiptAddress property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxDocument.ReceiptAddress property

The **ReceiptAddress** property is a null-terminated string that indicates the email address to which the fax service should send a delivery receipt when the fax job reaches a final state.

This property is read/write.

## Syntax


```VB
Property ReceiptAddress As String
```



## Property value

A **String** that specifies or receives the email address to which the fax service delivers receipts (delivery reports) for fax jobs. The fax service sends a receipt to the sender of the fax when the fax job reaches a final state, that is, when the fax has been successfully sent or when the transmission fails. If this parameter is **Null**, it indicates no delivery receipt is required.

## Remarks

This property has meaning only if the [**ReceiptType**](-mfax-faxdocument-receipttype-vb.md) property for the document is set to 0x0001, indicating that the delivery receipt will be sent by email.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>FaxComex.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Fxscomex.dll</dt> </dl> |



## See also

<dl> <dt>

[Visual Basic Example](-mfax-sending-a-fax.md)
</dt> <dt>

[**FaxDocument**](-mfax-faxdocument.md)
</dt> <dt>

[**IFaxDocument**](/windows/previous-versions/FaxComex/nn-faxcomex-ifaxdocument?branch=master)
</dt> </dl>

 

 



