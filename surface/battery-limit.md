---
title: Surface Battery Limit setting 
description: Enable Battery Limit on Surface devices that are always powered on such as in kiosk scenarios. Battery Limit is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.
ms.prod: surface
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.localizationpriority: medium
manager: frankbu
ms.date: 11/02/2023
---

# Surface Battery Limit setting

The Battery Limit option is a Surface UEFI setting that changes how the Surface device battery is charged and may prolong its longevity. This firmware setting (similar to BIOS) is recommended for devices intended to be always connected to power. Examples include devices configured for point of sale, RFID, and related kiosk scenarios. The Battery Limit UEFI setting is built into Surface devices by default including:

- Surface Go (all generations)
- Surface Pro 7 and later
- Surface Laptop 3 and later
- Surface Book 3
- Surface Laptop Studio (all generations)
- Surface Laptop Go (all generations)
- Surface Laptop SE

Many other devices also support Battery Limit with a firmware update, as described in the following section: [Battery Limit support on other Surface devices](#battery-limit-support-on-other-surface-devices).

## How it works

When you enable the Battery Limit setting, the battery stops charging when it reaches 50% of maximum charge capacity. If you enable Battery Limit when your device is more than 50% charged, the battery won't resume charging until it drops below 50% of maximum charge.

Enable Battery Limit via one of the following methods:

- [Modify Surface UEFI on an individual device](#modify-surface-uefi-on-an-individual-device)
- [Create a Surface UEFI configuration package for remote deployment to multiple devices](#create-a-surface-uefi-configuration-package-for-remote-deployment-to-multiple-devices)

## Modify Surface UEFI on an individual device

1. Boot into Surface UEFI: Press **Power + Vol Up** when turning on the device.
2. Choose **Boot configuration** > **Advanced Options**, and toggle **Enable Battery Limit** to **On**.

   :::image type="content" source="images/enable-bl.png" lightbox="images/enable-bl.png" alt-text="Screenshot of Battery Limit Advanced options." :::

   > [!TIP]
   > On Surface Go (all generations): Choose **Boot configuration** > **Kiosk Mode**, and move the slider to the right to set Battery Limit to **Enabled**.  

## Create a Surface UEFI configuration package for remote deployment to multiple devices

If you're an advanced IT admin, you can use [Surface UEFI Configurator](enroll-and-configure-surface-devices-with-semm.md) to modify Surface UEFI and remotely deploy it to multiple devices via [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md). Alternatively, you can use Surface UEFI Manager PowerShell scripts (SEMM_Powershell.zip) available from [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).

> [!NOTE]
> To use SEMM, most eligible devices must be commercial SKUs, branded as "Surface for Business." For a complete list of compatible devices, see [Supported devices](/surface/surface-enterprise-management-mode#supported-devices).

### Use Microsoft Surface UEFI Configurator

1. Open [UEFI Configurator](enroll-and-configure-surface-devices-with-semm.md).
2. On the **Advanced Settings** configuration page, toggle the **Kiosk Overrides** setting to **On**.
3. Toggle **Battery Limit** to **On**.

   :::image type="content" source="images/semm-bl.png" alt-text="Screenshot of advanced settings showing option to enable Battery Limit." :::

### Use Surface UEFI Manager PowerShell scripts

The battery limit feature is controlled via the following setting:  

`407 = Battery Profile`

**Description**:  Active management scheme for battery usage pattern

**Default**:  `0`

Configure setting to `1` to enable Battery Limit.

### Battery Limit support on other Surface devices

The following devices require a firmware update to support this feature:

- Surface Pro 3 - [September 10, 2018 update](https://support.microsoft.com/surface/surface-pro-3-update-history-78dc8c2a-97ba-fd87-f24f-ed76e8a66a38). Surface Embedded Controller firmware version 38.14.80.0 and later versions.
- Surface 3 - [December 6th, 2018 update](https://support.microsoft.com/surface/surface-3-update-history-5d86a7bc-03f7-2d27-d858-e90ce637fb52). Surface UEFI firmware version 1.51116.218.0 and later versions.
- Surface Pro 4 - [September 10, 2018 update](https://support.microsoft.com/surface/surface-pro-4-update-history-bc6b3a9b-a2a7-5d29-7590-46290d69218b). Surface Embedded Controller firmware version 103.2241.256.0 and later versions.
- Surface Book - [October 10, 2018 update](https://support.microsoft.com/surface/surface-book-update-history-3c36b18d-1261-2cfa-4ae8-67e1a84bb175). Surface Embedded controller firmware version 90.2226.256.0 and later versions.

  > [!NOTE]
  > This feature only applies to the battery in the detachable clipboard.

- Surface Laptop (1st gen) - [January 24, 2019 update](https://support.microsoft.com/surface/surface-laptop-1st-gen-update-history-0f7552c1-3476-a9e3-7cdb-e176102d1b6d). Surface System Aggregator firmware version 145.106.139.09 and later versions.
- Surface Pro (5th gen) and Surface Pro with Advanced LTE Model 1807 - [August 1, 2019 update](https://support.microsoft.com/surface/surface-pro-5th-gen-update-history-5203144a-90c1-63df-ce0b-7ec7ff32ff10). Surface System Aggregator firmware version 239.2660.257.0 and later versions.
- Surface Book 2 - [July 9, 2020 update](https://support.microsoft.com/help/4055398). Surface System Aggregator firmware version 182.2107.139.0 and later versions will apply Battery Limit Mode on the battery in the keyboard base, in addition to the detachable clipboard.
- Surface Go - [November 9, 2018 update](https://support.microsoft.com/surface/surface-go-update-history-c069f02e-5025-54b6-5fc1-2f5567783510). Surface UEFI firmware Version 1.0.10.0 and later versions.
- Surface Pro 6 - [August 1, 2019 update](https://support.microsoft.com/surface/surface-pro-6-update-history-1c611758-6d57-0a45-047b-ac358460033d). Surface System Aggregator firmware version 239.3101.139.0 and later versions.
- Surface Laptop 2 - [January 24, 2019 update](https://support.microsoft.com/surface/surface-laptop-2-update-history-33ead443-0d84-54ab-c22f-66c3e4cca855). Surface System Aggregator firmware version 145.106.1339.0 and later versions.
- Surface Go with LTE Advanced - [July 23, 2019 update](https://support.microsoft.com/surface/surface-go-update-history-c069f02e-5025-54b6-5fc1-2f5567783510). Surface UEFI firmware version 1.1.12.0 and later versions.

## Learn more

- [Enroll and configure Surface devices with SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Best practice power settings for Surface devices](maintain-optimal-power-settings-on-Surface-devices.md)
