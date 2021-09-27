---
title: Microsoft Teams Rooms on Surface Hub 
description: This article provides an overview of Microsoft Teams Rooms on Surface Hub.
keywords: Teams Rooms, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: dpandre
manager: laurawi
ms.localizationpriority: medium
---
# Microsoft Teams Rooms on Surface Hub

Teams Rooms for Surface Hub will automatically replace the current [Surface Hub Teams app](hub-teams-app.md) as part of a 4-week global rollout beginning September 30. For a demo of the new Teams experience, currently available as a preview via the Windows Insider program, see [Introducing Teams Rooms on Surface Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-teams-rooms-on-surface-hub/ba-p/2118373).

## What’s new?

- Meetings joined from the Surface Hub Welcome Screen or new Agenda page are joining “Edge to Edge” to put people in the foreground.
- Familiar meeting features including chat bubbles, reactions, desktop and application sharing, give and take control and audio, full PowerPoint live support, together mode, and large gallery.
- Teams Rooms on Surface Hub can run side by side with other applications or run minimized.
- Admins can configure features like Coordinated Meeting and Proximity Join for Surface Hub. [XML files](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) are supported and will be migrated to the new settings model.
- New QoS Options and network requirements. To learn more, see [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).
- Changes to Teams mode, replacing Skype for Business as the default collaboration and meeting app. To learn more, see [Deploy Microsoft Teams for Surface Hub](/MicrosoftTeams/teams-surface-hub).

## In meeting experience

Teams Rooms on Surface Hub Meetings experience is aligned to the familiar experience that users know from their personal devices with adjustments made to optimize for a large screen device. Opening Teams on Surface Hub lets users access key features including One-touch meeting join, Meet Now and Dial Pad for PSTN or peer-to-peer calls.

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Teams Rooms on Surface Hub Agenda.":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Teams Rooms on Surface Hub Meeting.":::

## Manage Teams Rooms on Surface Hub

 You can customize the Teams experience directly from the Settings menu after entering administrative credentials, including:

- Configure [Coordinated Meetings](/microsoftteams/rooms/coordinated-meetings) and Proximity join.
- Adjust settings for default microphones, cameras, and speakers.
- Check the client version and search for the latest updates.

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Teams Rooms Settings.":::

The new Teams Rooms for Surface Hub client, will automatically apply existing settings configured via XML files, provisioning packages, or an MDM provider. These methods, explained in [Manage Microsoft Teams configuration on Surface Hub](/microsoftteams/rooms/surface-hub-manage-config), will be superseded by new cloud-based solutions, as described below in [Simplified management of Teams coming to Surface Hub](#simplified-management-of-teams-coming-to-surface-hub).

### Prepare networking for Teams Rooms

To optimize Teams Rooms refer to the requirements and recommendations described in [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).

### Support for Teams Rooms in Government Community Cloud High (GCC-H)

When Teams Rooms for Surface Hub is publicly released later this year, a one-time manual update of the client to version 1.4.00.25354 is needed in order to for it to be able to connect to a GCC-H tenant and then keep itself up-to-date automatically:

 - Confirm that your Hub has KB5005611 or a later Windows Cumulative Update installed
 - Use Teams_Uninstall_win32.ppkg to remove current Teams Rooms on Surface Hub version
 - Restart your device
 - Install Teams_win32.ppkg to install version 1.4.00.25354
 - Restart your device again

Detailed steps:

1. Save both provisioning packages to the root of your USB drive
2.	Insert the USB drive into your Surface Hub
3.	On your Surface Hub, open the Start menu, select All apps, and then select Settings
4.	Provide your Hub admin credentials when prompted
5.	Go to **Surface Hub** > **Device management** > **Add or remove a provisioning package**, and then select **Add a package**
6.	Under **Select a package**, select the Teams_Uninstall_win32.ppkg provisioning package, and then restart your Surface Hub
7.	On your Surface Hub, open the Start menu, select All apps, and then select Settings
8.	Provide your Hub admin credentials when prompted
9.	Go to **Surface Hub** > **Device management** > **Add or remove a provisioning package**, and then select **Add a package**
10.	Under **Select a package**, select the Teams_win32.ppkg provisioning package, and then restart your Surface Hub


### Simplified management of Teams coming to Surface Hub

When Teams Rooms for Surface Hub is publicly released later this year, admins can take advantage of the following solutions:

- **Teams Admin Center.** Teams Admin Center provides a comprehensive self-management platform to monitor and manage the Teams Rooms experience on Teams devices. Teams Admin Center will be available to Microsoft Teams Rooms users at no additional cost.
- **Microsoft Teams Rooms managed service.** The [Microsoft Teams Rooms managed service](/microsoftteams/rooms/microsoft-teams-rooms-premium) is a cloud-based IT management and monitoring service that keeps Microsoft Teams Rooms devices and their peripherals up to date and proactively monitored, supporting an environment optimized for a great user experience.
