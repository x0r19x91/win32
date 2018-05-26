---
title: SBM\_GETPOS message
description: The SBM\_GETPOS message is sent to retrieve the current position of the scroll box of a scroll bar control.
ms.assetid: 00344d93-f205-4cda-aa25-6dd065f41b6e
keywords:
- SBM_GETPOS message Windows Controls
topic_type:
- apiref
api_name:
- SBM_GETPOS
api_location:
- Winuser.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# SBM\_GETPOS message

The **SBM\_GETPOS** message is sent to retrieve the current position of the scroll box of a scroll bar control. The current position is a relative value that depends on the current scrolling range. For example, if the scrolling range is 0 through 100 and the scroll box is in the middle of the bar, the current position is 50.

Applications should not send this message directly. Instead, they should use the [**GetScrollPos**](/windows/win32/Winuser/nf-winuser-getscrollpos?branch=master) function. A window receives this message through its [*WindowProc*](https://msdn.microsoft.com/library/windows/desktop/ms633573) function. Applications which implement a custom scroll bar control must respond to these messages for the **GetScrollPos** function to function properly.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

Not used; must be zero.

</dd> <dt>

*lParam* 
</dt> <dd>

Not used; must be zero.

</dd> </dl>

## Return value

The return value is the current position of the scroll box in the scroll bar.

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                                           |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Winuser.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

**Reference**
</dt> <dt>

[**SBM\_GETRANGE**](sbm-getrange.md)
</dt> <dt>

[**SBM\_SETPOS**](sbm-setpos.md)
</dt> <dt>

[**SBM\_SETRANGE**](sbm-setrange.md)
</dt> <dt>

[**SBM\_SETRANGEREDRAW**](sbm-setrangeredraw.md)
</dt> </dl>

 

 




