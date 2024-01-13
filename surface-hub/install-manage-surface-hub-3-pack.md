---
title: Install and manage Surface Hub 3 Pack
description: Explains how to upgrade Surface Hub 2S to Surface Hub 3 by installing the Surface Hub 3 Pack. 
ms.reviewer: dpandre
manager: frankbu
ms.service: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 01/08/2024
ms.localizationpriority: medium
appliesto:
- Surface Hub 2S
- Surface Hub 3

---

# Install and manage Surface Hub 3 Pack

The Surface Hub 3 Pack is a hardware upgrade that transforms your Surface Hub 2S device into a Surface Hub 3. To place an order, contact your [Surface device reseller](https://www.microsoft.com/surface/business/where-to-buy-microsoft-surface#DEVICESRESELLERS).

## Prerequisites

- A Surface Hub 2S, fully updated with the latest Windows Updates. By default, updates are installed automatically during nightly maintenance. To verify, go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and install all updates.

> [!TIP]
> You may need to restart the device and continue to check for available updates. Ensure Surface Hub 2S has received one of the following updates: **Microsoft Corporation - System Hardware Update - 5/24/2023** or **Microsoft Corporation - System Hardware Update - 8/18/2023**.

- An account with admin privileges. You'll need to reset the device if you don't know your username or admin password. For more information, see [Reset and recovery for Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset).
- A resource account with a [supported Microsoft Teams Rooms license](/microsoftteams/rooms/rooms-licensing).

> [!NOTE]
> Surface Hub 3 Pack runs Windows 11 IoT Enterprise and does not support downgrading to Windows 10 Team or Windows 10 Pro/Enterprise.

### To install Surface Hub 3 Pack

Review the following demo and follow the instructions on this page.

> [!video https://www.microsoft.com/en-us/videoplayer/embed/RW1eQiI]

1. Shut down Surface Hub 2S, unplug all cables, and slide the cover sideways.

  ![Screenshot that indicates how to slide the cover sideways.](images/remove-cartridge-fig1.png).

2. Use a Phillips-head screwdriver to remove the retaining screw to detach the cartridge from Surface Hub 2S.

  ![Screenshot that shows retaining screw to remove and allow you to pull out the old cartridge.](images/remove-cartridge-fig2.png).

3. Slide the compute cartridge out. You can use the return label in the Surface Hub 3 Pack packaging to send your old cartridge to Microsoft for recycling if desired.

  ![Screenshot that shows how to slide the compute cartridge out of the unit](images/remove-cartridge-fig3.png)

4. Slide the Surface Hub 3 Pack into your Surface Hub.
5. Fasten the locking screw and slide the cover into place. Power on your new Surface Hub 3.  
6. To complete setup, refer to the following articles:

- [First-time setup for Surface Hub 3](first-run-program-surface-hub-3.md).
- [Surface Hub 3 security best practices](surface-hub-3-security.md)

## Manage Surface Hub 3 devices connected to Microsoft Entra ID (Azure AD)

If you manage Surface Hub 2S via Microsoft Intune or another mobile device management (MDM) provider, remove the device before installing Surface Pack 3.

1. Sign into Microsoft Intune admin center, go to **Devices > All devices**,  and select your Surface Hub 2S.
2. Select **Delete**.

  ![Screenshot that shows removal of Surface Hub 2S from Intune.](images/remove-hub2s-from-intune.png).

## Recycle Surface Hub 2S cartridge

You will be able recycle the Surface Hub 2S cartridge as part of recommended sustainability best practices. Check this page for updates upon availability.

### Required removal of hard drive & corporate data

Before recycling your Surface Hub 2S cartridge, first remove the hard drive and delete any corporate data.

1. You'll need the compute cartridge and a screwdriver.

![Screenshot that shows compute cartridge and screwdriver.](images/surface-hub-2s-repack-7.png)

2. Remove the cover screw and the cover from the compute cartridge and then remove the solid state drive (SSD).

![Screenshot that shows removal of cover screw and cover from the compute cartridge and removal of solid state drive (SSD).](images/surface-hub-2s-repack-8.png)

## Install custom wallpaper

The latest Windows Bloom wallpaper is available for your Surface Hub 3 device or Pack. To learn more, see [Install Windows Bloom wallpaper on Surface Hub 3](install-wallpaper-surface-hub.md).

### Learn more

- [Surface Hub 3 Pack FAQ](surface-hub-3-pack-faq.md)
