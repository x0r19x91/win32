---
title: Using the ADSI Schema
description: A schema defines the universe of objects stored in a directory.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: 140a5dd0-6f50-4f84-8708-45c0f1c6bdc4
ms.prod: windows-server-dev
ms.technology: active-directory-domain-services
ms.tgt_platform: multiple
keywords:
- Using the ADSI Schema
- ADSI ADSI , using, ADSI schema
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Using the ADSI Schema

A schema defines the universe of objects stored in a directory. In Active Directory, the schema specifies what attributes a directory service object can, or must, have. It also specifies the value range and the syntax of the attributes and whether they support single or multiple values. In short, the schema is organized by class definitions, attribute definitions, and attribute syntax. ADSI provides three interfaces for reading attribute, class, and syntax data from a schema: [**IADsClass**](/windows/win32/Iads/nn-iads-iadsclass?branch=master), [**IADsProperty**](/windows/win32/Iads/nn-iads-iadsproperty?branch=master), and [**IADsSyntax**](/windows/win32/Iads/nn-iads-iadssyntax?branch=master).

Active Directory uses a set of schema objects to provide dynamically extensible schema management. For more information about an unknown object, look up its associated schema objects. To create a new class definition or extend an existing class definition, you can create or extend the appropriate schema objects. Schema objects are organized in the schema container of a given directory. To access an object schema class, use the [**IADs.Schema**](iads-property-methods.md) property of the object to obtain the ADsPath string and use that string to bind to an [**IADsClass**](/windows/win32/Iads/nn-iads-iadsclass?branch=master) interface on the object schema class.

To determine attribute definitions, that is, the range of values, the syntax, and so on, inspect the schema attribute objects for each property supported by the directory service object. For more information about how to access the schema attribute objects, see [**IADsProperty**](/windows/win32/Iads/nn-iads-iadsproperty?branch=master).

ADSI abstracts the syntax data as necessary and enables you to use [**IADsSyntax**](/windows/win32/Iads/nn-iads-iadssyntax?branch=master) to identify the syntax required to represent object data.

For more information about the Active Directory schema, see [Active Directory Schema](https://msdn.microsoft.com/library/ms674984). For code examples to use to read the schema container, see [Reading the Schema](reading-the-schema.md).

 

 



