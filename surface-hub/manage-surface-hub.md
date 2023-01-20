---
title: Manage Microsoft Surface Hub
description: How to manage your Surface Hub after finishing the first-run program.
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 01/17/2018
ms.localizationpriority: medium
---

# Manage Microsoft Surface Hub

After initial setup of Microsoft Surface Hub, device settings and configuration can be modified or changed in a couple ways:

- **Local management** - Every Surface Hub can be configured locally using the **Settings** app on the device. To prevent unauthorized users from changing settings, the Settings app requires admin credentials to open the app. For more information, see [Local management for Surface Hub settings](local-management-surface-hub-settings.md).
- **Remote management** - Surface Hub allow IT admins to manage settings and policies using a mobile device management (MDM) provider, such as Microsoft Intune, Microsoft Endpoint Configuration Manager, and other third-party providers. Additionally, admins can monitor Surface Hubs using Azure Monitor.  For more information, see [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md), and [Monitor Surface Hubs with Azure Monitor to track their health](/azure/azure-monitor/insights/surface-hubs).

> [!TIP]
> These management methods are not mutually exclusive. Devices can be both locally and remotely managed if you choose. However, MDM policies and settings will overwrite local changes when the Surface Hub syncs with the management server.

## In this section

Learn about managing and updating Surface Hub.

| Topic | Description |
| ----- | ----------- |
| [Remote Surface Hub management](remote-surface-hub-management.md) |Topics related to managing your Surface Hub remotely. Include install apps, managing settings with MDM and monitoring with Operations Management Suite. |
| [Manage Surface Hub settings](manage-surface-hub-settings.md) |Topics related to managing Surface Hub settings: accessibility, device account, device reset, fully qualified domain name, Windows Update settings, and wireless network |
| [Install apps on your Surface Hub](install-apps-on-surface-hub.md) | Admins can install apps can from either the Microsoft Store or the Microsoft Store for Business.|
[Configure Surface Hub Start menu](surface-hub-start-menu.md) | Use MDM to customize the Start menu for Surface Hub.
| [Set up and use Microsoft Whiteboard](whiteboard-collaboration.md)  | Microsoft Whiteboard’s latest update includes the capability for two Surface Hubs to collaborate in real time on the same board.   |
| [End a meeting with End session](finishing-your-surface-hub-meeting.md) | At the end of a meeting, users can tap **End session** to clean up any sensitive data and prepare the device for the next meeting.|
| [Sign in to Surface Hub with Microsoft Authenticator](surface-hub-authenticator-app.md) | You can sign in to a Surface Hub without a password using the Microsoft Authenticator app, available on Android and iOS.   |
| [Save your BitLocker key](save-bitlocker-key-surface-hub.md) | Every Surface Hub is automatically set up with BitLocker drive encryption software. Microsoft strongly recommends that you make sure you back up your BitLocker recovery keys.|
| [Connect other devices and display with Surface Hub](connect-and-display-with-surface-hub.md) | You can connect other device to your Surface Hub to display content.|
| [Miracast on existing wireless network or LAN](miracast-over-infrastructure.md) | You can use Miracast on your wireless network or LAN to connect to Surface Hub. |
 [Enable 802.1x wired authentication](enable-8021x-wired-authentication.md) | 802.1x Wired Authentication MDM policies have been enabled on Surface Hub devices.
| [Using a room control system](use-room-control-system-with-surface-hub.md) | Room control systems can be used with your Microsoft Surface Hub.|
[Using the Surface Hub Recovery Tool](surface-hub-recovery-tool.md) | Use the Surface Hub Recovery Tool to re-image the Surface Hub SSD.
[Surface Hub SSD replacement](surface-hub-ssd-replacement.md) | Learn how to remove and replace the solid state drive in your Surface Hub.

## Related topics

- [View reports and dashboards in presentation mode on Surface Hub and Windows 10 devices](https://powerbi.microsoft.com/documentation/powerbi-mobile-win10-app-presentation-mode/)
