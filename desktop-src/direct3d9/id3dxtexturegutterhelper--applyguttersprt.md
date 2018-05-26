---
Description: Applies gutters to an ID3DXPRTBuffer buffer object.
ms.assetid: db09aa50-3175-4588-8433-dad6bd37cf0c
title: ID3DXTextureGutterHelperApplyGuttersPRT method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ID3DXTextureGutterHelper::ApplyGuttersPRT method

Applies gutters to an [**ID3DXPRTBuffer**](id3dxprtbuffer.md) buffer object.

## Syntax


```C++
HRESULT ApplyGuttersPRT(
  [in] LPD3DXPRTBUFFER pBuffer
);
```



## Parameters

<dl> <dt>

*pBuffer* \[in\]
</dt> <dd>

Type: **[**LPD3DXPRTBUFFER**](id3dxprtbuffer.md)**

Pointer to an [**ID3DXPRTBuffer**](id3dxprtbuffer.md) buffer object.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the method succeeds, the return value is S\_OK. If the method fails, the following value will be returned.D3DERR\_INVALIDCALL

## Remarks

[**Class 2 texels**](id3dxtexturegutterhelper.md) are generated by resampling class 1 and 4 texels.

The width and height of the texture must be the same as those returned by [**ID3DXTextureGutterHelper::GetWidth**](id3dxtexturegutterhelper--getwidth.md) and [**ID3DXTextureGutterHelper::GetHeight**](id3dxtexturegutterhelper--getheight.md).

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Mesh.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[ID3DXTextureGutterHelper](id3dxtexturegutterhelper.md)
</dt> </dl>

 

 



