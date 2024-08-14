---
title: Install apps on Surface Hub
description: Learn how to install and manage apps on Surface Hub devices using WinGet, the Microsoft Store, and other deployment methods. Ideal for IT admins and developers managing Surface Hub 2S or Surface Hub 3 in an enterprise environment.
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: dpandre
manager: frankbu
ms.service: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 08/14/2024
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
- Surface Hub 3

---

# Install apps on Surface Hub

You can install more apps on your Surface Hub to fit your team or organization's needs. There are different methods for installing apps depending on whether you're developing and testing an app, or deploying a released app.

## Supported app guidelines

- Surface Hub only runs [UWP apps](/windows/uwp/get-started/universal-application-platform-guide). Apps created using the [MSIX Packaging Tool](/windows/msix/packaging-tool/tool-overview) do not run on Surface Hub.
- Surface Hub only supports offline-licensed apps.
- Apps must be targeted for the [Universal device family](/windows/apps/publish/publish-your-app/device-families) or Windows Team device family.
- By default, apps must be signed to be installed. During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.
- You need admin credentials to install apps on your Surface Hub.

## Use WinGet

WinGet, also known as the Windows Package Manager, is a powerful command-line tool developed by Microsoft that simplifies the process of discovering, installing, updating, and managing software on Windows devices, including Surface Hub. With the retirement of the Microsoft Store for Business, WinGet offers organizations a more flexible and efficient way to manage applications on Surface Hub and other devices. With WinGet, IT admins can browse the repository of available applications, install necessary software, and automate some app management tasks. This transition ensures continuity in software deployment while providing enhanced control and customization for enterprise environments.

### Install WinGet

1. By default, WinGet is preinstalled on Windows 10 (version 1809 and later) and Windows 11. To confirm you have WinGet installed, open a command prompt and enter **winget**.
2. Ensure you're running WinGet 1.8 or later.
3. If WinGet isn't present or you need the latest version, follow these instructions: [Install WinGet](/windows/package-manager/winget/#install-winget).

### Browse apps for Surface Hub

Find compatible apps with keywords related to Surface Hub or by filtering for Universal Windows Platform (UWP) apps.

Use the following command in the command prompt:

```shell
winget search --tag "Surface Hub"
```

This command searches for apps tagged with "Surface Hub," indicating they're optimized for Surface Hub devices.

#### Filter for UWP apps

If you're looking for UWP apps that are compatible with Surface Hub, you can filter your search with a command like this:

```shell
winget search --source msstore --query uwp
```

This shows UWP apps from the Microsoft Store, many of which can run on Surface Hub.

#### Browse by specific app name or category

If you have an idea of the type of app you're looking for, such as collaboration tools or specific software by name, you can search more directly:

```shell
winget search "collaboration"
```

Or

```shell
winget search "Microsoft Whiteboard"
```

#### View app details

Once you find an app that interests you, you can view more details to confirm compatibility or learn more about the app:

```shell
winget show <app-id>
```

For example:

```shell
winget show Microsoft.Whiteboard
```

This command provides detailed information about the app, including its description, version, and whether it’s compatible with devices like Surface Hub.

### Example scenario: Download app files for Enterprise distribution

In this scenario, use WinGet to download an app package for Surface Hub.

1. **Enter the following command:**

    Replace `<app-id>` with the specific ID of the app you want to download. 

    ```bash
    winget download <app-id> --platform windows.universal -a x64 --skip-license
    ```

    Example command:

    ```bash
    winget download 9WZDNCRFHVJL --platform windows.universal -a x64 --skip-license
    ```

2. **Agree to the terms:**

    If prompted, agree to the terms as part of the download process. 

     :::image type="content" alt-text="Screenshot of app download via WinGet." source="images/download-app-winget-example.png":::


3. **View the downloaded files:**

    After the download completes, the files are saved in a new subdirectory within your Downloads folder. This folder contains the app package and any necessary dependency files.

