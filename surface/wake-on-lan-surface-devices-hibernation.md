---
title: Wake On LAN for Surface devices 
description: See how you can use Wake On LAN to remotely wake up devices to perform management tasks automatically.
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
ms.date: 6/04/2021
---

# Wake On LAN for Surface devices in hibernation

To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows. WOL works by default for Surface devices in Modern Standby (also known as Connected Standby). But — unless your devices are [connected to Surface Dock 2](wake-on-lan-surface-dock2.md) — to wake devices from "deeper" power states requires some minimal IT configuration, as described on this page.

## Requirements

Devices must be connected to AC power and have a wired connection with one of the following compatible Ethernet adapters:

- Surface USB 3.0 Gigabit Ethernet Adapter
- Surface Ethernet Adapter
- Surface USB-C to Ethernet and USB Adapter
- Microsoft USB-C Travel Adapter Hub
- Surface Dock
- Surface Dock 2

## Wake devices from Hibernation or Shut-down power states

 To wake devices not connected to Surface Dock 2, requires you to first enable a UEFI policy setting via [Surface Enterprise Management Mode](surface-enterprise-management-mode.md) (SEMM).

> [!IMPORTANT]
> This section is intended only for waking devices out of Hibernation or Shut-down power states. Waking devices out of Modern Standby does not require any UEFI policy setting configuration.

To enable the Wake on LAN UEFI setting you need to enroll target devices into SEMM, create a configuration package, and apply the package to the devices. For more information, refer to:

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Enroll and configure Surface devices with SEMM](enroll-and-configure-surface-devices-with-semm.md)

1. Download and install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).
2. Select **Start** > **Configuration Package** > **Create** >**+ Certificate Protection**.
3. Go to **Advanced settings** and switch **Wake on LAN** to **On**.
4. Apply the package to target devices.

    > [!div class="mx-imgBorder"]
    > ![Enable Wake on LAN UEFI policy setting](images/wol-uefi.png)

## Learn more

- [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)
- [Microsoft Surface USB-C to Ethernet and USB Adapter](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [Surface USB 3.0 Gigabit Ethernet Adapter](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
