---
title: DMsgrSessionEvents OnAppNotPresent event
description: Fires when the application requested by the invitation is not present.
ms.assetid: 1f2526ff-7809-4112-85c0-5d3777508734
keywords:
- OnAppNotPresent event Windows Messenger
- OnAppNotPresent event Windows Messenger , DMsgrSessionEvents interface
- DMsgrSessionEvents interface Windows Messenger , OnAppNotPresent event
topic_type:
- apiref
api_name:
- DMsgrSessionEvents.OnAppNotPresent
api_location:
- Msnmsgrexe.adeb440d_7847_4f65_80bd_899870ed2ec9
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# DMsgrSessionEvents::OnAppNotPresent event

\[**OnAppNotPresent** is no longer available for use as of Windows Vista. See [Windows Messenger](im-messenger-entry.md) for more information.\]

Fires when the application requested by the invitation is not present.

## Syntax


```C++
void OnAppNotPresent(
  [in] BSTR bstrAppName,
  [in] BSTR bstrAppURL
);
```



## Parameters

<dl> <dt>

*bstrAppName* \[in\]
</dt> <dd>

**BSTR** that specifies the name of the application.

</dd> <dt>

*bstrAppURL* \[in\]
</dt> <dd>

**BSTR** that specifies the URL of the application.

</dd> </dl>

## Return value

This event does not return a value.

## Requirements



|                                     |                                                                                                                                |
|-------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                                                                    |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                                                           |
| End of client support<br/>    | Windows XP<br/>                                                                                                          |
| End of server support<br/>    | Windows Server 2003<br/>                                                                                                 |
| Product<br/>                  | Messenger 4.5<br/>                                                                                                       |
| Header<br/>                   | <dl> <dt>Msgrpriv.h</dt> </dl>                                          |
| IDL<br/>                      | <dl> <dt>Msgrpriv.idl</dt> </dl>                                        |
| DLL<br/>                      | <dl> <dt>Msnmsgrexe.adeb440d\_7847\_4f65\_80bd\_899870ed2ec9</dt> </dl> |



## See also

<dl> <dt>

[**DMsgrSessionEvents**](im-dmsgrsessionevents.md)
</dt> <dt>

[**OnAccepted**](im-dmsgrsessionevents-onaccepted.md)
</dt> <dt>

[**OnCancelled**](im-dmsgrsessionevents-oncancelled.md)
</dt> <dt>

[**OnContextData**](im-dmsgrsessionevents-oncontextdata.md)
</dt> <dt>

[**OnDeclined**](im-dmsgrsessionevents-ondeclined.md)
</dt> <dt>

[**OnReadyToLaunch**](im-dmsgrsessionevents-onreadytolaunch.md)
</dt> <dt>

[**OnSendError**](im-dmsgrsessionevents-onsenderror.md)
</dt> <dt>

[**OnStateChanged**](im-dmsgrsessionevents-onstatechanged.md)
</dt> <dt>

[**OnTermination**](im-dmsgrsessionevents-ontermination.md)
</dt> <dt>

[Messenger Lock and Key API](im-lock-and-key-ovw.md)
</dt> <dt>

[Messenger Session Invite and Messenger Private APIs](im-session-invite-ovw.md)
</dt> </dl>

 

 




