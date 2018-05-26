---
title: StorPortAllocateMdl routine
description: The StorPortAllocateMdl routine allocates an MDL to describe the given non-paged pool memory.
ms.assetid: 45450486-3264-4fc8-8051-f7c48997e3dd
keywords:
- StorPortAllocateMdl routine Storage Devices
topic_type:
- apiref
api_name:
- StorPortAllocateMdl
api_location:
- storport.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# StorPortAllocateMdl routine

The **StorPortAllocateMdl** routine allocates an MDL to describe the given non-paged pool memory.

## Syntax


```C++
ULONG StorPortAllocateMdl(
  _In_  PVOID HwDeviceExtension,
  _In_  PVOID BufferPointer,
  _In_  ULONG NumberOfBytes,
  _Out_ PVOID *Mdl
);
```



## Parameters

<dl> <dt>

*HwDeviceExtension* \[in\]
</dt> <dd>

A pointer to the hardware device extension for the host bus adapter (HBA).

</dd> <dt>

*BufferPointer* \[in\]
</dt> <dd>

A pointer to the base virtual address of the buffer that the MDL is to describe.

</dd> <dt>

*NumberOfBytes* \[in\]
</dt> <dd>

This parameter specifies the length, in bytes, of the buffer that the MDL is to describe.

</dd> <dt>

*Mdl* \[out\]
</dt> <dd>

A pointer to receive the allocated MDL.

</dd> </dl>

## Return value

StorPortAllocateMdl returns one of the following status codes:



| Return code                                                                                                          | Description                                                                                              |
|----------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <dl> <dt>**STOR\_STATUS\_NOT\_IMPLEMENTED**</dt> </dl>        | This function is not implemented on the active operating system.<br/>                              |
| <dl> <dt>**STOR\_STATUS\_SUCCESS**</dt> </dl>                 | Indicates that the routine allocated the MDL successfully.<br/>                                    |
| <dl> <dt>**STOR\_STATUS\_INVALID\_PARAMETER**</dt> </dl>      | The pointer to receive the MDL is **NULL**.<br/> The pointer to the buffer is **NULL**.<br/> |
| <dl> <dt>**STOR\_STATUS\_INVALID\_IRQL**</dt> </dl>           | The call was made at an invalid IRQL.<br/>                                                         |
| <dl> <dt>**STOR\_STATUS\_INSUFFICIENT\_RESOURCES**</dt> </dl> | Unable to allocate MDL to describe the given buffer.<br/>                                          |



 

## Remarks

A miniport driver calls the **StorPortAllocateMdl** routine to allocate an MDL to describe a block of memory from the non-paged pool. To free the MDL, the miniport driver calls the [**StorPortFreeMdl**](storportfreepool.md) routine.

## Requirements



|                                 |                                                                                                                                         |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Target platform<br/>      | <dl> <dt>[Universal](http://go.microsoft.com/fwlink/p/?linkid=531356)</dt> </dl> |
| Header<br/>               | <dl> <dt>Storport.h (include Storport.h)</dt> </dl>                              |
| IRQL<br/>                 | &lt;=DISPATCH\_LEVEL<br/>                                                                                                         |
| DDI compliance rules<br/> | [**StorPortIrql**](https://msdn.microsoft.com/library/windows/hardware/hh454266)                                                                                       |



 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20StorPortAllocateMdl%20routine%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")




