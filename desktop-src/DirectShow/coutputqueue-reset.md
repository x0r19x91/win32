---
Description: The Reset method resets the object so that it can receive more data.
ms.assetid: 7074ed71-1650-4b21-a9a2-ad74d0e3e882
title: COutputQueue.Reset method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# COutputQueue.Reset method

The `Reset` method resets the object so that it can receive more data.

## Syntax


```C++
void Reset();
```



## Parameters

This method has no parameters.

## Return value

This method does not return a value.

## Remarks

This method resets the [**COutputQueue::m\_hr**](coutputqueue-m-hr.md) member variable to S\_OK. The object can receive media samples again; for example, after a flush operation.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Outputq.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**COutputQueue Class**](coutputqueue.md)
</dt> </dl>

 

 



