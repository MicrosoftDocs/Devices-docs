---
title: Wake On LAN with Surface Thunderbolt 4 Dock
description: Surface Thunderbolt 4 Dock supports Wake on LAN (WOL) enabling admins to remotely wake up Surface devices.
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 04/04/2023
ms.localizationpriority: medium
appliesto:
- Windows 10
- Windows 11
---

# Wake On LAN with Surface Thunderbolt 4 Dock

To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows. Surface Thunderbolt™ 4 Dock supports Wake on LAN (WOL) enabling admins to remotely wake up Surface devices.

## Requirements

- Devices must have a wired connection with Surface Thunderbolt™ 4 Dock and stay connected to AC Power.
- Ensure host devices have installed the latest firmware and drivers, available via Windows Update or the Surface App. For WOL to function, host devices must have a Thunderbolt Ethernet driver.

> [!TIP]
> You can manually download the appropriate drivers from the [Surface Thunderbolt 4 Dock Firmware and Drivers page](https://www.microsoft.com/download/details.aspx?id=105115). Choose Arm64 for Surface Pro 9 with 5G, Surface Pro X, or compatible Windows on ARM devices. Choose x64 for all other devices.

## Wake up from Modern Standby

Modern Standby starts when the user causes the system to enter sleep, or the device goes to sleep based on the Windows power settings the user has set. For example, the user presses the power button, closes the lid, or selects Sleep from the power button in the Windows Start menu. WOL works by default for Surface devices in Modern Standby mode.

### Supported Surface devices

- Surface Laptop 5
- Surface Laptop 4 (Intel processors)
- Surface Laptop 4 (AMD processors)
- Surface Laptop 3 (Intel processors)
- Surface Pro 9 (Intel processors)
- Surface Pro 9 with 5G
- Surface Studio 2+
- Surface Pro 8
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go (all generations)
- Surface Laptop Go
- Surface Laptop Go 2
- Surface Book 3
- Surface Laptop Studio

## Learn more

- [Wake On LAN for Surface devices](wake-on-lan-for-surface-devices.md)
- [System Power States](/windows/win32/power/system-power-states)
