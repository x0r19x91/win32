---
Description: Specifies the maximum QP supported by the encoder.
ms.assetid: 2C02F82B-E645-4C5B-9526-5E130A6E2F67
title: CODECAPI\_AVEncVideoMaxQP property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CODECAPI\_AVEncVideoMaxQP property

Specifies the maximum QP supported by the encoder.

## Data type

**ULONG** (VT\_UI4)

## Property GUID

**CODECAPI\_AVEncVideoMaxQP**

## Remarks

**H.264/AVC encoders:**

The encoder shall support[**GetValue**](/windows/win32/mfobjects/nf-mfobjects-imfmediaevent-getvalue?branch=master), [**SetValue**](https://msdn.microsoft.com/library/windows/desktop/dd311966), and [**GetParameterRange**](https://msdn.microsoft.com/library/windows/desktop/dd311956).

This is a static property meaning that it can only be set before the encoding session starts.

Default value shall be the max QP allowed by the corresponding coding standard. For example, H.264 encoders shall have a default value of 51.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8.1 \[desktop apps \| UWP apps\]<br/>                                   |
| Minimum supported server<br/> | Windows Server 2012 R2 \[desktop apps \| UWP apps\]<br/>                        |
| Header<br/>                   | <dl> <dt>Codecapi.h</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Properties](media-foundation-properties.md)
</dt> <dt>

[CODECAPI\_AVEncVideoMinQP](codecapi-avencvideominqp.md)
</dt> </dl>

 

 



