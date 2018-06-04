---
Description: Enables hardware-accelerated decoding from a Direct3D 9 device, using DirectX Video Acceleration (DXVA) version 1.0.
ms.assetid: abe3beac-f3f8-413d-8b83-9da3340b19ac
title: IDirect3DVideoDevice9 interface
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: interface
ms.date: 05/31/2018
---

# IDirect3DVideoDevice9 interface

Enables hardware-accelerated decoding from a Direct3D 9 device, using DirectX Video Acceleration (DXVA) version 1.0.

## When to use

This interface is not intended for general application use. DirectShow decoder filters should use the [**IAMVideoAccelerator**](https://msdn.microsoft.com/windows/desktop/78e0a165-5a19-4dca-8d6c-445345772824) interface, not **IDirect3DVideoDevice9**. The input pins of the Video Mixing Renderer (VMR) filter and the Overlay Mixer filter expose **IAMVideoAccelerator**.

## Members

The **IDirect3DVideoDevice9** interface inherits from the [**IUnknown**](https://msdn.microsoft.com/windows/desktop/33f1d79a-33fc-4ce5-a372-e08bda378332) interface. **IDirect3DVideoDevice9** also has these types of members:

-   [Methods](#methods)

### Methods

The **IDirect3DVideoDevice9** interface has these methods.



| Method                                                                                   | Description                                                                                                                       |
|:-----------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------|
| [**CreateDXVADevice**](idirect3dvideodevice9-createdxvadevice.md)                       | Creates a DXVA decoder device.<br/>                                                                                         |
| [**CreateSurface**](idirect3dvideodevice9-createsurface.md)                             | Creates a compressed surface for DXVA decoding.<br/>                                                                        |
| [**GetDXVACompressedBufferInfo**](idirect3dvideodevice9-getdxvacompressedbufferinfo.md) | Gets information about the compressed buffers needed for hardware-accelerated decoding.<br/>                                |
| [**GetDXVAGuids**](idirect3dvideodevice9-getdxvaguids.md)                               | Gets a list of the DXVA profiles that are supported by the display driver.<br/>                                             |
| [**GetDXVAInternalInfo**](idirect3dvideodevice9-getdxvainternalinfo.md)                 | Queries for the amount of scratch memory that the hardware abstraction layer (HAL) will allocate for its private use. <br/> |
| [**GetUncompressedDXVAFormats**](idirect3dvideodevice9-getuncompresseddxvaformats.md)   | Gets a list of uncompressed pixel formats that can be rendered using a specified DXVA profile.<br/>                         |



 

## Remarks

To get a pointer to this interface, call **QueryInterface** on an [**IDirect3DDevice9**](https://msdn.microsoft.com/windows/desktop/cf951e8e-7adb-417a-bda0-9b3cde4912a7) or [**IDirect3DDevice9Ex**](https://msdn.microsoft.com/windows/desktop/b2132ee3-5888-4cfe-a7c7-1134c0418a37) pointer.

This interface supports DXVA 1.0 only. It does not support DXVA 2.0.

## Requirements



|                                     |                                                                                   |
|-------------------------------------|-----------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                    |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                              |
| Header<br/>                   | <dl> <dt>Dxva.h</dt> </dl> |



## See also

<dl> <dt>

[Direct3D Video Interfaces](direct3d-video-interfaces.md)
</dt> <dt>

[DirectX Video Acceleration 2.0](directx-video-acceleration-2-0.md)
</dt> <dt>

[DXVA 1.0 specification](http://go.microsoft.com/fwlink/p/?linkid=93647)
</dt> </dl>

 

 



