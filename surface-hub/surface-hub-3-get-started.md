---
title: Get started with Surface Hub running Microsoft Teams Rooms on Windows
description: Get started with Surface Hub 3 running Microsoft Teams Rooms on Windows. Learn setup, upgrade, IT management, security, and licensing essentials.
ms.reviewer: dpandre
manager: frankbu
ms.service: surface-hub
author: coveminer
ms.author: dpandre
ms.topic: how-to
ms.date: 09/24/2024
ms.localizationpriority: medium
---

# Get started with Surface Hub running Microsoft Teams Rooms on Windows

[!INCLUDE [Hub MTR Scope](includes/hub-mtr-scope.md)]

## New installs

New Surface Hub 3 devices and Surface Hub 3 Compute Cartridges come preinstalled with the Microsoft Teams Rooms on Windows experience. Turn it on and follow the prompts for the first run startup experience. See [First-time setup for Surface Hub running Microsoft Teams Rooms on Windows](first-run-program-surface-hub-3.md) to learn more.

## Upgrade

If you have a Surface Hub 2S, you can upgrade to the new experience via the Surface Hub 3 Compute Cartridge (formerly Surface Hub 3 Pack). See [Install and manage Surface Hub 3 Compute Cartridge](install-manage-surface-hub-3-compute-cartridge.md) to learn more.

## IT management of Surface Hub running Teams Rooms on Windows 

In addition to Microsoft Intune and other mobile device management (MDM) providers, IT admins can manage Surface Hubs running Teams Rooms on Windows via the [Microsoft Teams admin center](https://admin.teams.microsoft.com/). Use tools like [Microsoft Configuration Manager](/mem/configmgr/core/understand/introduction), OMA-DM-based management tools, and [Windows Group Policy](/azure/active-directory-domain-services/manage-group-policy).

## Security considerations

Depending on your organization's security posture, you might consider implementing more security measures beyond the default experience of running Microsoft Teams Rooms on Windows in a locked-down state. This strategy includes changing the default Administrator password (factory set to **sfb**), adding a UEFI password, and implementing appropriate physical security measures. To learn more, see [Security best practices for Surface Hubs running Microsoft Teams Rooms on Windows](surface-hub-3-security.md).

## Teams management portals

### Teams admin center

The Microsoft Teams admin center is a web-based portal that provides management capabilities for Microsoft Teams, enabling you to:

- Monitor the health of Microsoft Teams Rooms and peripherals like cameras, displays, and microphones.
- Review meeting activity, including call quality, network health, connectivity, and participant numbers.
- Manage devices, including restarting them and downloading logs.
- Apply Teams-specific settings.
- View peripherals connected to Microsoft Teams Rooms, such as cameras and projectors (available for Teams Rooms on Windows only).

To manage Teams Rooms devices, open the [Microsoft Teams admin center](https://admin.teams.microsoft.com/) and go to **Teams Devices** > **Teams Rooms on Windows**.
To learn more, see:

- [Manage Microsoft Teams Rooms](/microsoftteams/rooms/rooms-manage) – Teams Admin Center

### Teams Rooms Pro Management service

The Teams Rooms Pro Management service is a cloud-based management solution that proactively monitors and updates Microsoft Teams Rooms devices and their peripherals. The Pro management solution is for organizations looking to optimize the meeting room experience and perform
real-time monitoring and management for Teams Rooms devices. To learn more, see [Microsoft Teams Rooms Pro Management](/microsoftteams/rooms/rooms-pro-management).

## Licensing

All new Surface Hub 3 devices, Surface Hub 3 Compute Cartridges, and Surface Hub 2S devices that are software-migrated to the Teams Rooms on Windows platform include a Windows 11 IoT Enterprise license. In addition, a [Teams Rooms license](/microsoftteams/rooms/rooms-licensing) is required. For advanced features like remote device management, conditional access policies, and detailed analytics, a Teams Rooms Pro license is recommended. To learn more, see [Microsoft Teams Rooms licenses](/microsoftteams/rooms/rooms-licensing#teams-rooms-license-service-plan-comparison).

## Next steps

- [Site readiness guide for Surface Hub 3](surface-hub-3-site-readiness-guide.md)
- [First-time setup for Surface Hub running Microsoft Teams Rooms on Windows](first-run-program-surface-hub-3.md)
- [Security best practices for Surface Hubs running Microsoft Teams Rooms on Windows](surface-hub-3-security.md)
- [Install wallpaper on Surface Hub running Microsoft Teams Rooms on Windows](install-wallpaper-surface-hub.md)

### Learn more

- [Install & manage Surface Hub 3 Compute Cartridge](install-manage-surface-hub-3-compute-cartridge.md)
