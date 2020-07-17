---
title: "Install and configure the new Microsoft Edge on Surface Hub"
description: "Install and configure the new Microsoft Edge on Surface Hub."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/20/2020
ms.localizationpriority: Medium
---

# Install and configure the new Microsoft Edge on Surface Hub

Windows 10 Team 2020 Update supports the new Microsoft Edge based on Chromium (version 85 and above) as the recommended browser for Surface Hub. You can install the new Microsoft Edge manually using a provisioning package, remotely using Microsoft Intune or your preferred Mobile Device Management (MDM) provider. By default, Surface Hub devices are preinstalled with Microsoft Edge Legacy (version 44).

> [!NOTE]
> Surface Hub requires version 85 or later of the new Microsoft Edge, with availability limited to the “[Dev channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels),” designed to give IT admins an early look at upcoming Edge functionality and prepare for the next Beta release.  Support for the Dev channel is temporarily enabled for Windows Insiders to preview the new Microsoft Edge. (Normally, Surface Hub supports only versions released to the “Stable channel.”) For more information, see [Microsoft Edge channel overview.](https://docs.microsoft.com/deployedge/microsoft-edge-channels)
 
Note the following configuration details if you choose to install the new Microsoft Edge:
 
- By design, Microsoft Edge Dev channel installs side-by-side with Microsoft Edge Legacy, so users will see both “Microsoft Edge Dev” (version 85) and “Microsoft Edge” (version 44) in the Surface Hub Start menu. In contrast, Microsoft Edge Stable channel will replace Microsoft Edge Legacy as the default browser.
- Once installed, Microsoft Edge Dev channel will not automatically appear as a pinned app. To open, select  **Start** > **All Apps**. In contrast, Microsoft Edge Stable channel automatically replaces Microsoft Edge Legacy as a pinned app in the All Apps list.
- Once version 85 is promoted to Stable channel, Microsoft Edge Dev channel will automatically disappear from the Start menu, and you will be required to install Microsoft Edge Stable channel on your Surface Hub.

> [!NOTE]
>  A device reset is required to remove the new Microsoft Edge. See [Reset or recover a Surface Hub](https://docs.microsoft.com/surface-hub/device-reset-surface-hub) for more information.
 
## Install Microsoft Edge using a provisioning package

1. From a PC, download the Microsoft Edge provisioning package <add link to provisioning package> to the root folder of a USB drive.
2. Insert the USB drive into the Surface Hub.
3. From the Surface Hub, open **Settings** and enter your admin credentials when prompted.
4. Navigate to **Surface Hub** > **Device management**. Under **Provisioning packages**, select **Add or remove a provisioning package**.
5. Select **Add a package**.
6. Choose the Microsoft Edge provisioning package and select **Add**.
7. You'll see a summary of the changes that the provisioning package will apply. Select **Yes, add it**.
8. Wait for the Microsoft Edge installation to complete. Once it’s installed, navigate to the Surface Hub Start menu to access the new Microsoft Edge.

 
> [!NOTE]
> If there’s a newer version of Microsoft Edge available, it will be automatically updated.
 
## Install Microsoft Edge using Intune

The Surface Hub device must be enrolled into and managed using Intune. For more information, see [Manage Surface Hub 2S with Microsoft Intune](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune).
 

1. [Download the Microsoft Edge installer from Microsoft](https://www.microsoft.com/edge/business/download).
    - Use the current version from [Dev channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(version 85)**.
    - Choose **Windows 64-bit**.
2. [Add the Microsoft Edge installer as a line-of-business app to Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows).
    - If you choose to use Microsoft Edge Update to handle automatic updates to Microsoft Edge, be sure to configure the **Ignore app version** setting the **App information** pane. When you switch this setting to **Yes**, Microsoft Intune will not enforce the app version that’s installed on the Surface Hub device.

## Install Microsoft Edge using Mobile Device Management

1. [Download the Microsoft Edge installer from Microsoft](https://www.microsoft.com/edge/business/download).
    - Use the current version from [Dev channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(version 85).**
    - Choose **Windows 64-bit.**
2. Stage the Microsoft Edge installer on a hosted location, such as a local file share. The Surface Hub device must have permission to access the hosted location.
3. Use [EnterpriseModernAppManagement Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management) through your MDM provider to install Microsoft Edge.

 
## Configure Microsoft Edge


### Default Microsoft Edge policies for Surface Hub

Microsoft Edge is preconfigured with the following default policy settings to provide an optimized experience for Surface Hub.
It's recommend to keep the default value for these policies.

| **Microsoft Edge policy**                                                                                                    | **Recommended experience**                                                                                                                                                                                                                                               | **Default value** |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Do not automatically import datatypes and settings from Microsoft Edge Legacy. This avoids changing signed-in users’ profiles with shared settings from the Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Allow Microsoft Edge processes to keep running in the background even after the last browser window is closed, enabling faster access to web apps during a session.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Do not allow users to create new profiles in Microsoft Edge. This simplifies the browsing and signed-in experience.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Enables only one user to sign-in to Microsoft Edge. This simplifies the browsing and signed-in experience                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Enables users to enjoy Single Sign-On (SSO) in Microsoft Edge. When a user is signed into Surface Hub, their credentials can flow to supported websites without requiring them to re-authenticate. Ensure that Enterprise State Roaming is also enabled in your tenant.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Prevents non-admin users from installing new extensions in Microsoft Edge. To configure a list of extensions to be installed by default, use [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Hides the first run experience and splash screen that’s normally shown when users run Microsoft Edge for the first time. Since Surface Hub is a shared device, this simplifies the user experience.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Disables InPrivate mode. Since End Session already clears browsing data, this simplifies the browsing and signed-in experience.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Shows the Office 365 feed experience on new tab pages. When a user is signed into Surface Hub, this enables fast access to their files and content on Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | When a user is signed into Surface Hub, a non-removable profile will be created using their organizational account. This simplifies the Single Sign-On (SSO) experience.                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Disables printing in Microsoft Edge. Surface Hub does not support printing.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Enables Microsoft Edge to proactively authenticate signed-in users with Microsoft services. This simplifies the Single Sign-On (SSO) experience.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Automatically saves files to the Downloads folder, rather than asking users where to save the file. This simplifies the browsing experience.                                                                                                                             | 0                 |

## Configure Microsoft Edge policy settings

Use [Microsoft Edge browser policy settings](https://docs.microsoft.com/deployedge/microsoft-edge-policies) to configure browser settings in Microsoft Edge. These policy settings can be applied using one of the following options:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Your preferred Mobile Device Management (MDM) provider that supports ADMX Ingestion](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)
- [Provisioning packages using ADMX Ingestion in Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

## Configure Microsoft Edge updates

By default, Microsoft Edge is updated automatically. Use [Microsoft Edge update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) to configure settings for Microsoft Edge Update.
Note that Surface Hub does not support the following Microsoft Edge update policy settings:

- **Allowsxs** – On Surface Hub, Microsoft Edge Stable channel always replaces Microsoft Edge Legacy.
- **CreateDesktopShortcut** – Surface Hub does not use desktop shortcuts.

 
> [!NOTE]
>  Microsoft Edge requires connectivity to the Internet to support its features. Ensure that the [necessary domain URLs](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) are added to the Allow list to ensure communications through firewalls and other security mechanisms.
 
## Display Microsoft Edge in the Surface Hub Start menu

Microsoft Edge Stable channel is automatically pinned to the Surface Hub Start menu once it’s installed. If you want to apply a customized Start menu layout, use the following XML to add a pinned tile for Microsoft Edge.

**Important:** The new Microsoft Edge doesn’t support pinned websites and links using SecondaryTiles.
 
    ```html
    <start:DesktopApplicationTile
    DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe"
    Size="2x2"
    Row="0"
    Column="0"/>
    ```

For more information, see [Configure Surface Hub Start menu](https://docs.microsoft.com/surface-hub/surface-hub-start-menu).
 

## Related links

More information on Microsoft Edge documentation is available [here](https://docs.microsoft.com/microsoft-edge/).


 
 

