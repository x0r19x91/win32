---
title: Core Interfaces
description: This section contains information about the core interfaces.
ms.assetid: e96804db-0987-49ca-b1b1-321f36c13024
keywords:
- interfaces, Direct3D 11 Core
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Core Interfaces

This section contains information about the core interfaces.

## 

## In this section



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>[<strong>ID3D11Asynchronous</strong>](/windows/win32/D3D11/nn-d3d11-id3d11asynchronous?branch=master)<br/></td>
<td>This interface encapsulates methods for retrieving data from the GPU asynchronously.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11BlendState</strong>](/windows/win32/D3D11/nn-d3d11-id3d11blendstate?branch=master)<br/></td>
<td>The blend-state interface holds a description for blending state that you can bind to the [output-merger stage](d3d10-graphics-programming-guide-output-merger-stage.md).<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11BlendState1</strong>](/windows/win32/D3D11_1/nn-d3d11_1-id3d11blendstate1?branch=master)<br/></td>
<td>The blend-state interface holds a description for blending state that you can bind to the [output-merger stage](d3d10-graphics-programming-guide-output-merger-stage.md). This blend-state interface supports logical operations as well as blending operations.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11CommandList</strong>](/windows/win32/D3D11/nn-d3d11-id3d11commandlist?branch=master)<br/></td>
<td>The [<strong>ID3D11CommandList</strong>](/windows/win32/D3D11/nn-d3d11-id3d11commandlist?branch=master) interface encapsulates a list of graphics commands for play back.<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11Counter</strong>](/windows/win32/D3D11/nn-d3d11-id3d11counter?branch=master)<br/></td>
<td>This interface encapsulates methods for measuring GPU performance.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11DepthStencilState</strong>](/windows/win32/D3D11/nn-d3d11-id3d11depthstencilstate?branch=master)<br/></td>
<td>The depth-stencil-state interface holds a description for depth-stencil state that you can bind to the [output-merger stage](d3d10-graphics-programming-guide-output-merger-stage.md).<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11Device</strong>](/windows/win32/D3D11/nn-d3d11-id3d11device?branch=master)<br/></td>
<td>The device interface represents a virtual adapter; it is used to create resources.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11Device1</strong>](/windows/win32/D3D11_1/nn-d3d11_1-id3d11device1?branch=master)<br/></td>
<td>The device interface represents a virtual adapter; it is used to create resources. [<strong>ID3D11Device1</strong>](/windows/win32/D3D11_1/nn-d3d11_1-id3d11device1?branch=master) adds new methods to those in [<strong>ID3D11Device</strong>](/windows/win32/D3D11/nn-d3d11-id3d11device?branch=master).<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11Device2</strong>](/windows/win32/D3D11_2/nn-d3d11_2-id3d11device2?branch=master)<br/></td>
<td>The device interface represents a virtual adapter; it is used to create resources. [<strong>ID3D11Device2</strong>](/windows/win32/D3D11_2/nn-d3d11_2-id3d11device2?branch=master) adds new methods to those in [<strong>ID3D11Device1</strong>](/windows/win32/D3D11_1/nn-d3d11_1-id3d11device1?branch=master).<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11Device3</strong>](/windows/win32/D3D11_3/nn-d3d11_3-id3d11device3?branch=master)<br/></td>
<td>The device interface represents a virtual adapter; it is used to create resources. [<strong>ID3D11Device3</strong>](/windows/win32/D3D11_3/nn-d3d11_3-id3d11device3?branch=master) adds new methods to those in [<strong>ID3D11Device2</strong>](/windows/win32/D3D11_2/nn-d3d11_2-id3d11device2?branch=master).<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11Device4</strong>](/windows/win32/d3d11_4/nn-d3d11_4-id3d11device4?branch=master)<br/></td>
<td>The device interface represents a virtual adapter; it is used to create resources. [<strong>ID3D11Device4</strong>](/windows/win32/d3d11_4/nn-d3d11_4-id3d11device4?branch=master) adds new methods to those in [<strong>ID3D11Device3</strong>](/windows/win32/D3D11_3/nn-d3d11_3-id3d11device3?branch=master), such as <strong>RegisterDeviceRemovedEvent</strong> and <strong>UnregisterDeviceRemoved</strong>. <br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11Device5</strong>](/windows/win32/d3d11_4/nn-d3d11_4-id3d11device5?branch=master)<br/></td>
<td>The device interface represents a virtual adapter; it is used to create resources. [<strong>ID3D11Device5</strong>](/windows/win32/d3d11_4/nn-d3d11_4-id3d11device5?branch=master) adds new methods to those in [<strong>ID3D11Device4</strong>](/windows/win32/d3d11_4/nn-d3d11_4-id3d11device4?branch=master).<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11DeviceChild</strong>](/windows/win32/D3D11/nn-d3d11-id3d11devicechild?branch=master)<br/></td>
<td>A device-child interface accesses data used by a device.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11DeviceContext</strong>](/windows/win32/D3D11/nn-d3d11-id3d11devicecontext?branch=master)<br/></td>
<td>The [<strong>ID3D11DeviceContext</strong>](/windows/win32/D3D11/nn-d3d11-id3d11devicecontext?branch=master) interface represents a device context which generates rendering commands.<br/>
<blockquote>
[!Note]<br />
The latest version of this interface is [<strong>ID3D11DeviceContext4</strong>](/windows/win32/d3d11_3/nn-d3d11_3-id3d11devicecontext4?branch=master) introduced in the Windows 10 Creators Update. Applications targetting Windows 10 Creators Update should use the <strong>ID3D11DeviceContext4</strong> interface instead of <strong>ID3D11Device</strong>.
</blockquote>
<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11DeviceContext1</strong>](/windows/win32/D3D11_1/nn-d3d11_1-id3d11devicecontext1?branch=master)<br/></td>
<td>The device context interface represents a device context; it is used to render commands. [<strong>ID3D11DeviceContext1</strong>](/windows/win32/D3D11_1/nn-d3d11_1-id3d11devicecontext1?branch=master) adds new methods to those in [<strong>ID3D11DeviceContext</strong>](/windows/win32/D3D11/nn-d3d11-id3d11devicecontext?branch=master).<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11DeviceContext2</strong>](/windows/win32/D3D11_2/nn-d3d11_2-id3d11devicecontext2?branch=master)<br/></td>
<td>The device context interface represents a device context; it is used to render commands. [<strong>ID3D11DeviceContext2</strong>](/windows/win32/D3D11_2/nn-d3d11_2-id3d11devicecontext2?branch=master) adds new methods to those in [<strong>ID3D11DeviceContext1</strong>](/windows/win32/D3D11_1/nn-d3d11_1-id3d11devicecontext1?branch=master).<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11DeviceContext3</strong>](/windows/win32/d3d11_3/nn-d3d11_3-id3d11devicecontext3?branch=master)<br/></td>
<td>The device context interface represents a device context; it is used to render commands. [<strong>ID3D11DeviceContext3</strong>](/windows/win32/d3d11_3/nn-d3d11_3-id3d11devicecontext3?branch=master) adds new methods to those in [<strong>ID3D11DeviceContext2</strong>](/windows/win32/D3D11_2/nn-d3d11_2-id3d11devicecontext2?branch=master). <br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11DeviceContext4</strong>](/windows/win32/d3d11_3/nn-d3d11_3-id3d11devicecontext4?branch=master)<br/></td>
<td>The device context interface represents a device context; it is used to render commands. [<strong>ID3D11DeviceContext4</strong>](/windows/win32/d3d11_3/nn-d3d11_3-id3d11devicecontext4?branch=master) adds new methods to those in [<strong>ID3D11DeviceContext3</strong>](/windows/win32/d3d11_3/nn-d3d11_3-id3d11devicecontext3?branch=master).<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3DDeviceContextState</strong>](/windows/win32/D3D11_1/?branch=master)<br/></td>
<td>The [<strong>ID3DDeviceContextState</strong>](/windows/win32/D3D11_1/?branch=master) interface represents a context state object, which holds state and behavior information about a Microsoft Direct3D device.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11Fence</strong>](/windows/win32/D3D11_3/nn-d3d11_3-id3d11fence?branch=master)<br/></td>
<td>Represents a fence, an object used for synchronization of the CPU and one or more GPUs.<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11InputLayout</strong>](/windows/win32/D3D11/?branch=master)<br/></td>
<td>An input-layout interface holds a definition of how to feed vertex data that is laid out in memory into the [input-assembler stage](d3d10-graphics-programming-guide-input-assembler-stage.md) of the [graphics pipeline](overviews-direct3d-11-graphics-pipeline.md).<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11Multithread</strong>](/windows/win32/d3d11_4/nn-d3d11_4-id3d11multithread?branch=master)<br/></td>
<td>Provides threading protection for critical sections of a multi-threaded application.<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11Predicate</strong>](/windows/win32/D3D11/?branch=master)<br/></td>
<td>A predicate interface determines whether geometry should be processed depending on the results of a previous draw call.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11Query</strong>](/windows/win32/D3D11/nn-d3d11-id3d11query?branch=master)<br/></td>
<td>A query interface queries information from the GPU.<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11Query1</strong>](/windows/win32/D3D11_3/nn-d3d11_3-id3d11query1?branch=master)<br/></td>
<td>Represents a query object for querying information from the graphics processing unit (GPU).<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11RasterizerState</strong>](/windows/win32/D3D11/nn-d3d11-id3d11rasterizerstate?branch=master)<br/></td>
<td>The rasterizer-state interface holds a description for rasterizer state that you can bind to the [rasterizer stage](d3d10-graphics-programming-guide-rasterizer-stage.md).<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11RasterizerState1</strong>](/windows/win32/D3D11_1/nn-d3d11_1-id3d11rasterizerstate1?branch=master)<br/></td>
<td>The rasterizer-state interface holds a description for rasterizer state that you can bind to the [rasterizer stage](d3d10-graphics-programming-guide-rasterizer-stage.md). This rasterizer-state interface supports forced sample count.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ID3D11RasterizerState2</strong>](/windows/win32/D3D11_3/nn-d3d11_3-id3d11rasterizerstate2?branch=master)<br/></td>
<td>The rasterizer-state interface holds a description for rasterizer state that you can bind to the [rasterizer stage](d3d10-graphics-programming-guide-rasterizer-stage.md). This rasterizer-state interface supports forced sample count and conservative rasterization mode.<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ID3D11SamplerState</strong>](/windows/win32/D3D11/nn-d3d11-id3d11samplerstate?branch=master)<br/></td>
<td>The sampler-state interface holds a description for sampler state that you can bind to any shader stage of the [pipeline](overviews-direct3d-11-graphics-pipeline.md) for reference by texture sample operations.<br/></td>
</tr>
</tbody>
</table>



 

Direct3D 11 implements interfaces for:

-   [Resources](d3d11-graphics-reference-resource-interfaces.md)
-   [Shaders](d3d11-graphics-reference-d3d11-shader-interfaces.md)

## Related topics

<dl> <dt>

[Core Reference](d3d11-graphics-reference-d3d11-core.md)
</dt> </dl>

 

 




