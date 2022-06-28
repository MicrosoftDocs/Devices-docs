---
title: Manage DFCI on Surface devices
description: This page shows how to configure DFCI policy settings on Autopilot-deployed Surface devices, along with documentation for every DFCI setting.
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/28/2022
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
---
# Manage DFCI on Surface devices

## Introduction

With Device Firmware Configuration Interface (DFCI) profiles built into [Microsoft Intune](/mem/autopilot/dfci-management), Surface UEFI management extends the modern management stack down to the Unified Extensible Firmware Interface (UEFI) hardware level. DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings, including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future. This page lists [all DFCI policy settings](#dfci-policy-settings-reference-for-surface-devices) on eligible Autopilot-deployed Surface devices.

Designed to be used with software-level mobile device management (MDM), DFCI enables IT admins to remotely disable specific hardware components and prevent end users from accessing them. For example, if you need to protect sensitive information in highly secure areas, you can disable the camera, and if you don't want users booting from USB drives, you can disable that also.

> [!TIP]
> Support for some DFCI policy settings varies by device. Review the [DFCI policy settings reference](#dfci-policy-settings-reference-for-surface-devices) on this page and follow [Intune instructions](/mem/intune/configuration/device-firmware-configuration-interface-windows) to configure and deploy settings to your devices.

## Prerequisites

- Windows 11 or Windows 10 version 1809 (released November 2018)
- Devices must be registered with Windows Autopilot via one of the following methods:
  - [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider)
  - [Directly from Surface](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)

> [!NOTE]
> Devices manually or self-registered for Autopilot, such as imported from a CSV file, aren't allowed to use DFCI. By design, DFCI management requires external attestation of the device's commercial acquisition via a Microsoft CSP partner or Surface registration.

## DFCI policy settings reference for Surface devices

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
> Surface Pro X doesn't support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth.

**Table 1. DFCI policy settings reference: Autopilot-deployed Surface devices**

| DFCI setting                                        | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Supported on                                                                    |
|;--------------------------------------------------- |;--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |;------------------------------------------------------------------------------- |
| **UEFI access**                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |
| **Allow local user to change UEFI (BIOS) settings** | This setting lets you manage whether end users can modify UEFI settings on eligible devices.<br><br>- If you select **Only not configured settings,**  end users may change any UEFI setting *except* any settings that you've explicitly enabled or disabled via Intune.<br>- If you select **None**, end users may not change UEFI settings, including settings not shown in the DFCI profile.                                                                                                | All eligible devices                                                            |
| **Security features**                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |
| **Windows Platform Binary Table**                   | This setting lets you manage whether the Windows Platform Binary Table (WPBT) can run on eligible devices. WPBT allows vendors and OEMs to run an .exe program in the UEFI layer. Every time Windows boots, it looks at the UEFI, and runs the .exe. It's used to run programs that aren't included with the Windows media. <br><br>- If you enable this setting, WPBT is turned on and .exe programs in the UEFI layer are allowed to run. <br>- If you disable this setting, WPBT is turned off, and .exe programs in the UEFI layer cannot run. <br>- If you don't configure this setting, WPBT is turned on. The OS might allow vendors and OEMs to run programs using the WPBT. | All eligible devices                                                            |
| **Simultaneous multithreading**                     | This setting lets you manage whether simultaneous multithreading (SMT) support is enabled on eligible devices. SMT supports Intel hyperthreading technology, which provides two logical processors for each physical core.<br><br>- If you enable this setting, SMT is turned on in the UEFI layer.<br>-  If you disable this setting, SMT is turned off in the UEFI layer.<br>-  If you don't configure this setting, SMT is enabled.                                                                               | All eligible devices                                                            |
| **Built-in hardware**                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |
| **Cameras**                                         | This setting lets you manage whether the built-in camera can function on eligible devices.<br><br>- If you enable this setting, all built-in cameras are allowed. Peripherals, like USB cameras, aren't affected.<br>- If you disable this setting, all built-in cameras are disabled. Peripherals, like USB cameras, aren't affected.<br>- If you don't configure this setting,  all built-in cameras are enabled.                            | - Not supported on Surface Pro X.<br>- Supported on all other eligible devices. |
| **Microphones and speakers**                       | This setting lets you manage whether on-board audio can function on eligible devices. <br><br> - If you enable this setting, all built-in microphones and speakers are allowed. Peripherals, like USB devices, aren't affected.<br>- If you disable this setting, all built-in microphones and speakers are disabled. Peripherals, like USB devices, aren't affected.<br>- If you don't configure this setting, microphones and speakers are enabled.                                                                              | - Not supported on Surface Pro X.<br>- Supported on all other eligible devices. |
| **Radios (Bluetooth, Wi-Fi, NFC, etc.)**   |This setting lets you manage whether built-in Bluetooth, Wi-Fi, or near field communication (NFC) can function on eligible devices. <br><br> - If you enable this setting, all built-in radios are allowed. Peripherals, like USB devices, aren't affected. <br>- If you disable this setting, all built-in radios are disabled. Peripherals, like USB devices, aren't affected. <br>- If you don't configure this setting, all built-in radios are enabled. <br><br>**CAUTION:** The **Disable** setting should only be used on devices with a wired Ethernet connection.  | - Not supported on Surface Pro X. <br>- Supported on all other eligible devices. |
| **Boot options**                                    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                                                                                 |
| **Boot from external media (USB, SD)**              | This setting lets you manage whether eligible devices can be booted from external media.<br><br>  - If you enable this setting, end users can boot the device from  USB flash drives or other non-hard drive storage technologies.<br>- If you disable this setting, end users can't boot the device from  USB flash drives or other non-hard drive storage technologies.<br>- If you don't configure this setting,  end users can boot the device from  USB flash drives or other non-hard drive storage technologies.                                                          | All eligible devices                                                            |

> [!NOTE]
> DFCI in Intune includes two settings that don't currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.

## Get started

1. Sign in to your tenant at endpoint.microsoft.com.
2. In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile**.
3. Under Platform, select **Windows 10 and later**.
4. Under Profile type, select **Templates** > **Device Firmware Configuration Interface** and then select **Create.**

    :::image type="content" source="images/dfci-start.png" alt-text="Start creating DFCI profile":::<br>

5. See [Use DFCI profiles on Windows devices in Microsoft Intune](/mem/intune/configuration/device-firmware-configuration-interface-windows) for complete instructions, including:

   - Create your Azure AD security groups
   - Create the profiles
   - Assign the profiles and reboot
   - Update existing DFCI settings
   - Reuse, retire, or recover the device

## Prevent users from changing UEFI settings

For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI. As listed above in Table 1, this is managed via the setting **Allow local user to change UEFI settings**. If you don't edit or configure this setting, an end user can change any UEFI setting not managed by Intune. Therefore, it's highly recommended to set **Allow local user to change UEFI settings** to **None.**

:::image type="content" source="images/dfci-configure.png" alt-text="Block user access to change UEFI settings":::<br>

## Verify UEFI settings on DFCI-managed devices

In a test environment, you can verify settings in the Surface UEFI interface.

1. Open Surface UEFI:
   - Press and hold the **volume-up button** on your Surface and at the same time, press and release the **power** button.
   - When you see the Surface logo, release the volume-up button. The UEFI menu will display within a few seconds.

2. Select **Devices**. The UEFI menu will reflect configured settings, as shown in the following figure.

   :::image type="content" alt-text="Surface UEFI." source="images/df3.png":::

   Note that:

      - The settings are grayed out (inactive) because **Allow local user to change UEFI setting** is set to **None**.
      - On-board Audio is set to off because **Microphones and speakers** is set to **Disabled**.

## Remove DFCI policy settings

When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile's scope of management. You can only remove DFCI policy settings by editing the DFCI profile directly. If the original DFCI profile has been deleted, create a new profile and edit the appropriate settings.

### Removing DFCI management

**To remove DFCI management and return device to factory new state:**

1. Retire the device from Intune:
    1. In Endpoint Manager at endpoint.microsoft.com, choose **Devices** > **All Devices**. Select the device you want to retire, and then choose **Retire/Wipe.** To learn more, see [Remove devices by using wipe, retire, or manually unenrolling the device](/intune/remote-actions/devices-wipe).
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
