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
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
---

# Install and configure the new Microsoft Edge on Surface Hub

Windows 10 Team 2020 Update supports the new Microsoft Edge based on Chromium (version 85 and above) as the recommended browser for Surface Hub 2S and Surface Hub (v1). This article explains how to install the browser using one of three methods: a provisioning package, Microsoft Intune, or third party Mobile Device Management (MDM) provider.

> [!IMPORTANT]
> By default, Surface Hub devices are preinstalled with Microsoft Edge Legacy (version 44). After installing the [2020 Update](surface-hub-2020-update.md), it's recommended to switch to the new Microsoft Edge browser; support for [Microsoft Edge Legacy](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) will end on March 9, 2021.

> [!NOTE]
> The swipe down from top of screen gesture to exit full-screen mode requires two fingers with the new Microsoft Edge. The exit full-screen action is also available in the context menu displayed after a long-press touch.


## Install Microsoft Edge using a provisioning package

1. From a PC, download the [Microsoft Edge provisioning package](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) to the root folder of a USB drive.
2. Insert the USB drive into Surface Hub.
3. From Surface Hub, open **Settings** and enter your admin credentials when prompted.
4. Navigate to **Surface Hub** > **Device management**. Under **Provisioning packages**, select **Add or remove a provisioning package**.
5. Select **Add a package**.
6. Choose the Microsoft Edge provisioning package and select **Add**.
7. You will see a summary of the changes that the provisioning package applies. Select **Yes, add it**.
8. Wait for the Microsoft Edge installation to complete. Once it's installed, navigate to the Surface Hub Start menu to access the new Microsoft Edge.              

> [!NOTE]
> If there’s a newer version of Microsoft Edge available, it will be automatically updated.
 
## Install Microsoft Edge using Intune
 
> [!NOTE]
> To make use of this installation method, the Surface Hub device must be enrolled into and managed using Intune. For more information, see [Manage Surface Hub 2S with MDM](https://docs.microsoft.com/surface-hub/manage-settings-with-mdm-for-surface-hub).
 

1. [Download the Microsoft Edge installer](https://www.microsoft.com/edge/business/download).
    - Use the current version from [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(version 85)**
    - Choose **Windows 64-bit**
2. [Add the Microsoft Edge installer as a line-of-business app to Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows).
    - If you choose to use Microsoft Edge Update to handle automatic updates to Microsoft Edge, be sure to configure the **Ignore app version** setting the **App information** pane. When you switch this setting to **Yes**, Microsoft Intune will not enforce the app version that's installed on the Surface Hub device.

## Install Microsoft Edge using third party MDM provider

1. [Download the Microsoft Edge installer from Microsoft](https://www.microsoft.com/edge/business/download).
    - Use the current version from [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels) **(version 85)**
    - Choose **Windows 64-bit**
2. Stage the Microsoft Edge installer on a hosted location, such as a local file share (\\server\share\MicrosoftEdgeEnterpriseX64.msi). The Surface Hub device must have permission to access the hosted location.
3. Use [EnterpriseDesktopAppManagement Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) through your MDM provider to install Microsoft Edge.

## Configure Microsoft Edge

### Default Microsoft Edge policies for Surface Hub

Microsoft Edge is preconfigured with the following policy setttings to provide an optimized experience for Surface Hub.
 
> [!TIP]
> It's recommended to retain the default value for these policy settings.
 

| Policy setting                                                                                                   | Recommended experience                                                                                                                                                                                                                                               | Default value |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Do not automatically import datatypes and settings from Microsoft Edge Legacy. This avoids changing signed-in users' profiles with shared settings from the Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Allow Microsoft Edge processes to keep running in the background even after the last browser window is closed, enabling faster access to web apps during a session.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Do not allow users to create new profiles in Microsoft Edge. This simplifies the browsing and signed-in experience.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Enables only one user to sign-in to Microsoft Edge. This simplifies the browsing and signed-in experience                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | Enables users to enjoy Single Sign-On (SSO) in Microsoft Edge. When a user is signed into Surface Hub, their credentials can flow to supported websites without requiring them to re-authenticate.  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Prevents non-admin users from installing new extensions in Microsoft Edge. To configure a list of extensions to be installed by default, use [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Hides the first run experience and splash screen that's normally shown when users run Microsoft Edge for the first time. Since Surface Hub is a shared device, this simplifies the user experience.                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Disables InPrivate mode. Since End Session already clears browsing data, this simplifies the browsing and signed-in experience.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Shows the Office 365 feed experience on new tab pages. When a user is signed into Surface Hub, this enables fast access to their files and content on Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | When a user is signed into Surface Hub, a non-removable profile will be created using their organizational account. This simplifies the Single Sign-On (SSO) experience.                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | Disables printing in Microsoft Edge. Surface Hub does not support printing.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Enables Microsoft Edge to proactively authenticate signed-in users with Microsoft services. This simplifies the Single Sign-On (SSO) experience.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Automatically saves files to the Downloads folder, rather than asking users where to save the file. This simplifies the browsing experience.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Deployable progressive web apps (PWAs) are not currently supported on the Windows 10 Team operating system.  Note also that the Microsoft Edge policy setting [WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) is not supported on Surface Hub. 

### Configure Microsoft Edge policy settings

Use [Microsoft Edge browser policies](https://docs.microsoft.com/deployedge/microsoft-edge-policies) to configure browser settings in Microsoft Edge. These policies can be applied using:

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune),
- [Your preferred Mobile Device Management (MDM) provider that supports ADMX Ingestion](https://docs.microsoft.com/deployedge/configure-edge-with-mdm), or
- [Provisioning packages using ADMX Ingestion in Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion).

 
### Configure Microsoft Edge updates

By default, Microsoft Edge is updated automatically. Use [Microsoft Edge update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) to configure settings for Microsoft Edge Update.
Note that Surface Hub does not support the following Microsoft Edge update policies:

- **Allowsxs** – On Surface Hub, Microsoft Edge Stable channel always replaces Microsoft Edge Legacy.
- **CreateDesktopShortcut** – Surface Hub does not use desktop shortcuts.

> [!TIP]
>  Microsoft Edge requires connectivity to the Internet to support its features. Ensure that the [necessary domain URLs](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) are added to the Allow list to ensure communications through firewalls and other security mechanisms.

## Related links

- [Microsoft Edge documentation](https://docs.microsoft.com/microsoft-edge/)