4. Deploy the app via a [provisioning package](#create-provisioning-package) or your [MDM provider](#supported-mdm-provider). 

#### WinGet command parameters

- **9WZDNCRFHVJL**: The Microsoft Store app ID; in this example, Microsoft OneNote.
- **platform windows.universal**: Refers to the Universal Windows Platform (UWP), which means the package is designed to run on multiple Windows devices, including Surface Hub, PCs, tablets, and other devices that support UWP.
- **-a x64**: Specifies the architecture of the package, compatible with 64-bit Windows systems.
- **--skip-license**: Bypasses the requirement to accept the license agreement before downloading the package. By using this flag, you're automatically accepting the license terms without being prompted during the download process.

## Microsoft Store app

To evaluate apps on an individual Surface Hub, you can use the Microsoft Store app on Surface Hub to browse and download apps.

> [!NOTE]
> Using the Microsoft Store app is not the recommended method of deploying apps at scale to your organization. In an enterprise enviroment with multiple Surface Hubs, deploy apps with a [provisioning package](#install-offline-licensed-apps-via-provisioning-package) or via an [MDM provider](#supported-mdm-provider), such as Microsoft Intune.
>
> - To download apps, you must sign in to the Microsoft Store app with a Microsoft account or organizational account. However, you can only connect an account to a maximum of 10 devices at once. If you have more than 10 Surface Hubs, you will need to create multiple accounts or remove devices from your account between app installations.
> - To install apps, you will need to manually sign in to the Microsoft Store app on each Surface Hub you own.

#### To browse the Microsoft Store on Surface Hub

1. From your Surface Hub, start **Settings**.
2. Enter device admin credentials when prompted.
3. Navigate to **Surface Hub** > **Apps & features**.
4. Select **Open Store** and search for the app you're looking for.

### Install offline-licensed apps via provisioning package

You can manually install offline-licensed apps on Surface Hubs using provisioning packages. Use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package and *unencoded* license file that you downloaded via WinGet. For more information, see [Create provisioning packages for Surface Hub](provisioning-packages-for-certificates-surface-hub.md).

### Supported MDM provider

To deploy apps to a large number of Surface Hubs in your organization, use a supported MDM provider. The table below shows which MDM providers support deploying offline-licensed app packages.

| MDM provider                | Supports offline-licensed app packages |
|-----------------------------|----------------------------------------|
| On-premises MDM with Configuration Manager (beginning in version 1602) | Yes |
| Third-party MDM provider    | Check to make sure your MDM provider supports deploying offline-licensed app packages. |

> [!NOTE]
> To deploy offline apps remotely using Intune, refer to [Add a Windows line-of-business app to Microsoft Intune](/mem/intune/apps/lob-apps-windows). Surface Hub app deployment only supports offline apps that are assigned to a Device group and use the Device license type.

## Develop and test apps

This section provides information for app developers for testing apps on Surface Hub.

### Developer Mode

By default, Surface Hub only runs UWP apps published to and signed by the Microsoft Store. Apps submitted to the Microsoft Store go through security and compliance tests as part of the [app certification process](/windows/uwp/publish/the-app-certification-process), so this helps safeguard your Surface Hub against malicious apps. By enabling developer mode, you can also install developer-signed UWP apps.

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

Use Visual Studio to create an app package for your UWP app, signed using a test certificate. Then use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package. For more information, see [Create provisioning packages for Surface Hub](provisioning-packages-for-certificates-surface-hub.md).

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

   > [!TIP]
   > Developers can also publish line-of-business apps directly to enterprises without making them broadly available in the Store. For more information, see [Distribute LOB apps to enterprises](/windows/uwp/publish/distribute-lob-apps-to-enterprises).

   For more information, see [Organizational licensing options](/windows/uwp/publish/organizational-licensing).

## Summary

There are a few different ways to install apps on your Surface Hub depending on whether you're developing apps, evaluating apps on a few devices, or deploying apps broadly to your organization. This table summarizes the supported methods:

| Install method             | Developing apps | Evaluating apps on a few devices | Deploying apps broadly to your organization |
| -------------------------- | --------------- | -------------------------------- | ------------------------------------------ |
| Visual Studio              | X               |                                  |                                            |
| Provisioning package       | X               | X                                |                                            |
| Microsoft Store app        |                 | X                                |                                            |
| Supported MDM provider     |                 |                                  | X                                          |
