---
title: "Manage Microsoft Edge on Surface Hub"
description: "This article describes default Microsoft Edge policy settings and tools to configure browser settings."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
---

# Manage Microsoft Edge on Surface Hub

Use [Microsoft Edge browser policies](/deployedge/microsoft-edge-policies) to configure browser settings in Microsoft Edge via any of the following methods:

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Your preferred Mobile Device Management (MDM) provider that supports ADMX Ingestion](/deployedge/configure-edge-with-mdm)
- [Provisioning packages using ADMX Ingestion in Windows Configuration Designer](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> The swipe down from top of screen gesture to exit full-screen mode requires two fingers with the new Microsoft Edge. The exit full-screen action is also available in the context menu displayed after a long-press touch.

## Default Microsoft Edge policies for Surface Hub

Microsoft Edge is preconfigured with the following policy setttings to provide an optimized experience for Surface Hub.


> [!TIP]
> It's recommended to retain the default value for these policy settings.

| Policy setting                                                                                                   | Recommended experience                                                                                                                                                                                                                                               | Default value |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Do not automatically import datatypes and settings from Microsoft Edge Legacy. This avoids changing signed-in users' profiles with shared settings from the Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Allow Microsoft Edge processes to keep running in the background even after the last browser window is closed, enabling faster access to web apps during a session.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Do not allow users to create new profiles in Microsoft Edge. This simplifies the browsing and signed-in experience.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Enables only one user to sign-in to Microsoft Edge. This simplifies the browsing and signed-in experience                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | Enables users to enjoy Single Sign-On (SSO) in Microsoft Edge. When a user is signed into Surface Hub, their credentials can flow to supported websites without requiring them to re-authenticate.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Prevents non-admin users from installing new extensions in Microsoft Edge. To configure a list of extensions to be installed by default, use [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Hides the first run experience and splash screen that's normally shown when users run Microsoft Edge for the first time. Since Surface Hub is a shared device, this simplifies the user experience.                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Disables InPrivate mode. Since End Session already clears browsing data, this simplifies the browsing and signed-in experience.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Shows the Office 365 feed experience on new tab pages. When a user is signed into Surface Hub, this enables fast access to their files and content on Office 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | When a user is signed into Surface Hub, a non-removable profile will be created using their organizational account. This simplifies the Single Sign-On (SSO) experience.                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | Disables printing in Microsoft Edge. Surface Hub does not support printing.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Enables Microsoft Edge to proactively authenticate signed-in users with Microsoft services. This simplifies the Single Sign-On (SSO) experience.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Automatically saves files to the Downloads folder, rather than asking users where to save the file. This simplifies the browsing experience.                                                                                                                             | 0                 |

> [!IMPORTANT]
> Deployable progressive web apps (PWAs) are not currently supported on the Windows 10 Team operating system.  Note also that the Microsoft Edge policy setting [WebAppInstallForceList](/deployedge/microsoft-edge-policies#webappinstallforcelist) is not supported on Surface Hub.

### Configure Microsoft Edge updates

By default, Microsoft Edge is updated automatically. Use [Microsoft Edge update policies](/deployedge/microsoft-edge-update-policies) to configure settings for Microsoft Edge Update. Note that Surface Hub does not support the **CreateDesktopShortcut** policy setting as Surface Hub does not use desktop shortcuts.

> [!TIP]
> Microsoft Edge requires connectivity to the Internet to support its features. Add the [necessary domain URLs](/deployedge/microsoft-edge-security-endpoints) to the Allow list to ensure communications through firewalls and other security mechanisms.

## Related links

- [Microsoft Edge documentation](/microsoft-edge/)