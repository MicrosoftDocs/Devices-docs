---
title: Operating system essentials for Surface Hub
description: This article explains unique aspects of the Windows Team operating system on Surface Hub and how it differs from Windows 10 or Windows 11 Enterprise.
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 02/15/2022
manager: frankbu
ms.localizationpriority: medium
appliesto:
- Surface Hub 
- Surface Hub 2S
---

# Operating system essentials for Surface Hub

The Surface Hub operating system, Windows 10 Team, originated with Windows 10 Enterprise, providing rich support for enterprise management, security, and other features. However, there are important differences between them. While the Enterprise edition is designed for PCs, Windows 10 Team is designed from the ground up for large screens and meeting rooms. When you evaluate security and management requirements for Surface Hub, it's recommended to consider it as a new operating system. This article highlights the key differences between Windows 10 Team on Surface Hub and enterprise versions of Windows 10 or Windows 11.

## Convert Surface Hub to run Pro or Enterprise desktop

You can change the OS on Surface Hub 2S by migrating to Windows 10 or Windows 11 Pro/Enterprise. To learn more, see the following resources:

- [Announcing the availability of Windows 10 Pro and Enterprise on Surface Hub 2](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107).

- [Migrate to Windows 10 or Windows 11 Pro or Enterprise on Surface Hub 2](surface-hub-2s-migrate-os.md)

## User interface

### Shell (OS user interface)

The Surface Hub's shell is designed from the ground up to be large screen and touch optimized. It doesn't use the same shell as Windows 10 or Windows 11 Enterprise.

*Potential impact on organization policies:*

- Settings related to controls in the Windows 10 or Windows 11 Enterprise shell don't apply for Surface Hub.

### Lock screen and screensaver

Surface Hub doesn't have a lock screen or a screen saver, but it has a similar feature called the welcome screen. The welcome screen shows scheduled meetings from the device account's calendar, and easy entry points to the Surface Hub's top apps - Skype for Business, Whiteboard, and Connect.

*Potential impact on organization policies:*

- Settings for lock screen, screen timeout, and screen saver don't apply for Surface Hub.

### User sign-in

Unlike Windows PCs, anyone can walk up and use a Surface Hub without requiring a user to sign in. To enable this communal functionality, Surface Hub doesn't support Windows sign-in the same way that Windows 10 or Windows 11 Enterprise does (for example, signing in a user to the OS and using those credentials throughout the OS). Instead, there's always a local, auto signed-in, low-privilege user signed in to the Surface Hub. It doesn't support signing in any more users, including admin users (for example, when an admin signs in, they aren't signed in to the OS).

Users can sign in to a Surface Hub, but they won't be signed in to the OS. For example, when a user signs in to Apps or My Meetings and Files, the user is signed in only to the apps or services, not to the OS. As a result, the signed-in user is able to retrieve their cloud files and personal meetings stored in the cloud, and these credentials are discarded when **End session** is activated. The Meetings and Files sign-in process doesn't support EWSAllowList or EWSBlockList policies.

*Potential impact on organization policies:*

- Generally, Surface Hub uses lockdown features rather than user access control to enforce security. Policies related to password requirements, interactive sign in, user accounts, and access control don't apply for Surface Hub.

### Saving and browsing files

Users have access to a limited set of directories on the Surface Hub:

- Music
- Videos
- Documents
- Pictures
- Downloads

Files saved locally in these directories are deleted when users press **End session**. To save content created during a meeting, users should save files to a USB drive or to OneDrive.

*Potential impact on organization policies:* - Policies related to access permissions and ownership of files and folders don't apply for Surface Hub. Users can't browse and save files to system directories and network folders.

## Applications

### Default applications

With few exceptions, the default Universal Windows Platform (UWP) apps on Surface Hub are also available on Windows 10 or Windows 11 PCs.

UWP apps pre-installed on Surface Hub:

- Alarms & Clock
- Calculator
- Connect
- Excel Mobile
- Feedback Hub
- File Explorer
- Get Started
- Maps
- Microsoft Edge
- Microsoft Power BI
- Microsoft Teams
- Microsoft Whiteboard
- OneDrive
- Photos
- PowerPoint Mobile
- Settings
- Store
- Tips
- Word Mobile

*Potential impact on organization policies:*

- Use guidelines for Windows 10 or Windows 11 Enterprise to determine the features and network requirements for default apps on the Surface Hub.

### Installing apps, drivers, and services

To help preserve the appliance-like nature of the device, Surface Hub only supports installing Universal Windows Platform (UWP) apps, and doesn't support installing classic Win32 apps, services and drivers. Furthermore, only admins have access to install UWP apps.

*Potential impact on organization policies:*

