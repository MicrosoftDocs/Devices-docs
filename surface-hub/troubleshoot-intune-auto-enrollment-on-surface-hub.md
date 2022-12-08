---
title: "Troubleshoot Intune Auto Enrollment on Surface Hub"
description: "This page describes how to verify and troubleshoot intune auto enrollment for Surface Hub."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: ryan-wold
ms.author: rwold
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/8/2022
ms.localizationpriority: Medium
---

# Troubleshoot Intune Auto Enrollment on Surface Hub

Azure AD joining with Intune auto enrollment allows the Surface Hub to enroll into Intune without any additional steps.
 
If the Surface Hub is Azure AD joined and then *manually* enrolled into Intune, two device objects will be present in Azure. When the Surface Hub is Azure AD joined with Intune auto enrollment a single device object is created within Azure. A single object is needed for the Surface Hub to work with the non Global Admin policy and for the device to be marked as "compliant" for use with user based Conditional Access policies.
 
## Verify Surface Hub was Auto Enrolled into Intune

We can verify the Surface Hub was successfully auto enrolled into Intune by navigating to the Devices page within the Azure AD portal. 
 
Locate the Surface Hub device and note the Join Type and MDM columns. If it shows the Surface Hub was "Azure AD joined" with "Microsoft Intune" listed under MDM the device was successfully auto enrolled into Intune. If the device shows as "Azure AD registered" or if "None" is listed under MDM the Surface Hub was not auto enrolled into Intune.

**Microsoft Azure > Devices > All Devices**

![](images/intune-auto-enroll-1.png)


## Check MDM User Scope

If Intune auto enrollment failed that likely means the account used to Azure AD join was not scoped correctly to auto enroll. We can verify this by opening the Azure AD portal and navigating to the Mobility (MDM and MAM) configuration page. 
 
MDM user scope defines the accounts capable of Intune auto enrollment. Ensure the account being used to Azure AD join the Surface Hub is included in the MDM user scope group. Otherwise, devices will not be auto enrolled in Intune during the Azure AD join process.

**Microsoft Azure > Mobility (MDM and MAM) > Microsoft Intune > MDM User Scope**

![](images/intune-auto-enroll-2.png)



