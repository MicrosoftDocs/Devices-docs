---
title: "Enable dual-pen support for Surface Hub 2S"
description: "This page describes how to configure two Surface Hub 2 pens for use at the same time, enabling side by side collaboration."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
---
# Enable dual-pen support for Surface Hub 2S

Users can write with two Surface Hub 2 pens at the same time on Surface Hub 2S, enabling them to collaborate side-by-side. To enable this feature:


1. Get the Windows 10 Team 2020 Update.
2. Get the latest firmware for Surface Hub 2S.
3. Check the latest firmware is installed.
4. Update Surface Hub 2S Pen with the latest firmware.


## Get the Windows 10 Team 2020 Update

For more information, see [Install Windows 10 Team 2020 Update Preview Build](surface-hub-install-2020preview.md).
 
## Get the latest firmware for Surface Hub 2S

### Manually download firmware from Windows Update

After you've installed the Windows 10 Team 2020 Update:

1. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
2. Navigate to **Update & Security** > **Windows Update** and then select **Check for updates**.
3. Once you've downloaded and installed the update, select **Restart now** to complete the firmware update.

## Verify firmware installation

After you've installed the Windows 10 Team 2020 Update, your Surface Hub will automatically download and install the latest firmware during the next maintenance window. To check that the latest firmware is installed:

1. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
2. Navigate to **Update & Security** > **Windows Update** and then select **View update history**.
3. Under **Driver Updates**, check that **Surface - Firmware - ###** is successfully installed.

## Update Surface Hub 2S Pen with the latest firmware

Once you have installed the latest firmware for Surface Hub 2S, update the Surface Hub 2 Pen by pairing it with your Surface Hub 2S.


1. On your Surface Hub 2 Pen, press and hold the **top** button until the white indicator LED begins to blink.
![Surface Hub 2 pen](images/sh2-pen-1.png) <br>
2. On your Surface Hub 2S, open **Settings** and enter your admin credentials when prompted.
3. Navigate to **Devices** > **Bluetooth & other devices**, and select **Add Bluetooth or other device**.
4. On the **Add a device** dialog, select **Bluetooth**. Select the Surface Hub 2 Pen and follow the prompts to complete the pairing process.

Once paired, the Surface Hub 2 Pen will automatically install the firmware update. Use the **Surface** app to check that the latest firmware is installed:


1. On Surface Hub 2S, open **Surface** from the Start menu. If it isn’t installed, download the app from the Microsoft Store.
2. Using the side menu, navigate to **Accessories**.
3. Under Surface Hub 2 Pen, check that **Firmware version** is **468.3226.256** or greater.

