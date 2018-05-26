---
Description: Retrieves the reply APDUs message status word.
ms.assetid: c8a4b713-4ae9-49f2-a623-6ee305123638
title: ISCardCmdget\_ReplyStatus method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ISCardCmd::get\_ReplyStatus method

\[The **get\_ReplyStatus** method is available for use in the operating systems specified in the Requirements section. It is not available for use in Windows Server 2003 with Service Pack 1 (SP1) and later, Windows Vista, Windows Server 2008, and subsequent versions of the operating system. The [Smart Card Modules](secsmart.smart_card_modules) provide similar functionality.\]

The **get\_ReplyStatus** method retrieves the [*reply APDU's*](security.r_gly#-security-reply-apdu-gly) message status word.

## Syntax


```C++
HRESULT get_ReplyStatus(
  [out] LPWORD pwStatus
);
```



## Parameters

<dl> <dt>

*pwStatus* \[out\]
</dt> <dd>

Pointer to the word that is the status on return.

</dd> </dl>

## Return value

The method returns one of the following possible values.



| Return code                                                                                   | Description                                        |
|-----------------------------------------------------------------------------------------------|----------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>          | Operation completed successfully.<br/>       |
| <dl> <dt>**E\_INVALIDARG**</dt> </dl>  | The *pwStatus* parameter is not valid.<br/>  |
| <dl> <dt>**E\_POINTER**</dt> </dl>     | A bad pointer was passed in *pwStatus*.<br/> |
| <dl> <dt>**E\_OUTOFMEMORY**</dt> </dl> | Out of memory.<br/>                          |



 

## Remarks

To set the reply APDU's message status word, call [**put\_ReplyStatus**](iscardcmd-put-replystatus.md).

For a list of all the methods provided by this interface, see [**ISCardCmd**](iscardcmd.md).

In addition to the COM error codes listed above, this interface may return a [*smart card*](security.s_gly#-security-smart-card-gly) error code if a smart card function was called to complete the request. For more information, see [Smart Card Return Values](authentication-return-values.md#smart-card-return-values).

## Examples

The following example shows how to retrieve the message status word of the [*reply APDU*](security.r_gly#-security-reply-apdu-gly). The example assumes that pISCardCmd is a valid pointer to an instance of the [**ISCardCmd**](iscardcmd.md) interface.


```C++
WORD    wReplyStatus;
HRESULT hr;

// Get reply status.
hr = pISCardCmd->get_ReplyStatus(&amp;wReplyStatus);
if (FAILED(hr))
{
  printf("Failed get_ReplyStatus\n");
  // Take other error handling action as needed.
}
else
{
  if (wReplyStatus != 0x9000)
  {
    printf("APDU failed - Error [0x%x]\n", wReplyStatus);
    // Take other error handling action as needed.
  }
}
```



## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>                                             |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                    |
| End of client support<br/>    | Windows XP<br/>                                                                   |
| End of server support<br/>    | Windows Server 2003<br/>                                                          |
| Header<br/>                   | <dl> <dt>Scarddat.h</dt> </dl>   |
| Type library<br/>             | <dl> <dt>Scarddat.tlb</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Scardssp.dll</dt> </dl> |
| IID<br/>                      | IID\_ISCardCmd is defined as D5778AE3-43DE-11D0-9171-00AA00C18068<br/>            |



## See also

<dl> <dt>

[**ISCardCmd**](iscardcmd.md)
</dt> <dt>

[**put\_ReplyStatus**](iscardcmd-put-replystatus.md)
</dt> </dl>

 

 



