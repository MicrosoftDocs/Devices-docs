---
title: Install apps on your Microsoft Surface Hub
description: Admins can install apps can from either the Microsoft Store or the Microsoft Store for Business.
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: dpandre
manager: laurawi
keywords: install apps, Microsoft Store, Microsoft Store for Business
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/24/2021
ms.localizationpriority: medium
audience: ITPro
---

# Install apps on your Microsoft Surface Hub

You can install additional apps on your Surface Hub to fit your team or organization's needs. There are different methods for installing apps depending on whether you are developing and testing an app, or deploying a released app. This topic describes methods for installing apps for either scenario.

## Supported app guidelines

- Surface Hub only runs [Universal Windows Platform (UWP) apps](/windows/uwp/get-started/universal-application-platform-guide). Apps created using the [MSIX Packaging Tool] (/windows/msix/packaging-tool/tool-overview) will not run on Surface Hub.
- Apps must be targeted for the [Universal device family](/windows/uwp/get-started/universal-application-platform-guide) or Windows Team device family.
- Surface Hub only supports [offline-licensed apps](/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store/private-store).
- By default, apps must be Store-signed to be installed. During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.
- When submitting an app to the Microsoft Store, developers need to set Device family availability and Organizational licensing options to make sure an app will be available to run on Surface Hub.
- You need admin credentials to install apps on your Surface Hub. Since the device is designed to be used in communal spaces like meeting rooms, people can't access the Microsoft Store to download and install apps.

## Deploy released apps

There are several options for installing apps that have been released to the Microsoft Store, depending on whether you want to evaluate them on a few devices, or deploy them broadly to your organization.

To install released apps:

- Download the app using the Microsoft Store app, or
- Download the app package from the Microsoft Store for Business, and distribute it using a provisioning package or a supported MDM provider.

### Microsoft Store app

To evaluate apps released on the Microsoft Store, use the Microsoft Store app on the Surface Hub to browse and download apps.

> [!NOTE]
> Using the Microsoft Store app is not the recommended method of deploying apps at scale to your organization:
>
> - To download apps, you must sign in to the Microsoft Store app with a Microsoft account or organizational account. However, you can only connect an account to a maximum of 10 devices at once. If you have more than 10 Surface Hubs, you will need to create multiple accounts or remove devices from your account between app installations.
> - To install apps, you will need to manually sign in to the Microsoft Store app on each Surface Hub you own.

#### To browse the Microsoft Store on Surface Hub

1. From your Surface Hub, start **Settings**.
2. Type the device admin credentials when prompted.
3. Navigate to **This device** > **Apps & features**.
4. Select **Open Store**.

### Download app packages from Microsoft Store for Business

To download the app package you need to install apps on your Surface Hub, visit the [Microsoft Store for Business](https://www.microsoft.com/business-store). The Store for Business is where you can find, acquire, and manage apps for the Windows 10 devices in your organization, including Surface Hub.

> [!NOTE]
> Currently, Surface Hub only supports offline-licensed apps available through the Store for Business. App developers set offline-license availability when they submit apps.

Find and acquire the app you want, then download:

- The offline-licensed app package (either an .appx or an .appxbundle)
- The *unencoded* license file (if you're using provisioning packages to install the app)
- The *encoded* license file (if you're using MDM to distribute the app)
- Any necessary dependency files

For more information, see [Download an offline-licensed app](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).

### Install offline-licensed apps via provisioning package

You can manually install the offline-licensed apps that you downloaded from the Store for Business on a few Surface Hubs using provisioning packages. Use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package and *unencoded* license file that you downloaded from the Store for Business. For more information, see [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md).

### Supported MDM provider

To deploy apps to a large number of Surface Hubs in your organization, use a supported MDM provider. The table below shows which MDM providers support deploying offline-licensed app packages.

| MDM provider                | Supports offline-licensed app packages |
|-----------------------------|----------------------------------------|
| On-premises MDM with  Configuration Manager (beginning in version 1602) | Yes |
|
| Third-party MDM provider    | Check to make sure your MDM provider supports deploying offline-licensed app packages. |

> [!NOTE]
> To deploy offline apps remotely using Microsoft Intune, refer to [Manage VPP apps from Microsoft Store for Business](/mem/intune/apps/windows-store-for-business). Surface Hub app deployment only supports offline apps that are deployed in a device context.

## Develop and test apps

While you're developing your own app, there are a few options for testing apps on Surface Hub.

### Developer Mode

By default, Surface Hub only runs UWP apps that have been published to and signed by the Microsoft Store. Apps submitted to the Microsoft Store go through security and compliance tests as part of the [app certification process](/windows/uwp/publish/the-app-certification-process), so this helps safeguard your Surface Hub against malicious apps.

By enabling developer mode, you can also install developer-signed UWP apps.

> [!IMPORTANT]
> After developer mode has been enabled, you will need to reset the Surface Hub to disable it. Resetting the device removes all local user files and configurations and then reinstalls Windows.

#### To turn on developer mode

1. From your Surface Hub, start **Settings**.
2. Type the device admin credentials when prompted.
3. Navigate to **Update & security** > **For developers**.
4. Select **Developer mode** and accept the warning prompt.

### Visual Studio

During development, the easiest way to test your app on a Surface Hub is using Visual Studio. Visual Studio's remote debugging feature helps you discover issues in your app before deploying it broadly. For more information, see [Test Surface Hub apps using Visual Studio](/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio).

#### Create provisioning package

Use Visual Studio to create an app package for your UWP app, signed using a test certificate. Then use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package. For more information, see [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md).

## Submit apps to the Microsoft Store

Once an app is ready for release, developers need to submit and publish it to the Microsoft Store. For more information, see [Publish Windows apps and games](/windows/uwp/publish).

During app submission, developers need to set **Device family availability** and **Organizational licensing** options to make sure the app will be available to run on Surface Hub.

### To set device family availability

1. On the [Windows Dev Center](https://developer.microsoft.com/windows), navigate to your app submission page.
2. Select **Packages**.
3. Under **Device family availability**, select these options:

    - **Windows 10 Team**
    - **Let Microsoft decide whether to make the app available to any future device families**
  
   ![Image showing Device family availability page - part of Microsoft Store app submission process.](images/device-family.png)  

   For more information, see [Device family availability](/windows/uwp/publish/upload-app-packages#device-family-availability).

### To set organizational licensing

1. On the [Windows Dev Center](https://developer.microsoft.com/windows), navigate to your app submission page.

2. Select **Pricing and availability**.

3. Under Organizational licensing, select **Allow disconnected (offline) licensing for organizations**.

   ![Image showing Organizational licensing page - part of Microsoft Store app submission process.](images/sh-org-licensing.png)

   > [!NOTE]
   > **Make my app available to organizations with Store-managed (online) licensing and distribution** is selected by default.

   > [!NOTE]
   > Developers can also publish line-of-business apps directly to enterprises without making them broadly available in the Store. For more information, see [Distribute LOB apps to enterprises](/windows/uwp/publish/distribute-lob-apps-to-enterprises).

   For more information, see [Organizational licensing options](/windows/uwp/publish/organizational-licensing).

## Summary

There are a few different ways to install apps on your Surface Hub depending on whether you are developing apps, evaluating apps on a small number of devices, or deploying apps broadly to your organization. This table summarizes the supported methods:

| Install method             | Developing apps | Evaluating apps on <br> a few devices | Deploying apps broadly <br> to your organization |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| Visual Studio              | X |   |   |
| Provisioning package       | X | X |   |
| Microsoft Store app          |   | X |   |
| Supported MDM provider     |   |   | X |
