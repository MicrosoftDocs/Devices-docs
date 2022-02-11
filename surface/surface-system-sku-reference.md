---
title: Surface System SKU reference
description: See a reference of System Model and System SKU names for all Surface devices. 
keywords: uefi, configure, firmware, secure, semm, Autopilot
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 02/03/2022
ms.reviewer: carlol
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
---

# Surface System SKU reference

This document provides a reference that can be used for various IT tasks such as executing commands or installing drivers based on device model/SKU names. 
System Model and System SKU are variables stored in System Management BIOS (SMBIOS) tables in the UEFI layer of Surface devices. Use the System SKU name whenever you need to differentiate between devices with the same System Model name, such as Surface Pro and Surface Pro with LTE Advanced. SKUs listed in the following table refer to commercial devices unless labeled as Consumer. 

| Device   | System Model | System SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 Wi-FI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE North America                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE outside of North America and Y!mobile in Japan | Surface 3        | Surface_3_ROW                    |
| Surface Book 2 13"                                           | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                           | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                           | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                           | Surface Book 3   | Surface_Book_3_1899
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go Consumer                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go LTE Commercial                                    | Surface Go       | Surface_Go_1825_Commercial |
| Surface Go 2 Commercial                                      | Surface Go 2     | Surface_Go_2_1926                |
| Surface Go 2 Consumer                                        | Surface Go 2     | Surface_Go_2_1901                |
| Surface Go 2 LTE                                             | Surface Go 2     | Surface_Go_2_1927                |
| Surface Go 3 Commercial                                      | Surface Go 3     | Surface_Go_3_1926                |
| Surface Go 3 Consumer                                        | Surface Go 3     | Surface_Go_3_1901                |
| Surface Go 3 LTE                                             | Surface Go 3     | Surface_Go_3_2022                |
| Surface Hub 2S 50"                                           | Surface Hub 2S   | Surface Hub 2S                   |
| Surface Hub 2S 85"                                           | Surface Hub 2S   | Surface Hub 2S 85                |
| Surface Laptop                                               | Surface Laptop   | Surface_Laptop                   |
| Surface Laptop 2 Commercial                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Laptop 2 Consumer                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 3 13" Intel                                   | Surface Laptop 3 | Surface_Laptop_3_1867:1868 |
| Surface Laptop 3 15" AMD                                     | Surface Laptop 3 | Surface_Laptop_3_1873      |
| Surface Laptop 3 15" Intel                                   | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 4 13" AMD                                     | Surface Laptop 4 | Surface_Laptop_4_1958:1959    |
| Surface Laptop 4 13" Intel                                   | Surface Laptop 4 | Surface_Laptop_4_1950:1951 |
| Surface Laptop 4 15" AMD                                     | Surface Laptop 4 | Surface_Laptop_4_1952:1953     |
| Surface Laptop 4 15" Intel                                   | Surface Laptop 4 | Surface_Laptop_4_1978:1979     |
| Surface Laptop Go                                            | Surface Laptop Go | Surface_Laptop_Go_1943      |
| Surface Laptop SE                                            | Surface Laptop SE | Surface Laptop SE            |
| Surface Laptop Studio                                        | Surface Laptop Studio | Surface_Laptop_Studio_1964 |
| Surface Pro (5th Gen)                                        | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro with LTE Advanced (5th Gen)                      | Surface Pro      | Surface_Pro_1807                 |
| Surface Pro 6 Commercial                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Pro 6 Consumer                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 7                                                | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro 7+                                               | Surface Pro 7+   | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+   | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 8                                                | Surface Pro 8    | Surface_Pro_8_for_Business_1983|
| Surface Pro 8 Consumer                                       | Surface Pro 8    | Surface_Pro_8_1983|
| Surface Pro 8 LTE                                            | Surface Pro 8    | Surface_Pro_8_for_Business_with_LTE_Advanced_1982|
| Surface Pro X with SQ1 processor                             | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro X with SQ2 processor                             | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Pro X (Wi-Fi)                                        | Surface Pro X    | Surface_Pro_X_2010        |
| Surface Studio                                               | Surface Studio   | Surface_Studio   |
| Surface Studio 2                                             | Surface Studio 2 | Surface_Studio_2_1707_Commercial   |


## Examples

**Retrieving the SKU by using PowerShell**  
Use the following PowerShell command to pull the System SKU information:

 ``` powershell  
(Get-CimInstance -Namespace root\wmi -ClassName MS_SystemInformation).SystemSKU
```

**Retrieving the SKU by using System Information**  
You can also find the System SKU and System Model for a device in **System Information**. To do this, follow these steps:

1. Select **Start**, and then type **MSInfo32** in the search box.  
1. Select **System Information**.

**Using the SKU in a task sequence WMI condition**  
You can use the System SKU information in the Microsoft Deployment Toolkit (MDT) or Microsoft Endpoint Configuration Manager as part of a task sequence WMI condition.

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ```

## Learn more

- [WMI reference](/windows/win32/wmisdk/wmi-reference)
- [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md)
