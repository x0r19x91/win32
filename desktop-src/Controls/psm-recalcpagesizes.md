---
title: PSM\_RECALCPAGESIZES message
description: Recalculates the page size of a standard or wizard property sheet after pages have been added or removed. You can send this message explicitly or use the PropSheet\_RecalcPageSizes macro.
ms.assetid: 42257ea3-0471-4c67-adcd-01cd2669a51e
keywords:
- PSM_RECALCPAGESIZES message Windows Controls
topic_type:
- apiref
api_name:
- PSM_RECALCPAGESIZES
api_location:
- Prsht.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# PSM\_RECALCPAGESIZES message

Recalculates the page size of a standard or wizard property sheet after pages have been added or removed. You can send this message explicitly or use the [**PropSheet\_RecalcPageSizes**](/windows/win32/Prsht/nf-prsht-propsheet_recalcpagesizes?branch=master) macro.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

Must be zero.

</dd> <dt>

*lParam* 
</dt> <dd>

Must be zero.

</dd> </dl>

## Return value

Returns **TRUE** if successful, or **FALSE** otherwise.

## Remarks

When a property sheet is created, it is sized to fit its initial collection of pages. In order to maintain compatibility with previous versions of the common controls, property sheets and wizards do not automatically resize themselves when pages are subsequently added or removed. With common controls [version 5.80](common-control-versions.md), applications should send a **PSM\_RECALCPAGESIZES** message after adding or removing pages with [**PSM\_ADDPAGE**](psm-addpage.md), [**PSM\_INSERTPAGE**](psm-insertpage.md), [**PSM\_REMOVEPAGE**](psm-removepage.md), or their equivalent macros. It ensures that the property sheet is properly sized for its current collection of pages. If this message is not sent, some property sheet pages may be truncated or too large.

> [!Note]  
> This message is not supported when using the Aero wizard style ([**PSH\_AEROWIZARD**](/windows/win32/Prsht/ns-prsht-_propsheetheadera_v2?branch=master)).

 

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                     |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                               |
| Header<br/>                   | <dl> <dt>Prsht.h</dt> </dl> |



 

 




