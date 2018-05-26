---
title: VML BackDepth Attribute
description: VML BackDepth Attribute
ms.assetid: afac0e39-1006-4d73-a4d9-7ed2484019a1
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# VML BackDepth Attribute

This topic describes VML, a feature that is deprecated as of Windows Internet Explorer 9. Webpages and applications that rely on VML should be [migrated to SVG](http://go.microsoft.com/fwlink/p/?LinkID=236964) or other widely supported standards.

> [!Note]  
> As of December 2011, this topic has been archived. As a result, it is no longer actively maintained. For more information, see [Archived Content](https://msdn.microsoft.com/library/hh772377). For information, recommendations, and guidance regarding the current version of Windows Internet Explorer, see [Internet Explorer Developer Center](http://go.microsoft.com/fwlink/p/?linkid=204313).

 

Defines the amount of backward extrusion. Read/write. **VgNumber**.

**Applies To**

[Extrusion](msdn-online-vml-extrusion-element.md)

**Tag Syntax**

&lt;o: *element* backdepth=" *expression* "&gt;

**Script Syntax**

*element* .backdepth="*expression*"

*expression*=*element*.backdepth

**Remarks**

Backward extrusion is the amount of extrusion that appears to be behind the shape. The default units are in points and the default value is 36pt.

*Microsoft Office Extensions Attribute*

 

 