- Employees can only use the apps that have been installed by admins, helping mitigate against unintended use. Surface Hub doesn't support installing Win32 agents required by most traditional PC management and monitoring tools.

## Security and lockdown

For Surface Hub to be used in communal spaces, such as meeting rooms, its custom OS implements many of the security and lockdown features available in Windows 10 or Windows 11. To learn more, see [Surface Hub Security Overview](surface-hub-security.md)

Surface Hub implements these Windows security features:

- [Secure Boot](/windows-hardware/design/device-experiences/oem-secure-boot)
- [Windows Defender Application Control and virtualization-based protection of code integrity](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Application restriction policies using AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)
- [BitLocker Drive Encryption](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Trusted Platform Module (TPM)](/windows/security/information-protection/tpm/trusted-platform-module-top-node)
- [Microsoft Defender Antivirus in Windows](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)
- [User Account Control (UAC)](/windows/security/identity-protection/user-account-control/user-account-control-overview) for access to the Settings app

These Surface Hub features provide more security:

- Custom UEFI firmware
- Custom shell and Start menu limits device to meeting functions
- Custom File Explorer only grants access to files and folders under My Documents
- Custom Settings app only allows admins to modify device settings
- Downloading advanced Plug and Play drivers is disabled

*Potential impact on organization policies:*

- Consider these features when performing your security assessment for Surface Hub.

## Management

### Device settings

Device settings can be configured through the Settings app. The Settings app is customized for Surface Hub, but also contains many familiar settings from Windows 10 or Windows 11 Desktop. A User Accounts Control (UAC) prompt appears when opening up the Settings app to verify the admin's credentials, but this doesn't sign in the admin.

*Potential impact on organization policies:*

- Employees can use the Surface Hub for meetings, but can't modify any device settings. In addition to lockdown features, this ensures that employees only use the device for meeting functions.

### Administrative features

The administrative features in Windows 10 or Windows 11 Enterprise, such as the Microsoft Management Console, Run, Command Prompt, PowerShell, Registry editor, and Task manager aren't supported on Surface Hub. The Settings app contains all of the administrative features locally available on Surface Hub.

#### Event viewer

Windows 10 Team 2020 Update 2 adds support for the Windows Event Viewer, which is identical to the [Event Viewer](/host-integration-server/core/windows-event-viewer1) installed on Windows 10 Pro or Windows 10 Enterprise.

**To open Event viewer:**

1. Sign in to **Settings** app with admin credentials.
2. Select **Update & Security** > **Logs** and under Event Viewer, select **Open**.

To learn more, see [Windows Event Viewer](/host-integration-server/core/windows-event-viewer1).

### Remote management and monitoring

Surface Hub supports remote management through mobile device management (MDM) solutions such as [Microsoft Intune](/mem/intune/) and monitoring through [Azure Monitor](/azure/azure-monitor/).

*Potential impact on organization policies:*

- Surface Hub doesn't support installing Win32 agents required by most traditional PC management and monitoring tools, such as System Center Operations Manager.

### Group Policy

Surface Hub doesn't support Windows Group Policy, including auditing. Instead, use MDM to apply policies to your Surface Hub. For more information about MDM, see [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md).

*Potential impact on organization policies:*

- Use MDM to manage Surface Hub rather than group policy.

### Remote assistance

Surface Hub doesn't support remote assistance.

*Potential impact on organization policies:*

- Policies related to remote assistance don't apply for Surface Hub.

## Network

<a name='domain-join-and-azure-active-directory-azure-ad-join'></a>

### Domain join and Microsoft Entra join

Surface Hub uses domain join and Microsoft Entra join primarily to provide a directory-backed admin group. Hybrid join isn't supported. Users can't sign in with a domain account. For more information, see [Admin group management](admin-group-management-for-surface-hub.md).

*Potential impact on organization policies:*

- Group policy settings aren't applied when a Surface Hub is joined to your domain. Policy settings related to domain membership don't apply to Surface Hub.

### Accessing domain resources

Users can sign in to Microsoft Edge to access intranet sites and online resources (such as Microsoft 365). If your Surface Hub is configured with a device account, the system uses it to access Exchange, Microsoft Teams Rooms, or Skype for Business. However, Surface Hub doesn't support accessing domain resources such as file shares and printers.

*Potential impact on organization policies:*

- Policies related to accessing domain objects don't apply for Surface Hub.

### Diagnostic data

The Surface Hub OS uses the Windows Connected User Experience to gather and transmit diagnostic data. For more information, see [Configure Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization).

*Potential impact on organization policies:*

- Configure diagnostic data levels for Surface Hub in the same way as you do for Windows 10 or Windows 11 Enterprise.
