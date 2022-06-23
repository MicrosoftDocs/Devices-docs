---
title: Manage DFCI on Surface devices
description: This article explains how to configure a DFCI environment in Microsoft Intune and manage firmware settings for targeted Surface devices.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/01/2021
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
---
# Manage DFCI on Surface devices

## Introduction

With Device Firmware Configuration Interface (DFCI) profiles built into [Microsoft Intune](/intune/configuration/device-firmware-configuration-interface-windows), Surface UEFI management extends the modern management stack down to the Unified Extensible Firmware Interface (UEFI) hardware level. DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings, including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.

Designed to be used with software-level mobile device management (MDM), DFCI enables IT admins to lock down devices at the hardware level. This page shows how to configure DFCI policy settings on Autopilot-deployed Surface devices, along with documentation for every DFCI setting.

## Overview

1. Review [Intune DFCI documentation](/mem/autopilot/dfci-management) to ensure your devices and environment meet the requirements to manage DFCI.
2. Review [DFCI settings reference](#dfci-settings-reference-for-surface-devices) below for a description of all available settings on Surface devices.
3. [Configure DFCI settings](#configure-dfci-settings-for-surface-devices).
4. [Target DFCI settings](#target-dfci-settings-to-surface-devices).
5. [Apply DFCI settings on new devices](#apply-dfci-settings-on-new-devices).

## Prerequisites

Devices must be registered with Windows Autopilot by a [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider) or OEM distributor. To learn more, see:

- [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md)

Before you begin, review how to set up and manage a DFCI profile with Windows Autopilot, as documented in [Use DFCI profiles on Windows devices in Microsoft Intune](/mem/intune/configuration/device-firmware-configuration-interface-windows)

## DFCI settings reference for Surface devices

### Eligible devices

- Surface Pro 8 (commercial SKUs only)
- Surface Pro 7+ (commercial SKUs only)
- Surface Pro 7 (all SKUs)
- Surface Pro X (all SKUs)
- Surface Laptop Studio (commercial SKUs only)
- Surface Laptop 4 (commercial SKUs only)
- Surface Laptop 3 (Intel processors only)
- Surface Laptop Go
- Surface Laptop Go 2
- Surface Laptop SE
- Surface Book 3
- Surface Go 3 (commercial SKUs only)

> [!NOTE]
> Surface Pro X doesn't support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth. Some newer settings are only supported on the latest devices.

**Table 1. DFCI settings reference**

| DFCI setting                                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Supported on                                                                    |
| --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| **UEFI access**                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |
| **Allow local user to change UEFI (BIOS) settings** | This setting lets you manage whether end users can modify UEFI settings.<br><br>- If you select **Only not configured settings,** the local user may change any setting *except* any settings that you've explicitly enabled or disabled via Intune.<br>- If you select **None**, the local user may not change UEFI settings, including settings not shown in the DFCI profile.                                                                                                | All eligible devices                                                            |
| **Security settings**                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |
| **Windows Platform Binary Table**                   | This setting lets you manage whether Windows Platform Binary Table  (WPBT) can run on eligible devices. WPBT allows computer vendors to force the installation of a service program or anti-theft software, exposing devices to potentially unwanted 3rd party programs that run on first boot.<br>If you enable this setting, WPBT is allowed to run.<br><br>- If you disable this setting, WPBT can't run. <br>- If you don't configure this setting, WPBT is allowed to run. | All eligible devices                                                            |
| **Simultaneous multithreading**                     | This setting lets you manage whether simultaneous multithreading (SMT) support is enabled on eligible devices. SMT supports Intel hyperthreading technology, which provides two logical processors for each physical core.<br><br>- If you enable this setting, SMT is turned on.<br>-  If you disable this setting, SMT is turned off.<br>-  If you don't configure this setting, SMT is enabled.                                                                               | All eligible devices                                                            |
| **Cameras**                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |
| **Cameras**                                         | This setting lets you manage whether devices can utilize the built-in camera.<br><br>- If you enable this setting, all built-in cameras are allowed. Peripherals, like USB cameras, aren't affected.<br>- If you disable this setting, all built-in cameras are disabled. Peripherals, like USB cameras, aren't affected.<br>- If you don't configure this setting,  all built-in cameras are enabled. Intune doesn't change or update this setting.                             | - Not supported on Surface Pro X.<br>- Supported on all other eligible devices. |
| **Microphones and speakers:**                       | - If you enable this setting, all built-in microphones and speakers are allowed. Peripherals, like USB devices, aren't affected.<br>- If you disable this setting, all built-in microphones and speakers are disabled. Peripherals, like USB devices, aren't affected.<br>- If you don't configure this setting, microphones and speakers are enabled. Intune doesn't change or update this setting.                                                                             | - Not supported on Surface Pro X.<br>- Supported on all other eligible devices. |
| **Microphones**                                     | - If you enable this setting, all built-in microphones are enabled. Peripherals, like USB devices, aren't affected.<br>- If you disable this setting, all built-in microphones are disabled. Peripherals, like USB devices, aren't affected.<br>- If you don't configure this setting, microphones are enabled. Intune doesn't change or update this setting.                                                                                                                    | - Not supported on Surface Pro X.<br>- Supported on all other eligible devices. |
| **Radios (Bluetooth, Wi-Fi, NFC, etc...)**           | - If you enable this setting, all built-in radios are allowed. Peripherals, like USB devices, aren't affected.<br>- If you disable this setting, all built-in radios are disabled. Peripherals, like USB devices, aren't affected.<br>- If you don't configure this setting, all built-in radios are enabled.<br><br>CAUTION: The **Disable** setting should only be used on devices with a wired Ethernet connection.                                                           | - Not supported on Surface Pro X.<br>- Supported on all other eligible devices. |
| Bluetooth                                           | - If you enable this setting, Bluetooth is enabled.<br>- If you disable this setting,  Bluetooth is disabled.<br>- If you don't configure this setting,  Bluetooth is enabled.                                                                                                                                                                                                                                                                                                   | - Not supported on Surface Pro X.<br>- Supported on all other eligible devices. |
| Wi-Fi                                               | - If you enable this setting,  Wi-Fi is enabled.<br>- If you disable this setting,  Wi-Fi is disabled.<br>- If you don't configure this setting,  Wi-Fi is enabled.                                                                                                                                                                                                                                                                                                              | - Not supported on Surface Pro X.<br>- Supported on all other eligible devices. |
| Boot options                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |
| Boot from external media (USB, SD)                  | - If you enable this setting, end users can boot the device from  USB flash drives or other non-hard drive storage technologies.<br>- If you disable this setting, end users can't boot the device from  USB flash drives or other non-hard drive storage technologies.<br>- If you don't configure this setting,  end users can boot the device from  USB flash drives or other non-hard drive storage technologies.                                                           | All eligible devices                                                            |
| **Ports**                                           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |
| USB type A                                          | This setting lets you manage how devices can utilize USB-A connections.<br><br>- If you enable this setting,  USB-A data connections are allowed on eligible devices.<br>- If you disable this setting, USB-A data connections are disabled on eligible devices.<br><br>If you don't configure this setting, USB-A data connections are enabled on all devices.                                                                                                                  | Supported only on Surface Laptop Go 2 and later.                                |
| Wake settings                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |
| Wake on LAN                                         | This setting lets you manage whether eligible devices can be remotely started from Modern Standby.<br><br>- If you enable this setting, IT admins can remotely wake eligible devices.<br>- If you disable this setting,  admins can't remotely wake eligible devices.<br>- If you don't configure this setting,  admins can remotely wake eligible devices.                                                                                                                     | Supported only on Surface Laptop Go 2 and later.                                |
| Wake on power                                       | This setting lets you manage whether eligible devices can be remotely started from Modern Standby, hibernation, or powered-off states.<br><br>- If you enable this setting, eligible Surface devices can be configured to automatically start when reconnected to power<br>- If you disable this setting,  eligible Surface devices can't be remotely powered on.<br>- If you don't configure this setting, eligible Surface devices can be configured to automatically start when reconnected to power.                                                                        | Supported only on Surface Laptop Go 2 and later.                                |

> [!NOTE]
> DFCI in Intune includes two settings that don't currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.

## Configure DFCI settings for Surface devices

1. Sign in to your tenant at devicemanagement.microsoft.com.
2. In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile** and enter a name; for example, **DFCI Configuration Policy.**
3. Under Platform, select **Windows 10 and later**.
4. Under Profile type, select **Templates** > **Device Firmware Configuration Interface** and then select **Create.**

:::image type="content" source="images/dfci-start.png" alt-text="Start creating DFCI profile":::<br>

5. Name the profile, add an optional description and select **Next**.
6. On the configuration settings page, select the category of settings you wish to configure.

    :::image type="content" source="images/dfci-config-settings.png" alt-text="Select DFCI settings category":::<br>

## UEFI access

For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI. As listed in [Table 1](#), this is managed via the setting **Allow local user to change UEFI settings**. If you don't edit or configure this setting, local users can change any UEFI setting not managed by Intune. Therefore, it's highly recommended to set **Allow local user to change UEFI settings** to **None.**

    :::image type="content" source="images/dfci-configure.png" alt-text="Block user access to change UEFI settings":::<br>

## All DFCI settings

DFCI lets you remotely disable hardware components and prevent users from accessing them. For example, suppose you must protect sensitive information in highly secure areas. In that case, you can disable the camera, and if you don't want users booting from USB drives, you can disable that also.
In most cases, this requires you to set a policy to Disable. For example, to turn off access to the built-in camera, select Cameras and then choose **Disabled.**

:::image type="content" source="images/dfci-disable-camera.png" alt-text="Disable built-in camera":::<br>

## Target DFCI settings to Surface devices

When you finish configuring the desired settings, target the settings to your intended Surface devices.

1. On the Assignments page, add groups containing your target devices. Or you can **Add all users** or **Add all devices.** Select **Next.** For more information about creating and managing security groups, see [Intune documentation](/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).

    :::image type="content" source="images/dfci-assign.png" alt-text="Assign DFCI profile":::<br>

2. On the Applicability Rules page, you can target DFCI settings to apply to specific operating systems (OS edition) and OS versions. Select **Next**.

    :::image type="content" source="images/dfci-rules.png" alt-text="Apply DFCI rules":::<br>

3. On the Review + create page, check your intended DFCI settings and choose **Create.** This example blocks users from changing UEFI settings.

:::image type="content" source="images/dfci-create.png" alt-text="Create DFCI profile":::<br>

## Apply DFCI settings on new devices

To ensure that devices, apply the DFCI configuration during OOBE before users sign in, you need to configure enrollment status. For more information, see [Set up an enrollment status page](/intune/enrollment/windows-enrollment-status).

## Verify UEFI settings on DFCI-managed devices

In a test environment, you can verify settings in the Surface UEFI interface.

1. Open Surface UEFI, which involves pressing the **Volume +** and **Power** buttons at the same time.
2. Select **Devices**. The UEFI menu will reflect configured settings, as shown in the following figure.
   :::image type="content" alt-text="Surface UEFI." source="images/df3.png":::

Note how:
    - The settings are greyed out because **Allow local user to change UEFI setting** is set to None.
    - Audio is set to off because **Microphones and speakers** are set to **Disabled**.

## Remove DFCI policy settings

When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile's scope of management. You can only remove DFCI policy settings by editing the DFCI profile directly.
If the original DFCI profile has been deleted, create a new profile and edit the appropriate settings.

## Remove DFCI management

**To remove DFCI management and return device to factory new state:**

1. Retire the device from Intune:
    1. In Endpoint Manager at devicemanagement.microsoft.com, choose **Groups > All Devices**. Select the devices you want to retire, and then choose **Retire/Wipe.** To learn more, see [Remove devices by using wipe, retire, or manually unenrolling the device](/intune/remote-actions/devices-wipe).
2. Delete the Autopilot registration from Intune:
    1. Choose **Device enrollment > Windows enrollment > Devices**.
    2. Under Windows Autopilot devices, choose the devices you want to delete, then choose **Delete**.
3. Connect the device to wired internet with a Surface-branded ethernet adapter. Restart the device and open the UEFI menu (press and hold the volume-up button while also pressing and releasing the power button).
4. Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**

To manage the device with Intune but without DFCI management, self-register it to Autopilot and enroll it in Intune. DFCI won't be applied to self-registered devices.

## Learn more

- [DFCI Management | Microsoft Docs](/mem/autopilot/dfci-management)
- [Use DFCI profiles on Windows devices in Microsoft Intune](/intune/configuration/device-firmware-configuration-interface-windows)
- [Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot and Surface devices](windows-autopilot-and-surface-devices.md)
- [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
