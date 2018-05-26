---
Description: Specifies the quantization parameter (QP) that was used to encode a video sample.
ms.assetid: F7C4FEFC-FEE7-4614-BC90-4F9D5D878F49
title: MFSampleExtension\_VideoEncodeQP attribute
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MFSampleExtension\_VideoEncodeQP attribute

Specifies the quantization parameter (QP) that was used to encode a video sample.

## Data type

**UINT64**

## Get/set

To get this attribute, call [**IMFAttributes::GetUINT64**](/windows/win32/mfobjects/nf-mfobjects-imfattributes-getuint64?branch=master).

To set this attribute, call [**IMFAttributes::SetUINT64**](/windows/win32/mfobjects/nf-mfobjects-imfattributes-setuint64?branch=master).

## Applies to

[**IMFSample**](/windows/win32/mfobjects/nn-mfobjects-imfsample?branch=master)

## Remarks

The [**H.264 Video Encoder**](h-264-video-encoder.md) sets this attribute on the output samples that it generates.

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8 \[desktop apps \| UWP apps\]<br/>                                  |
| Minimum supported server<br/> | None supported<br/>                                                          |
| Header<br/>                   | <dl> <dt>Mfapi.h</dt> </dl> |



## See also

<dl> <dt>

[Alphabetical List of Media Foundation Attributes](alphabetical-list-of-media-foundation-attributes.md)
</dt> <dt>

[**H.264 Video Encoder**](h-264-video-encoder.md)
</dt> <dt>

[Sample Attributes](sample-attributes.md)
</dt> <dt>

[Media Samples](media-samples.md)
</dt> </dl>

 

 



