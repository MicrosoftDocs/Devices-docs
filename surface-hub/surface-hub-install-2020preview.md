---
title: "Install Windows 10 Team 2020 Update Preview Build"
description: "The latest update of the Surface Hub operating system, Windows 10 Team 2020 Update, is now available."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/07/2020
ms.localizationpriority: Medium
---
# Install Windows 10 Team 2020 Update Preview Build 

The latest update of the Surface Hub operating system, **Windows 10 Team 2020 Update**, is now available at no additional cost for the Surface Hub 50-inch and Surface Hub 2S 55-inch devices from the [Windows Insider Program](https://insider.windows.com). The Surface Hub 84-inch model will be supported in the final release of Windows 10 Team 2020 Update.

Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features. To learn more about what's new, see the following blog post: [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) For known issues, refer to the "Known issues" section below.
 
## Prerequisites

- Register with the [Windows Insider Program](https://insider.windows.com/).
- Download the Windows 10 Team 2020 Update Preview Build from the Windows Insider Program Fast Channel.
- After you install the Preview build, download the required firmware updates. Note: Firmware updates cannot be uninstalled even if you decide to leave the Windows Insider Program.

## Prepare your Surface Hub

Before you begin, check that your Surface Hub has the latest updates from Windows Update and make sure you save the BitLocker key associated with your device.

**To manually check for updates:**

1. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
2. Navigate to **Update & Security** > **Windows Update** and then select **Check for updates**.

For more information, see [Manage Windows updates on Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).

**To manually save your BitLocker key:**

1. Insert a USB drive into Surface Hub.
2. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
3. Navigate to **Update & Security** > **Recovery**.
4. Under **BitLocker**, select **Save**. The BitLocker key is saved to a text file on the USB drive.

For more information, see [Save your BitLocker key](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).
 
## Install the Windows 10 Team 2020 Update Preview Build

1. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
2. Navigate to **Privacy > Diagnostics & feedback** and **Full** for the Diagnostic data. 
3. Navigate to **Update & Security** > **Windows Insider Program** and then select **Get started**.
4. Follow the prompts to register as a Windows Insider using either your work account (recommended) or your personal Microsoft account. For details on the benefits of registering with your work account, see [Register for the Windows Insider Program for Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).
5. Under **Pick your Insider settings**, select **Fast**.
6. Allow the Surface Hub to automatically install the Preview Build and the required firmware updates over the next 3 to 4 days. The device will automatically download and install the updates during daily [maintenance windows](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window). For example:

- During the first maintenance window, Surface Hub starts downloading the Preview Build from Windows Update.
- During a second maintenance window, the device restarts to complete the update.
- During a third maintenance window, the device downloads and installs the required firmware updates.

> [!IMPORTANT]
> Microsoft recommends reserving the Surface Hub for 3-4 days to allow the device to finish installing the Preview Build and the required firmware updates. You may experience graphics, audio, and user interface issues if you use the device during this process.

### If you choose to manually install the Preview Build and required firmware updates:

1. After you've registered with the Windows Insider Program, go to **Settings** > **Update & Security** > **Windows Update** and select **Check for updates** to install the Preview Build.
2. Once the Preview Build installs (it may take up to 14 hours), select **Restart now** to complete the installation.
3. After the device restarts, go to **Settings** > **Update & Security** > **Windows Update**, and select **Check for updates to install required firmware updates**.
4. Once the firmware installs, select **Restart now**.

> [!WARNING]
> You may see graphics, audio, and user interface issues if you install the Preview Build without installing the required firmware updates.

> [!NOTE]
> If you choose to leave the Windows Insider Program and revert your Surface Hub to an older version of the operating system, you must first [reset your device](https://docs.microsoft.com/surface-hub/device-reset-surface-hub). Afterwards, you will need to go through the [first run program](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) to re-configure your device.
 
## Known issues: Windows 10 Team 2020 Update Preview Build

### Graphics, audio, and user interface issues 

You may experience various graphics and user interface issues if you install the Preview Build, but do not immediately install the required firmware updates afterward. Microsoft plans to fix these issues in the release build of Windows 10 Team 2020 Update.

### Resolved: Surface Hub 84-inch: graphics and user interface issues

This issue is resolved in Public Preview Build 19041.396.20200725-1700 and greater. Please ensure that you have taken all Windows Updates.

You may experience various graphics and user interface issues if you install the Preview Build on a first-generation Surface Hub 84-inch device. The Surface Hub 84-inch will be supported in the final release of Windows 10 Team 2020 Update.

### Sign in is impacted when Conditional Access policies are applied

- Sign in fails when attempting to sign into apps such as Microsoft Whiteboard. Users must first sign in from [My meetings and files](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) from the Start menu.

- Sign in fails if your user account is registered to a different Azure AD tenant than the one used by Surface Hub to Azure AD join.

Microsoft plans to fix these issues in the release build of Windows 10 Team 2020 Update.

### Windows Update prompts to install new drivers when none are available

When you go to **Settings** > **Update & Security** > **Windows Update** after you’ve installed Windows 10 Team 2020 Update and the required firmware updates, you may see the following error: 

- “A current driver on your PC may be better than the driver we’re trying to install. We’ll keep trying to install.” 

This error can be safely ignored. Microsoft is actively investigating this issue.

### Resolved: Unable to install Surface Hub policies using provisioning packages

This issue is resolved in Public Preview Build 19041.396.20200725-1700 and greater. Please ensure that you have taken all Windows Updates.

Provisioning packages that use policies from the Surface Hub Configuration Service Provider (CSP) fail to install. For now, use Microsoft Intune or another mobile device management (MDM) provider to apply Surface Hub policies. Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.

### Prompt to remove USB drive prematurely during first run

When using a provisioning package to setup Surface Hub during first run, you’re prompted to remove the USB drive before the device is able to read the Surface Hub configuration file. Ignore the message if you’re using a configure file to setup your device account. Microsoft is actively investigating this issue.
 
### Resolved: Unable to set up proxy settings during first run

This issue is resolved in Public Preview Build 19041.396.20200725-1700 and greater. Please ensure that you have taken all Windows Updates.

If you use a proxy to connect to the Internet, you may have limited Internet connectivity during the first run program. Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.
 
### An error appears when you download apps from Microsoft Store

To download an app from the Microsoft Store, you will see a prompt to sign in. A known issue causes an error to appear during sign-in, but this doesn't affect your ability to download apps. Microsoft is actively investigating this issue.

### Surface Hub 2S intermittently loses Wi-Fi connection

Try unplugging your device and plugging it back in, or using an Ethernet cable to connect to the Internet. Microsoft is actively investigating this issue.

### Surface Hub 2S intermittently fails to resume from sleep

Surface Hub 2S may intermittently fail to fully resume from sleep and appear to stop responding on a screen showing the Microsoft logo. Try unplugging your device and plugging it back in. 

To prevent this issue:

1. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
2. Navigate to **Surface Hub** > **Session & power**. 
3. Under **When the device goes to sleep, use this power setting**, select **Connected Standby.**
4. Under **When no one is present, put the device to sleep after**, select **Never.**

Microsoft plans to fix this issue in a firmware update prior to the final release of Windows 10 Team 2020 Update.

### Projection issues when the Connect app is not in view

- When you use a cable to project to Surface Hub, touchback stops working if you navigate away from the Connect app.
- When you project to Surface Hub using Miracast, the wireless connection drops soon after you navigate away from the Connect app.

Microsoft is actively investigating these issues.

### Skype for Business isn't using proxy for media traffic

For some devices that use a proxy, Skype for Business can sign in, but will not use the proxy server for media traffic. Microsoft is actively investigating this issue.

We invite you to share your insights and suggestions with Microsoft Support.

## Learn more

- [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [Getting started with the Windows Insider Program for Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)