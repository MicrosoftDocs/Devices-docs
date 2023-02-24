---
title: Troubleshoot Intune auto enrollment on Surface Hub
description: How to troubleshoot Intune auto enrollment issues on Surface Hub
keywords: change history
ms.prod: surface-hub
ms.sitesec: library
author: rwold
ms.author: rwold
ms.topic: article
ms.date: 02/01/2023
ms.reviewer: 
manager: laurawi
ms.localizationpriority: medium
---

# Troubleshoot Intune Auto Enrollment on Surface Hub

If your Surface Hub is successfully Azure AD joining, but failing to automatically enroll into Intune follow the troubleshooting steps on this page.

## Check MDM user scope

A common reason for Intune auto enrollment to fail is because the account used to Azure AD join the Surface Hub wasn't included in the MDM user scope to enroll into Intune. To see which users and groups are included in the MDM user scope navigate to the [Azure portal](https://portal.azure.com/), and select **Azure Active Directory > Mobility (MDM and MAM) > Microsoft Intune.**

The MDM user scope section defines the accounts capable of Intune auto enrollment. Ensure the account used to Azure AD join the Surface Hub is also included in the MDM user scope group. Otherwise, devices aren't auto enrolled in Intune during the Azure AD join process.

![MDM user scope settings within Azure.](images/intune-auto-enroll-1.png)

## Identify Intune auto enrolled Surface Hubs

You can determine if a Surface Hub was auto enrolled into Intune by navigating to the devices page within the [Azure portal](https://portal.azure.com/), and select **Azure Active Directory > Devices > All Devices.**

Locate the Surface Hub and note the join type and MDM fields. If join type shows "Azure AD joined" with "Microsoft Intune" as the MDM provider, the Surface Hub was successfully auto enrolled into Intune. If the device lists anything other than this, it wasn't auto enrolled into Intune.

![Confirming if Surface Hub device was Intune auto enrolled.](images/intune-auto-enroll-2.png)
