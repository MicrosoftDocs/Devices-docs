---
title: Surface Battery Limit setting 
description: Enable Battery Limit on Surface devices that are always powered on such as in kiosk scenarios. Battery Limit is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.
ms.prod: surface
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.localizationpriority: medium
manager: frankbu
ms.date: 01/13/2023
---

# Surface Battery Limit setting

The Battery Limit option is a Surface UEFI (BIOS) setting that changes how the Surface device battery is charged and may prolong its longevity. This setting is recommended for devices continuously connected to power, such as kiosk scenarios. The Battery Limit UEFI setting is built into Surface devices by default including:

- Surface Go and later
- Surface Pro 7 and later
- Surface Laptop 3 and later
- Surface Book 3
- Surface Laptop Studio
- Surface Laptop Go
- Surface Laptop Go 2
- Surface Laptop SE

## How it works

When you enable the Battery Limit setting, the battery stops charging when it reaches 50% of maximum charge capacity. If you enable Battery Limit when your device is more than 50% charged, the battery won't resume charging until it drops below 50% of maximum charge.

Enable Battery Limit via one of the following methods:

- [Modify Surface UEFI on an individual device](#modify-surface-uefi-on-an-individual-device)
- [Create a Surface UEFI configuration package for remote deployment to multiple devices](#create-a-surface-uefi-configuration-package-for-remote-deployment-to-multiple-devices)

## Modify Surface UEFI on an individual device

1. Boot into Surface UEFI: Press **Power + Vol Up** when turning on the device.
2. Choose **Boot configuration** > **Advanced Options**, and toggle **Enable Battery Limit** to **On**.  
:::image type="content" source="images/enable-bl.png" alt-text="Screenshot of Battery Limit Advanced options." :::

> [!TIP]
> On Surface Go (all generations): Choose **Boot configuration** > **Kiosk Mode**, and move the slider to the right to set Battery Limit to **Enabled**.  

## Create a Surface UEFI configuration package for remote deployment to multiple devices

If you're an advanced IT admin, you can use [Surface UEFI Configurator](enroll-and-configure-surface-devices-with-semm.md) to modify Surface UEFI and remotely deploy it to multiple devices via [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md). Alternatively, you can use Surface UEFI Manager PowerShell scripts (SEMM_Powershell.zip) available from [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).

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

## Learn more

- [Enroll and configure Surface devices with SEMM](enroll-and-configure-surface-devices-with-semm.md)
- [Best practice power settings for Surface devices](maintain-optimal-power-settings-on-Surface-devices.md)
