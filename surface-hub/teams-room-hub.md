---
title: Microsoft Teams Rooms on Surface Hub 
description: This section explains how to configure Microsoft Teams Rooms on Surface Hub.
keywords: Teams Rooms, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/17/2021
ms.reviewer: 
manager: laurawi
ms.localizationpriority: medium
---
# Microsoft Teams Room on Surface Hub (preview)

Upon release in late 2021, Teams Rooms for Surface Hub will be installed on all Surface Hubs configured to receive automatic updates. The new experience, currently available as a [preview via the Windows Insider program](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-teams-rooms-on-surface-hub/ba-p/2118373), will replace the current [Surface Hub Teams app](hub-teams-app.md).
 

## What’s new?

- Meetings joined from the Surface Hub Welcome Screen or new Agenda page are joining “Edge to Edge” to put people in the foreground.
- Familiar meeting features including chat bubbles, reactions, desktop and application sharing, give and take control and audio, full PowerPoint live support, together mode, and large gallery.
- Teams Rooms on Surface Hub can run side by side with other applications or run minimized.
- Admins can configure features like Coordinated Meeting and Proximity Join for Surface Hub. [XML files](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) are supported and will be migrated to the new settings model.
- New QoS Options and network requirements. To learn more, see Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub***.***
- Changes to Teams mode, replacing Skype for Business as the default collaboration and meeting app. To learn more, see [Deploy Microsoft Teams for Surface Hub](/MicrosoftTeams/teams-surface-hub).


## In meeting experience

Teams Rooms on Surface Hub Meetings experience is aligned to the familiar experience that users know from their personal devices with adjustments made to optimize for a large screen device. Opening Teams on Surface Hub lets users access key features including One-touch meeting join, Meet Now and Dial Pad for PSTN or peer-to-peer calls.


## Manage Teams Rooms on Surface Hub

When signed in with administrative credentials, you can customize the Teams experience directly from the Settings menu including:

- Configure [Coordinated Meetings](/microsoftteams/rooms/coordinated-meetings) and Proximity join.
- Adjust settings for default microphones, cameras, and speakers.
- Check the client version and search for the latest updates.

The new Teams Rooms for Surface Hub client, will automatically apply existing settings configured via XML files, provisioning packages, or an MDM provider. These methods, explained in [Manage Microsoft Teams configuration on Surface Hub](/microsoftteams/rooms/surface-hub-manage-config), will be superseded by new cloud-based solutions, as described in Simplified management of Teams coming to Surface Hub.
 
## Prepare networking for Teams Rooms

To optimize Teams Rooms refer to the requirements and recommendations described in Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub.
 
## Simplified management of Teams coming to Surface Hub

When Teams Rooms for Surface Hub is publicly released later this year, admins can take advantage of the following solutions: 

- **Teams Admin Center.** Teams Admin Center provides a comprehensive self-management platform to monitor and manage the Teams Rooms experience on Teams devices. Teams Admin Center will be available to Microsoft Teams Rooms users at no additional cost.
- **Microsoft Teams Rooms managed service.** The [Microsoft Teams Rooms managed service](/microsoftteams/rooms/microsoft-teams-rooms-premium) is a cloud-based IT management and monitoring service that keeps Microsoft Teams Rooms devices and their peripherals up to date and proactively monitored, supporting an environment optimized for a great user experience.
