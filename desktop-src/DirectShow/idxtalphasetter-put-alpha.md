---
Description: The put\_Alpha method specifies the alpha value for the entire image.
ms.assetid: ba02a9ae-b722-4771-89c6-e76369d39ed7
title: IDxtAlphaSetterput\_Alpha method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IDxtAlphaSetter::put\_Alpha method

> [!Note]  
> \[Deprecated. This API may be removed from future releases of Windows.\]

 

The `put_Alpha` method specifies the alpha value for the entire image.

## Syntax


```C++
HRESULT put_Alpha(
  [in] long Alpha
);
```



## Parameters

<dl> <dt>

*Alpha* \[in\]
</dt> <dd>

The alpha value. This value will be applied to the entire target image. To disable this property, set a negative value.

</dd> </dl>

## Return value

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Remarks

If you set this property to a non-negative value, you must also disable the alpha ramp property, by calling **put\_AlphaRamp** with a negative value. Otherwise the effect will not render correctly.

> [!Note]  
> The header file Qedit.h is not compatible with Direct3D headers later than version 7.

 

> [!Note]  
> To obtain Qedit.h, download the [Microsoft Windows SDK Update for Windows Vista and .NET Framework 3.0](http://go.microsoft.com/fwlink/p/?linkid=129787). Qedit.h is not available in the Microsoft Windows SDK for Windows 7 and .NET Framework 3.5 Service Pack 1.

 

## Requirements



|                    |                                                                                         |
|--------------------|-----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Qedit.h</dt> </dl>      |
| Library<br/> | <dl> <dt>Strmiids.lib</dt> </dl> |



## See also

<dl> <dt>

[**IDxtAlphaSetter Interface**](idxtalphasetter.md)
</dt> <dt>

[**IDxtAlphaSetter::put\_AlphaRamp**](idxtalphasetter-put-alpharamp.md)
</dt> </dl>

 

 



