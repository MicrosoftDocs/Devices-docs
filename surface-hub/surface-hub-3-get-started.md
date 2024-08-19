---
title: Get started with Surface Hub running Microsoft Teams Rooms on Windows
description: Get started with Surface Hub running Microsoft Teams Rooms on Windows. Explore comprehensive setup guides, upgrade paths, IT management tips, and security best practices for Microsoft's interactive whiteboard.
ms.reviewer: dpandre
manager: frankbu
ms.service: surface-hub
author: coveminer
ms.author: dpandre
ms.topic: how-to
ms.date: 12/04/2023
ms.localizationpriority: medium
---

# Get started with Surface Hub running Microsoft Teams Rooms on Windows

[!INCLUDE [Hub MTR Scope](includes/hub-mtr-scope.md)]

## New installs

New deliveries of Surface Hub 3 and the Surface Hub 3 Compute Cartridge come preinstalled with the Microsoft Teams Rooms on Windows (MTR-W) experience. Turn it on and follow the prompts for the first run startup experience (aka OOBE). See [First-time setup for Surface Hub running Microsoft Teams Rooms on Windows](first-run-program-surface-hub-3.md) to learn more.

## Upgrade

If you have a Surface Hub 2S, you can upgrade to the new experience via the Surface Hub 3 Compute Cartridge. See [Install and manage Surface Hub 3 Compute Cartridge](install-manage-surface-hub-3-pack.md) to learn more.

## IT management of Surface Hub running MTR-W

In addition to Microsoft Intune and third-party MDM providers, IT admins can manage Surface Hubs running MTR-W via the [Microsoft Teams admin center](https://admin.teams.microsoft.com/) and use tools like [Microsoft Configuration Manager](/mem/configmgr/core/understand/introduction), third-party OMA-DM-based management tools, and [Windows Group Policy](/azure/active-directory-domain-services/manage-group-policy).

## Security considerations

Depending on your organization's security posture, you may wish to implement additional security measures beyond the default experience of running Microsoft Teams Rooms on Windows in a locked-down state. This includes changing the default Administrator password (factory set to **sfb**), adding a UEFI password, and implementing appropriate physical security measures. To learn more, see [Security best practices for Surface Hubs running Microsoft Teams Rooms on Windows](surface-hub-3-security.md).

### Teams management portals

#### Teams admin center

Microsoft Teams admin center is a web-based portal that provides management capabilities for Microsoft Teams. It is designed to provide a simple and intuitive way to manage your Teams environment at scale. With Teams admin center, you can:

- Perform device management, like restarting devices and downloading device logs.
- Apply Teams-specific settings.
- Check the health status of Microsoft Teams Rooms and their peripherals, including cameras, displays, and microphones.
- Review current and past meeting activity (such as details about call quality, network health and connectivity, and number of participants).
- See peripherals (such as cameras and projectors) connected to Microsoft Teams Rooms (only for Teams Rooms on Windows).

To manage Teams Rooms devices, open the [Microsoft Teams admin center](https://admin.teams.microsoft.com/) and go to **Teams Devices** > **Teams Rooms on Windows** or **Surface Hubs**.
To learn more, see:

- [Manage Microsoft Teams Rooms](/microsoftteams/rooms/rooms-manage) – Teams Admin Center

#### Teams Rooms Pro Management Portal

The Teams Rooms Pro Management service is a cloud-based management solution that proactively monitors and updates Microsoft Teams Rooms devices and their peripherals. The Pro management solution is for organizations looking to optimize the meeting room experience and perform
real-time monitoring and management for Teams Rooms devices. To learn more, see [Microsoft Teams Rooms Pro Management](/microsoftteams/rooms/rooms-pro-management).

## Licensing

New Surface Hub 3 devices, Surface Hub 3 Compute Cartridges, and Surface Hub 2S devices software-migrated to the MTR-W platform, all come with a Windows 11 IoT Enterprise license,  and you'll also need  
a [Teams Rooms](/microsoftteams/rooms/rooms-licensing) license. A Teams Rooms Pro license is recommended for advanced features like remote device management, conditional access policies, and detailed device analytics. To learn more, see [Microsoft Teams Rooms licenses](/microsoftteams/rooms/rooms-licensing#teams-rooms-license-service-plan-comparison).

## Next steps

- [Site readiness guide for Surface Hub 3](surface-hub-3-site-readiness-guide.md)
- [First-time setup for Surface Hub running Microsoft Teams Rooms on Windows](first-run-program-surface-hub-3.md)
- [Security best practices for Surface Hubs running Microsoft Teams Rooms on Windows](surface-hub-3-security.md)
- [Install wallpaper on Surface Hub running Microsoft Teams Rooms on Windows](install-wallpaper-surface-hub.md)

### Learn more

- [Install & manage Surface Hub 3 Compute Cartridge](install-manage-surface-hub-3-pack.md)
