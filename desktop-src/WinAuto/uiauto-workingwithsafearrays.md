---
title: Best Practices for Using Safe Arrays
description: Many interface methods of the Microsoft UI Automation \ 32;API take arguments called safe arrays, of the SAFEARRAY data type. This topic describes the best practices for using safe arrays in a UI Automation applications.
ms.assetid: 07e87cfd-d565-41b5-a68d-b99dd191fa95
keywords:
- UI Automation,safe arrays
- UI Automation,providers
- UI Automation,clients
- UI Automation,converting among data types
- clients,safe arrays
- providers,UI Automation
- safe arrays
- data types
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Best Practices for Using Safe Arrays

Many interface methods of the Microsoft UI Automation API take arguments called safe arrays, of the [**SAFEARRAY**](https://msdn.microsoft.com/library/windows/desktop/ms221482) data type. This topic describes the best practices for using safe arrays in a UI Automation applications.

## Clients

All safe arrays that are used with the UI Automation client API methods are zero-based, one-dimensional arrays. To create a safe array for a UI Automation client method, use the [**SafeArrayCreateVector**](https://msdn.microsoft.com/library/windows/desktop/ms221558) function, and to read from and write to a safe array, use the [**SafeArrayGetElement**](https://msdn.microsoft.com/library/windows/desktop/ms221255) and [**SafeArrayPutElement**](https://msdn.microsoft.com/library/windows/desktop/ms221283) functions. When you finish using a safe array, always destroy it by using the [**SafeArrayDestroy**](https://msdn.microsoft.com/library/windows/desktop/ms221702) function, whether you created the safe array or received it from a UI Automation client method.

Several UI Automation methods, including property-retrieval methods such as [**GetCurrentPropertyValue**](/windows/win32/UIAutomationClient/nf-uiautomationclient-iuiautomationelement-getcurrentpropertyvalue?branch=master), retrieve [**VARIANT**](https://msdn.microsoft.com/library/windows/desktop/ms221627)s that can contain [**POINT**](https://msdn.microsoft.com/library/windows/desktop/dd162805) or [**UiaRect**](/windows/win32/UIAutomationCore/ns-uiautomationcore-uiarect?branch=master) structures. A **POINT** is packed into a **VARIANT** as a safe array of doubles (VT\_R8) with the **x** member at index 0, and the **y** member at index 1. Similarly, a **UiaRect** is packed into a **VARIANT** as a safe array of doubles with the **left**, **top**, **width**, and **height** members at indexes 0 through 3, respectively. For an array of **UiaRect** structures, the safe array contains a sequential array of four doubles for each **UiaRect**. The **left**, **top**, **width**, and **height** members of the first **UiaRect** occupy index 0 through 3, the members of the second rectangle occupy index 4 through 7, and so on.

The [**IUIAutomation**](/windows/win32/UIAutomationClient/nn-uiautomationclient-iuiautomation?branch=master) interface includes the following methods for converting between [**SAFEARRAY**](https://msdn.microsoft.com/library/windows/desktop/ms221482) and various other data types.



| Method                                                                                               | Description                                                                                                     |
|------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| [**IUIAutomation::IntNativeArrayToSafeArray**](/windows/win32/UIAutomationClient/nf-uiautomationclient-iuiautomation-intnativearraytosafearray?branch=master)   | Converts an array of integers to a [**SAFEARRAY**](https://msdn.microsoft.com/library/windows/desktop/ms221482).                                          |
| [**IUIAutomation::IntSafeArrayToNativeArray**](/windows/win32/UIAutomationClient/nf-uiautomationclient-iuiautomation-intsafearraytonativearray?branch=master)   | Converts a [**SAFEARRAY**](https://msdn.microsoft.com/library/windows/desktop/ms221482) of integers to an array.                                          |
| [**IUIAutomation::SafeArrayToRectNativeArray**](/windows/win32/UIAutomationClient/nf-uiautomationclient-iuiautomation-safearraytorectnativearray?branch=master) | Converts a [**SAFEARRAY**](https://msdn.microsoft.com/library/windows/desktop/ms221482) that contains rectangle coordinates to an array of type **RECT**. |



 

## Providers

A provider must implement a number of interface methods that UI Automation calls to retrieve information from the provider. Many times, this information consists of an array of values. To return an array to UI Automation, the provider must pack the array into a [**SAFEARRAY**](https://msdn.microsoft.com/library/windows/desktop/ms221482) structure. The array elements must be of the expected data type, and must appear in the expected order.

## Related topics

<dl> <dt>

**Conceptual**
</dt> <dt>

[UI Automation Properties Overview](uiauto-propertiesoverview.md)
</dt> <dt>

[UI Automation Fundamentals](entry-uiautocore-overview.md)
</dt> </dl>

 

 



