---
title: Surface Registration Support for Windows Autopilot
description: This article describes the requirements for submitting Autopilot registration requests to Microsoft Support. 
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/15/2022
ms.reviewer: brrecord
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
---
# Surface Registration Support for Windows Autopilot

A simplified process of registering Surface devices for Windows Autopilot deployment is now available from Microsoft Support. Customers and Microsoft Cloud Solution Providers (CSPs) can register Surface devices by submitting requests to Microsoft Support. This page outlines the requirements for the following supported Autopilot registration scenarios:
 
- **Surface Device Autopilot Registration**. Submits request to register Surface devices into Windows Autopilot.
- **Surface Device Hardware Hash Request.** Submits request to Microsoft Support to provide you with hardware hashes that customers or CSPs can use to self-register devices via Microsoft Intune or the Microsoft Partner Center.
- **Surface Device Autopilot Deregistration.** Submits request to delete devices from Windows Autopilot, typically used in device end of life scenarios.

See the following table for details of the information you will need to collect prior to submitting registration requests to Microsoft Support. For the official System Model names of all Surface devices, refer to [Surface System SKU reference](surface-system-sku-reference.md).
 
**Table 1. Required information for Autopilot registration requests**
 

| Required information                   | Description                                                                                                                                                                                                                                                                                    | Autopilot Registration | Hardware Hash Request | Autopilot<br>Deregistration |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory Tenant ID**   | Your Azure Active Directory tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain.<br> <br>To find your Tenant ID sign into the Azure Portal [here](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). | Y                      | N                     | Y                           |
| **Azure Active Directory Domain Name** | Your top-level domain name; for example, contoso.com.                                                                                                                                                                                                                                          | Y                      | N                     | Y                           |
| **Proof of ownership**                 | Verify proof of ownership by uploading the original bill of sale or invoice in PDF format. Screenshots are not accepted.<br> <br>The bill of sale or invoice  must include the following:<br>Device serial numbers.<br>Company name.                                                           | Y                      | Y                     | Y                           |
| **Device serial numbers**              | Upload Excel file in CSV format with each device serial number in a new line.                                                                                                                                                                                                                  | Y                      | Y                     | Y                           |

 

## Submit support requests

  [![Get Autopilot Registration Support for Surface.](images/autopilot-reg-support-surface.png)](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
## Learn more

- [Windows Autopilot and Surface devices](windows-autopilot-and-surface-devices.md)
- [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot)
- [Overview of Windows Autopilot](/mem/autopilot/windows-autopilot)
- [Surface System SKU reference](surface-system-sku-reference.md)

 
 
 

