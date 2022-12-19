---
title: Manage OEMConfig on Surface Duo 2
description: This article explains how to manage hardware components on Surface Duo 2 using Android OEMConfig via an MDM provider such as Microsoft Intune.  
ms.technology: windows
ms.prod: surface


author: coveminer
ms.author: karand
ms.topic: how-to
ms.date: 6/08/2022
ms.reviewer: karand
manager: frankbu
ms.

ms.localizationpriority: medium
appliesto:
- Surface Duo 2
---

# Manage OEMConfig on Surface Duo 2

With Surface Duo 2, admins can remotely configure specific hardware components via a mobile device management (MDM) provider such as Microsoft Intune. Specifically, you can turn on or off the following components:

- Camera
- Microphone
- Near Field Communication (NFC)
- Wireless LAN (aka Wi-Fi)
- Bluetooth

This capability is similar to Device Firmware Configuration Interface profiles that admins use to remotely manage firmware on Surface Pro 8 and other Surface devices.

OEMConfig policies are a distinct type of device configuration policy similar to app configuration policy. OEMConfig is a standard defined by Google that uses app configuration in Android to send device settings to apps written by OEMs (original equipment manufacturers). This standard allows OEMs and enterprise mobility management (EMM) solutions to build and support OEM-specific features in a standardized way. To learn more, see [OEMConfig supports enterprise device features](https://blog.google/products/android-enterprise/oemconfig-supports-enterprise-device-features/) at Google’s Android Enterprise blog.

## Prerequisites

- Surface Duo 2
- Devices configured for Full Device Management or Dedicated Device Management

## Get started

:::image type="content" source="images/surface-oem-config.png" alt-text="Microsoft Surface OEM Config app" :::

First, add the Microsoft Surface OEMConfig application to your environment using the Managed Google Play iframe in your EMM.

First, assign the Surface OEMConfig app to the groups or users you want to target. Then create an Android Configuration profile to apply your settings to target devices.

> [!NOTE]
> This guide shows how to use OEMConfig with Microsoft Intune, which functions as an MDM and EMM solution. However, the feature can be used with [any EMM that supports Full Device Management or Dedicated Device Management](https://androidenterprisepartners.withgoogle.com/emm/).

## Assign Surface OEMConfig to groups or users

> [!TIP]
> Before beginning, review Intune documentation: [Managed Google Play app deployment to unmanaged devices](/mem/intune/apps/apps-deploy#managed-google-play-app-deployment-to-unmanaged-devices)

1. Sign in to the Intune portal at [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/).
2. Go to **Apps** > **Android** > and select **Add**.
3. Under **App** type, select **Managed Google Play**.
4. On the **Managed Google Play** page, search for Microsoft Surface OEMConfig.
5. On the Surface OEMConfig page, select  **Properties**. Under Assignments, select **Edit**.
6. Assign to groups or users as appropriate.
7. Select **Review** + save.

## Manage firmware on Surface Duo 2

1. Select **Devices** > **Android Configuration profiles** > **Create profile**.
2. Under Platform, select **Android enterprise**. Under **Profile** type, choose **OEMConfig** and then select  **Create**.
3. Enter a name and an optional description.
4. Choose **Select an OEMConfig app** and select **Surface OEMConfig**. Select **Next**.
5. Select **Next**. On the configuration settings page, you can manage the following: Camera, Microphone, Near Field Communication (NFC), Wireless LAN (aka Wi-Fi), and Bluetooth. These components are enabled by default. To turn any of them off, select **false** and click **Next**.
6. Enter scope tags as appropriate and select **Next**.
7. Under Assignments, add a group containing the Surface Duo 2 devices you wish to target. Or you can add All users or All devices, as appropriate. Select **Next**.
8. Review the profile and select **Create**.

## Security

To enhance the security of your deployment, consider deploying additional Android Enterprise policies designed to prevent accidental misuse of devices:

- Disable developer mode.
- Use Enterprise Factory Reset Protection to control who can perform a factory reset on your devices.

To learn more, see [Android Enterprise device settings to allow or restrict features using Intune](/mem/intune/configuration/device-restrictions-android-for-work).

## Reporting

[Microsoft Intune reports](/mem/intune/fundamentals/reports) allow you to monitor the health and activity of Surface Duo 2 devices across your organization and provide other reporting data across Intune. To learn more, see [Microsoft Intune reports](/mem/intune/fundamentals/reports)

## Related links

- [Android Enterprise device settings to allow or restrict features using Intune](/mem/intune/configuration/device-restrictions-android-for-work).
- [Microsoft Intune reports](/mem/intune/fundamentals/reports)
- [Android Enterprise EMM directory](https://androidenterprisepartners.withgoogle.com/emm/)
