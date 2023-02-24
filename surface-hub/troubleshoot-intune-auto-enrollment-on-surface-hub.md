---
title: Troubleshoot Intune auto enrollment on Surface Hub
description: How to troubleshoot Intune auto enrollment issues on Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: rwold
ms.author: rwold
ms.topic: article
ms.date: 02/24/2023
ms.reviewer: 
manager: laurawi
ms.localizationpriority: medium
---

# Troubleshoot Intune auto enrollment on Surface Hub

If your Surface Hub is joined to Azure AD but fails to automatically enroll in Intune, follow the troubleshooting steps on this page.

## Check MDM user scope

Intune auto-enrollment fails when the account used to Azure AD join the Surface Hub wasn't included in the MDM user scope to enroll in Intune. To verify the users and groups included in the MDM user scope:

1. Go to the [Azure portal](https://portal.azure.com/), and select **Azure Active Directory > Mobility (MDM and MAM) > Microsoft Intune.** The MDM user scope section defines the accounts capable of Intune auto-enrollment.
2. Ensure the account used to Azure AD join the Surface Hub is also included in the MDM user scope group. Otherwise, devices don't automatically enroll in Intune during the Azure AD join process.

![MDM user scope settings within Azure.](images/intune-auto-enroll-1.png)

## Identify Intune auto enrolled Surface Hubs

To determine if a Surface Hub was auto-enrolled in Intune:

1. Go to the [Azure portal](https://portal.azure.com/) and select **Azure Active Directory > Devices > All Devices.**
2. Locate the Surface Hub and note the join type and MDM fields. If the join type shows "Azure AD joined" with "Microsoft Intune" as the MDM provider, the Surface Hub was successfully auto-enrolled in Intune. If the device lists anything else, it wasn't auto-enrolled in Intune.

![Image that confirms Surface Hub was Intune auto-enrolled.](images/intune-auto-enroll-2.png)
