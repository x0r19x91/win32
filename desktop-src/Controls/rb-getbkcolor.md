---
title: RB\_GETBKCOLOR message
description: Retrieves a rebar controls default background color.
ms.assetid: be90d1ce-a1f8-446d-ae64-001f7174ab05
keywords:
- RB_GETBKCOLOR message Windows Controls
topic_type:
- apiref
api_name:
- RB_GETBKCOLOR
api_location:
- Commctrl.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# RB\_GETBKCOLOR message

Retrieves a rebar control's default background color.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>Must be zero.</dd> <dt>

*lParam* 
</dt> <dd>Must be zero.</dd> </dl>

## Return value

Returns a [**COLORREF**](https://msdn.microsoft.com/library/windows/desktop/dd183449) value that represent the current default background color.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Commctrl.h</dt> </dl> |



## See also

<dl> <dt>

[**RB\_SETBKCOLOR**](rb-setbkcolor.md)
</dt> </dl>

 

 




