---
title: Wake On LAN for Surface devices
description: Surface devices that run Windows 10, version 1607 or later and use a Surface Ethernet adapter to connect to a wired network are capable of Wake On LAN (WOL) from Modern Standby.
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
ms.date: 11/30/2021
appliesto:
- Windows 10
- Windows 11
---

# Wake On LAN for Surface devices 

Surface devices that run Windows 10 version 1607 or later are capable of Wake On LAN (WOL) from Modern Standby (also known as Connected Standby). With WOL, IT admins can remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or third party solutions.

>[!NOTE]
>To support WOL, Surface devices must be plugged into AC power and use a Surface Ethernet adapter that is connected to a wired network.

## Supported devices

Ethernet adapters with support for WOL:

- Microsoft USB-C Travel Hub
- Surface Ethernet adapter
- Surface USB-C to Ethernet and USB 3.0 Adapter
- Surface USB 3.0 Gigabit Ethernet Adapter 
- Surface DockDocking Station for Surface Pro 3 
- Surface Dock 2
- Docking Station for Surface 3
- Docking Station for Surface Pro 3 

Surface devices with support for WOL:

- Surface 3
- Surface Pro 3
- Surface Pro 4
- Surface Pro (5th Gen)
- Surface Pro (5th Gen) with LTE Advanced
- Surface Pro 6
- Surface Pro 7
- Surface Pro 7+
- Surface Pro 8
- Surface Book (all generations)
- Surface Go (all generations)
- Surface Laptop (all generations)
- Surface Laptop Go
- Surface Laptop Go 2
- Surface Laptop SE
- Surface Laptop Studio
- Surface Studio 2 (see Surface Studio 2 instructions below)


## Using WOL 

When not in use, Surface devices enter an idle, low-powered state known as Modern Standby or Connected Standby. IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device. The destination network interface card (NIC) compares the MAC address with its own before waking up the device. If the MAC address in the magic packet wake request does not match the MAC address on the destination NIC, the NIC won’t wake up the device. To learn more, review [Wake sources documentation](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## Modern Standby

Modern Standby starts when the user causes the system to enter sleep, or the device goes to sleep based on the Windows power settings the user has set. For example, the user presses the power button, closes the lid, or selects Sleep from the power button in the Windows Start menu. WOL works by default for Surface devices in Modern Standby mode running Windows 10 version 1607 or later. No additional IT configuration is required, except for Surface Studio 2.

## Surface Studio 2 instructions

To enable WOL on Surface Studio 2, you must use the following procedure

1. Open Registry Editor (**Start** > **Search** > **regedit.exe**) and create the following registry keys:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   ```

2. Run the following command

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

> [!NOTE]
> If you upgrade the version of Windows 10 on your Surface Studio 2 (for example, you upgrade from Windows 10 20H2 to 21H1), you will need to follow these instructions again to enable WOL.


### To wake from hibernation (S4) or shutdown (S5) 

- For devices connected to Surface Dock 2, see [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)
