---
title: Device Names
description: Device Names
ms.assetid: 0ba06439-cc33-43e1-a094-09bcc5e2f6b5
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Device Names

For each device type, there might be several MCI drivers that share the command set but operate on different data formats. To uniquely identify an MCI driver, MCI uses *device names*.

Device names are identified either in the \[mci\] section of the SYSTEM.INI file or in the appropriate part of the registry. This information identifies all MCI drivers to Windows. The entries in the \[mci\] section use the following form:

*device\_name* = *driver\_filename.extension*

The following example shows a typical \[mci\] section from SYSTEM.INI:


```C++
[mci]
cdaudio=mcicda.drv 
sequencer=mciseq.drv 
waveaudio=mciwave.drv 
avivideo=mciavi.drv
```



If an MCI driver is installed using a device name that already exists in SYSTEM.INI or the registry, the system appends an integer to the device name of the new driver, creating a unique device name. In the preceding example, an additional driver installed using the "cdaudio" device name would be assigned the device name "cdaudio1".

 

 



