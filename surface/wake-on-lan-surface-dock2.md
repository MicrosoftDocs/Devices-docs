---
title: Wake On LAN for Surface Dock 2
description: Surface Dock 2 provides the best support for Wake on LAN (WOL) enabling admins to remotely wake up devices and automatically perform management tasks.
keywords: update, deploy, driver, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 6/03/2021
---

# Wake On LAN for Surface Dock 2

To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows. Surface Dock 2 provides the best support for Wake on LAN (WOL) enabling admins to remotely wake up devices and automatically perform management tasks with Microsoft Intune or other mobile device management (MDM) providers. Devices must be connected to AC power and have a wired connection with Surface Dock 2.

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## Supported Surface devices

- Surface Laptop 4 (Intel processors)
- Surface Laptop 4 (AMD processors)
- Surface Laptop 3 (Intel processors)
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop Go
- Surface Book 3

Surface Dock 2 provides WOL support for devices in the following power states:

- Connected standby
- Hibernation (S4 power state)
- Hibernation (S5 “soft off” power state)

To learn more about power states, see [System Power States](/windows/win32/power/system-power-states).

## How it works

When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby. IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device. Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.

To enable WOL on devices without Surface Dock 2, see [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md).

## Learn more

- [Surface Dock 2](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [Wake On LAN for Surface devices](wake-on-lan-for-surface-devices.md)
- [System Power States](/windows/win32/power/system-power-states)
- [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)
