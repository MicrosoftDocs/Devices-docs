---
title: Microsoft Teams Rooms on Surface Hub 
description: This article provides an overview of Microsoft Teams Rooms on Surface Hub and includes guidance on Direct Guest Join and related features. 
keywords: Teams Rooms, Surface Hub, Intune, QoS, Direct Guest Join
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 09/19/2022
ms.reviewer: dpandre
manager: laurawi
ms.localizationpriority: medium
---
# Microsoft Teams Rooms on Surface Hub

Teams Rooms for Surface Hub automatically replaced the previous [Surface Hub Teams app](hub-teams-app.md) upon installation of [KB5004196, KB5004198, and KB5004199](surface-hub-update-history.md).

## What’s new?

- Meetings joined from the Surface Hub Welcome Screen or new Agenda page are joining “Edge to Edge” to put people in the foreground.
- Familiar meeting features including chat bubbles, reactions, desktop and application sharing, give and take control and audio, full PowerPoint live support, together mode, and large gallery.
- Teams Rooms on Surface Hub can run side by side with other applications or run minimized.
- Admins can configure features like Coordinated Meeting, Proximity Join for Surface Hub, and [Direct Guest Join](#third-party-meetings-on-surface-hub). [XML files](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) are supported and will be migrated to the new settings model.
- New QoS Options and network requirements. To learn more, see [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).
- If not already the default, Teams can be set as the default app for meetings and calls in **Settings** > **Surface Hub** > **Calling & audio**. To learn more about meeting modes and configuring them through MDM policy, see [Manage Surface Hub with an MDM provider](manage-settings-with-mdm-for-surface-hub.md#changing-default-app-for-meetings--calls).

## In meeting experience

Teams Rooms on Surface Hub Meetings experience are aligned to the familiar experience that users know from their personal devices with adjustments made to optimize for a large screen device. Opening Teams on Surface Hub lets users access key features including One-touch meeting join, Meet Now and Dial Pad for PSTN or peer-to-peer calls.

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Teams Rooms on Surface Hub Agenda.":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Teams Rooms on Surface Hub Meeting.":::

## Manage Teams Rooms on Surface Hub

 You can customize the Teams experience directly from the Settings menu after entering administrative credentials, including:

- Configure [Coordinated Meetings](/microsoftteams/rooms/coordinated-meetings) and Proximity join.
- Adjust settings for default microphones, cameras, and speakers.
- Check the client version and search for the latest updates.

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Teams Rooms Settings.":::

The new Teams Rooms for Surface Hub client, will automatically apply existing settings configured via XML files, provisioning packages, or an MDM provider. These methods, explained in [Manage Microsoft Teams configuration on Surface Hub](/microsoftteams/rooms/surface-hub-manage-config), will be superseded by new cloud-based solutions, as described below in [Simplified management of Teams coming to Surface Hub](#simplified-management-of-teams-on-surface-hub).

### Prepare networking for Teams Rooms

To optimize Teams Rooms, refer to the requirements and recommendations described in [Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub](surface-hub-teams-rooms-networking.md).

### Simplified management of Teams on Surface Hub

- **Teams Admin Center.** Teams Admin Center provides a comprehensive self-management platform to monitor and manage the Teams Rooms experience on Teams devices. Teams Admin Center is available to Microsoft Teams Rooms users at no additional cost.
- **Microsoft Teams Rooms managed service.** The [Microsoft Teams Rooms managed service](/microsoftteams/rooms/microsoft-teams-rooms-premium) is a cloud-based IT management and monitoring service that keeps Microsoft Teams Rooms devices and their peripherals up to date and proactively monitored, supporting an environment optimized for a great user experience.

## Third-party meetings on Surface Hub

Microsoft Teams Rooms on Surface Hub supports joining third-party online meetings, referred to as Direct Guest Join. You can use Surface Hub to join meetings hosted on Cisco Webex and Zoom. And others can join Teams meetings on Hub from their third-party room systems. This feature is rolling out to Surface Hubs beginning September 19. 

### To enable third-party meetings on Surface Hub:

1. Open Teams, select Settings (**…**), and enter your admin username and password.
2. Select **Meetings** and then select **Allow joining third-party meetings**. 
:::image type="content" source="images/teams-settings-surface-hub.png" alt-text="Enable third party meetings on Surface Hub Meeting.":::
1. Select **Cisco WebEx** or **Zoom**, as appropriate.

### To join third-party meetings:

1. Select **Home**, select the meeting tile from the home screen calendar, or go directly to the Teams agenda page, which includes join buttons for the third-party-enabled meetings.

    :::image type="content" source="images/jointhirdpartymeeting-hub.png" alt-text="Join third party meetings on Surface Hub Meeting.":::

1. Select **Join**. When the Microsoft Edge browser launches you into the meeting, you'll need to allow the browser to use the Surface Hub microphone and camera for the meeting.  

> [!NOTE]
> Microphone and camera approvals are removed when you end a Surface Hub session, and you will be asked to allow them again in the next session.

3.Enter your name and other required fields to start the meeting.

### Optional advanced configuration for third-party meetings

Depending on your environment, you may need to configure more settings. For example, you should ensure your organization has no policies preventing you from connecting to third-party meeting services.

#### Configure Edge policy settings

To enable a more seamless experience that avoids users having to approve the microphone and camera for each Hub session, you can configure the following Edge policies via Microsoft Endpoint Manager. 

| Microsoft Edge policy setting                                                 | Location                                                                                                  | Notes                                                                                                   |
| ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Force synchronization of browser data and do not show the sync consent prompt** | Devices > Configuration Profiles > Administrative Templates > Edge Chromium General Policies | Properties | Enable                                                                                                  |
| **Sites that can access video capture devices without requesting permission**     | Devices > Configuration Profiles > Administrative Templates > Edge Chromium General Policies | Properties |                                                                                                         |
| **Sites that can access audio capture devices without requesting permission**    | Devices > Configuration Profiles > Administrative Templates > Edge Chromium General Policies | Properties |                                                                                                         |
| **Default geolocation setting**                                                 | Devices > Configuration Profiles > Administrative Templates > Edge Chromium General Policies | Properties | Policy options mapping: * BlockGeolocation (2) = Don't allow any site to track users' physical location |

Optionally, you may wish to configure calendar processing rules to enable "auto accept," "auto decline," and related settings.

To learn more, see [Enable Teams Rooms devices to join third-party meetings](/microsoftteams/rooms/third-party-join) and related [Teams Rooms documentation](/microsoftteams/rooms/).
 
## Support for Teams Rooms in Government Community Cloud High (GCC-H)

A one-time manual update of the Teams Rooms client to version 1.4.00.25354 is needed in order to for it to be able to connect to a GCC-H tenant and then keep itself up-to-date automatically:

 - Confirm that your Hub has KB5005611 or a later Windows Cumulative Update installed
 - Use [Teams_Uninstall_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Uninstall_Win32.ppkg) to remove current Teams Rooms on Surface Hub version
 - Restart your device
 - Install [Teams_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Win32.ppkg) to install version 1.4.00.25354
 - Restart your device again

Detailed steps:

1. Save both provisioning packages to the root of your USB drive.
2.	Insert the USB drive into your Surface Hub.
3.	On your Surface Hub, open the Start menu, select All apps, and then select Settings.
4.	Provide your Hub admin credentials when prompted.
5.	Go to **Surface Hub** > **Device management** > **Add or remove a provisioning package**, and then select **Add a package**.
6.	Under **Select a package**, select the Teams_Uninstall_win32.ppkg provisioning package, and then restart your Surface Hub.
7.	On your Surface Hub, open the Start menu, select All apps, and then select Settings.
8.	Provide your Hub admin credentials when prompted.
9.	Go to **Surface Hub** > **Device management** > **Add or remove a provisioning package**, and then select **Add a package**.
10.	Under **Select a package**, select the Teams_win32.ppkg provisioning package, and then restart your Surface Hub.
