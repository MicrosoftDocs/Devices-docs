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
ms.date: 07/15/2020
ms.localizationpriority: Medium
---
# Install Windows 10 Team 2020 Update Preview Build 

The latest update of the Surface Hub operating system, **Windows 10 Team 2020 Update**, is now available at no additional cost for the Surface Hub 50-inch and Surface Hub 2S 55-inch devices from the [Windows Insider Program](https://insider.windows.com). The Surface Hub 84-inch model will be supported in the final release of Windows 10 Team 2020 Update.

Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features. To learn more about what's new, see the following blog post: [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/bg-p/SurfaceITPro) For known issues, refer to the "Known issues" section below.
 
## Prerequisites

- Register with the [Windows Insider Program](https://insider.windows.com/).
- Download the Windows 10 Team 2020 Update Preview Build from the Windows Insider Program Fast Channel.
- Preview build includes a required firmware update that cannot be uninstalled, even if you decide to leave the Windows Insider Program.

## Prepare your Surface Hub

Before you begin, check that your Surface Hub has the latest updates from Windows Update and make sure you save the BitLocker key associated with your device.

**To manually check for updates:**

1. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
2. Navigate to **Update & Security** > **Windows Update** and then select **Check for updates**.

For more information, see [Manage Windows updates on Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).

**To manually save your BitLocker key:**

1. Insert a USB drive into the Surface Hub.
2. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
3. Navigate to **Update & Security** > **Recovery**.
4. Under **BitLocker**, select **Save**. The BitLocker key is saved to a text file on the USB drive.

For more information, see [Save your BitLocker key](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).
 
## Install the Windows 10 Team 2020 Update Preview Build

1. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
2. Navigate to **Update & Security** > **Windows Insider Program** and then select **Get started**.
3. Follow the prompts to register as a Windows Insider using either your work account (recommended) or your personal Microsoft account. For details on the benefits of registering with your work account, see [Register for the Windows Insider Program for Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).
4. Under **Pick your Insider settings**, select **Fast**.
5. From **Settings**, navigate to **Update & Security** > **Windows Update**. Select **Check for updates** to download the Windows 10 Team 2020 Update Preview Build.
6. When your Surface Hub installs the update, select **Restart now** to complete the update. Otherwise, the device will automatically restart during its regular [maintenance window](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window).

> [!NOTE]
> If you choose to leave the Windows Insider Program and revert your Surface Hub to an older version of the operating system, you must first [reset your device](https://docs.microsoft.com/surface-hub/device-reset-surface-hub). Afterwards, you will need to go through the [first run program](https://docs.microsoft.com/en-us/surface-hub/first-run-program-surface-hub) to re-configure your device.
 
## Known issues: Windows 10 Team 2020 Update Preview Build

**Sign in is impacted when Conditional Access policies are applied**

- Sign in is limited to accessing your [meetings and recent files](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) from the Start menu but fails when attempting to sign into apps such as Microsoft Whiteboard.
- Sign in fails if your user account is registered to a different Azure AD tenant than the one used by Surface Hub to Azure AD join.

Microsoft plans to fix these issues in the release build of Windows 10 Team 2020 Update.

**Can't install Surface Hub policies using provisioning packages**
Provisioning packages that use policies from the Surface Hub Configuration Service Provider (CSP) fail to install. For now, use Microsoft Intune or another mobile device management (MDM) provider to apply Surface Hub policies. Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.
 
**Can’t setup proxy settings during first run**
If you use a proxy to connect to the Internet, you may have limited Internet connectivity during the first run program. Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.
 
**An error appears when you download apps from Microsoft Store**
To download an app from the Microsoft Store, you will see a prompt to sign in. A known issue causes an error to appear during sign-in, but this doesn't affect your ability to download apps. Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.

**Surface Hub 2S intermittently fails to resume from hibernate**
Surface Hub 2S may intermittently fail to fully resume from hibernate and appear to stop responding on a screen showing the Microsoft logo. Try unplugging your device and plugging it back in. 

To prevent this issue:

1. On Surface Hub, open **Settings** and enter your admin credentials when prompted.
2. Navigate to **Surface Hub** > **Session & power**. Under **When the device goes to sleep, use this power setting**, select **Connected Standby (wakes up faster)**.

Microsoft plans to fix this issue in a firmware update prior to the final release of Windows 10 Team 2020 Update.

**Skype for Business isn't using proxy for media traffic**
For some devices that use a proxy, Skype for Business can sign in, but won't use the proxy server for media traffic. Microsoft is actively investigating this issue.

**Device doesn't apply settings to disable wireless projection**
The following projection settings (located in **Settings** > **Surface** **Hub** > **Projection**) don’t work:

- Open Connect automatically when someone projects
- Presenters can use Miracast to project wirelessly to this device

Microsoft plans to fix this issue in the final build of Windows 10 Team 2020 Update.
 
We invite you to share your insights and suggestions with Microsoft Support.

## Learn more

- [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/bg-p/SurfaceITPro)
- [Getting started with the Windows Insider Program for Business] (https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)