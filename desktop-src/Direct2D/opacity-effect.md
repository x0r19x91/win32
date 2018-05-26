---
title: Opacity effect
description: This effect adjusts the opacity of an image by multiplying the alpha channel of the input by the specified opacity value. It has a single input.
ms.assetid: a4995228-e08f-b543-0af1-e0eedfe8ecb2
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Opacity effect

This effect adjusts the opacity of an image by multiplying the alpha channel of the input by the specified opacity value. It has a single input.

The CLSID for this effect is CLSID\_D2D1Opacity.

## Effect Properties



| Display anme and index enumeration              | Type and default value | Descripiton                                                                                                 |
|-------------------------------------------------|------------------------|-------------------------------------------------------------------------------------------------------------|
| Opacity D2D1\_OPACITY\_PROP\_OPACITY<br/> | FLOAT1.0f<br/>   | The multiplier to the input image's alpha channel. The minimum value is 0.0f and the maximum value is 1.0f. |



 

## Requirements



|                          |                                                   |
|--------------------------|---------------------------------------------------|
| Minimum supported client | Windows 10 \[desktop apps \| Windows Store apps\] |
| Minimum supported server | Windows 10 \[desktop apps \| Windows Store apps\] |
| Header                   | d2d1effects\_2.h                                  |
| Library                  | d2d1.lib, dxguid.lib                              |



 

## Related topics

<dl> <dt>

[**ID2D1Effect**](/windows/win32/D2d1_1/?branch=master)
</dt> </dl>

 

 




