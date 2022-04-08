---
title: "Install Windows 10 Team 2020 Update"
description: "Get the latest update of the Surface Hub operating system, Windows 10 Team 2020 Update."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
---
# Install Windows 10 Team 2020 Update 

The new Surface Hub operating system, **Windows 10 Team 2020 Update**, based on Windows 10 version 20H2, is now available for Surface Hub 2S and the original Surface Hub (v1). 

- See also: [Known issues: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)

## Distribution

You can obtain Windows 2020 Update using one of the following methods:

- **Windows Update for Business**.
- **Bare metal recovery (BMR) image**. Recommended option for customers who join their devices to Azure Active Directory or don’t allow their devices to receive updates from the internet. To get started, see [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).
- **Windows Update.** Availability varies by region/country, as noted in the following table:

| Phase | Country/Region                         | Starting          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ, Australia, Canada, Belgium, Mexico | October 2020  |
| 2     | UK, Japan, Switzerland, Italy          | November 2020 |
| 3     | Germany, Netherlands                   | Late February 2021 |
| 4     | Global                                 | Early March 2021 |

## Servicing Surface Hubs with Windows 10 Team Edition version 1703 

Full servicing support for [Windows 10 Team Edition version 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) is scheduled to continue until March 16, 2021.

### 2S devices 

Customers in all regions can update their Surface Hub 2S devices to the 2020 Update through Windows Update, Windows Update for Business or by using the bare metal recovery (BMR) image, as explained in [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).

### V1 devices 

Customers in all regions can update their Surface Hub v1 devices to the 2020 Update through Windows Update, Windows Update for Business, or by [using the Surface Hub Recovery Tool](surface-hub-recovery-tool.md). KB5000749 must be installed in order to receive the update over-the-air. To learn more, see [Surface IT Pro Blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371).
 
## What’s new

Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows features. To learn more, see [What's new in Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md).
 
## Before you begin

Prior to installing Windows 10 Team 2020 Update, make sure you save the BitLocker key associated with your device. 

**To manually save your BitLocker key**

1. Insert a USB drive into Surface Hub.
2. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
3. Navigate to **Update & Security** > **Recovery**.
4. Under **BitLocker**, select **Save**. The BitLocker key is saved to a text file on the USB drive.

To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).

## Learn more

- [What's new in Windows 10 Team 2020 Update](surface-hub-2020-update-whats-new.md)
- [Update to the Windows 10 Team rollout](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
