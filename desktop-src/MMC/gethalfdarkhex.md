---
title: SysColorCtrl.GetHalfDarkHex method
description: The GetHalfDarkHex method derives a \ 0034;darker \ 0034; color by calculating a color that is blended 50 between a given color and black. It is returned as a hexadecimal value.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 553abc10-8d3b-48cc-9e21-7a31b14b2c2f
ms.prod: windows-server-dev
ms.technology: microsoft-management-console
ms.tgt_platform: multiple
keywords:
- GetHalfDarkHex method MMC
- GetHalfDarkHex method MMC , SysColorCtrl class
- SysColorCtrl class MMC , GetHalfDarkHex method
topic_type:
- apiref
api_name:
- SysColorCtrl.GetHalfDarkHex
api_location:
- Cic.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# SysColorCtrl.GetHalfDarkHex method

The **GetHalfDarkHex** method derives a "darker" color by calculating a color that is blended 50% between a given color and black. It is returned as a hexadecimal value.

## Syntax


```VB
SysColorCtrl.GetHalfDarkHex( _
  ByVal pszFrom, _
  ByVal pszFormat _
)
```



## Parameters

<dl> <dt>

*pszFrom* \[in\]
</dt> <dd>

A string that contains the color you want to use as the starting color. The contents of the string depend on the format specified in the *pszFormat* parameter.

</dd> <dt>

*pszFormat* \[in\]
</dt> <dd>

A string that contains the name of the format that is being passed in the *pszFrom* parameter.

<dt>

<span id="CSS"></span><span id="css"></span>

<span id="CSS"></span><span id="css"></span>**CSS**


</dt> <dd>

Name of the display element whose color you want to specify. See [System Color Values for Color Derivation Methods](system-color-values-for-color-derivation-methods.md).

</dd> <dt>

<span id="HEX"></span><span id="hex"></span>

<span id="HEX"></span><span id="hex"></span>**HEX**


</dt> <dd>

Hexadecimal form of the color. For example, specify FFFFFF for white.

</dd> <dt>

<span id="RGB"></span><span id="rgb"></span>

<span id="RGB"></span><span id="rgb"></span>**RGB**


</dt> <dd>

RGB form of the color. For example, specify 16777215 for white.

</dd> </dl> </dd> </dl>

## Return value

A string that contains the hexadecimal value for the derived color specified by the method's parameters.

## Requirements



|                            |                                                                                    |
|----------------------------|------------------------------------------------------------------------------------|
| Redistributable<br/> | MMC 1.1 or later<br/>                                                        |
| DLL<br/>             | <dl> <dt>Cic.dll</dt> </dl> |



 

 




