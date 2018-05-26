---
Description: When using logs, applications often reserve one or more log records in a marshaling area. You reserve records prior to appending them. After you no longer need reserved records, you should free them.
ms.assetid: ac80f492-5e45-4061-a8eb-1fcca155228f
title: Reserving and Freeing Log Records
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Reserving and Freeing Log Records

When using logs, applications often reserve one or more log records in a marshaling area. You reserve records prior to appending them. After you no longer need reserved records, you should free them.

Each record in the log is rounded up to the nearest block size.

Calling [**ReserveAndAppendLog**](/windows/win32/Clfsw32/nf-clfsw32-reserveandappendlog?branch=master) or [**ReserveAndAppendLogAligned**](/windows/win32/Clfsw32/nf-clfsw32-reserveandappendlogaligned?branch=master) reserves space in the marshaling area for a log stream. Your application must store information about the reserved records, typically this is done using an array. The array contains information to tell CLFS what to do when FreeReservedLog is called. This information is represented by either a positive or negative number for each record; CLFS performs different operations depending on whether the number is positive or negative.

When you call [**FreeReservedLog**](/windows/win32/Clfsw32/nf-clfsw32-freereservedlog?branch=master), you must free the same records that you reserved in a previous call to [**ReserveAndAppendLog**](/windows/win32/Clfsw32/nf-clfsw32-reserveandappendlog?branch=master) or [**ReserveAndAppendLogAligned**](/windows/win32/Clfsw32/nf-clfsw32-reserveandappendlogaligned?branch=master).

 

 


