---
title: "Manage Microsoft Edge on Surface Hub"
description: "This article describes default Microsoft Edge policy settings and tools to configure browser settings."
ms.prod: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: how-to
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
> The swipe down from top of screen gesture to exit full-screen mode requires two fingers with Microsoft Edge. The exit full-screen action is also available in the context menu displayed after a long-press touch.

## Default Microsoft Edge policies for Surface Hub

Microsoft Edge is preconfigured with the following policy settings to provide an optimized experience for Surface Hub.

> [!TIP]
> It's recommended to retain the default value for these policy settings.

| Policy setting                                                                                                   | Recommended experience                                                                                                                                                                                                                                               | Default value |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | Don't automatically import datatypes and settings from Microsoft Edge Legacy. This configuration avoids changing signed-in users' profiles with shared settings from the Surface Hub.                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | Allow Microsoft Edge processes to keep running in the background even after the last browser window is closed, enabling faster access to web apps during a session.                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | Don't allow users to create new profiles in Microsoft Edge, simplifying the browsing and signed-in experience.                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | Enables only one user to sign-in to Microsoft Edge, simplifying the browsing and signed-in experience                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | Enables users to enjoy single sign-on (SSO) in Microsoft Edge. When users are signed into Surface Hub, their credentials can flow to supported websites without requiring them to reauthenticate.  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | Prevents non-admin users from installing new extensions in Microsoft Edge. To configure a list of extensions to be installed by default, use [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist). | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | Hides the first run experience and splash screen that's normally shown when users run Microsoft Edge for the first time.                                                                       | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | Disables InPrivate mode. Since End Session already clears browsing data, disabling InPrivate mode simplifies the browsing and signed-in experience.                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | Shows the Microsoft 365 feed experience on new tab pages. When users are signed into Surface Hub, this tab display enables fast access to files and content on Microsoft 365.                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | When users are signed into Surface Hub, a non-removable profile is created using their organizational account, simplifying the SSO experience.                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | Disables printing in Microsoft Edge. Surface Hub doesn't support printing.                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | Enables Microsoft Edge to proactively authenticate signed-in users with Microsoft services, simplifying the SSO  experience.                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | Automatically saves files to the Downloads folder, rather than asking users where to save the file, simplifying the browsing experience.                                                                                                                             | 0                 |

> [!TIP]
> Deployable progressive web apps (PWAs) are now supported on the Windows 10 Team operating system. To learn more, see [Install Progressive Web Apps on Surface Hub](install-pwa-surface-hub.md). 

### Configure Microsoft Edge updates

By default, Microsoft Edge is updated automatically. Use [Microsoft Edge update policies](/deployedge/microsoft-edge-update-policies) to configure settings for Microsoft Edge Update. Surface Hub doesn't support the **CreateDesktopShortcut** policy setting as Surface Hub doesn't use desktop shortcuts.

> [!TIP]
> Microsoft Edge requires connectivity to the Internet to support its features. Add the [necessary domain URLs](/deployedge/microsoft-edge-security-endpoints) to the Allow list to ensure communications through firewalls and other security mechanisms.

## Related links

- [Microsoft Edge documentation](/microsoft-edge/)