---
title: Surface UEFI settings reference for SEMM 
description: This article provides a technical reference of UEFI settings for Surface devices enrolled into Surface Enterprise Management Mode.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 04/25/2024
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 11
- Windows 10
---

# SEMM UEFI settings reference 

This article provides a technical reference of Unified Extensible Firmware Interface (UEFI) settings for Surface devices enrolled into Surface Enterprise Management Mode (SEMM). Configure UEFI settings using the [Surface UEFI Configurator](surface-it-toolkit-uefi-config.md) included in the [Surface IT Toolkit](surface-it-toolkit.md).  

## Enable or disable components in Surface UEFI

The following components can be turned or off:

- Docking USB port
- On-board audio
- Digital graphics processing unit
- Type cover
- Micro SD card
- Front camera
- Rear camera
- Infrared camera (for Windows Hello)
- Bluetooth only
- Wireless network and Bluetooth
- Long-term evolution (LTE)
- Discrete GPU (dGPU)
- On-board microphone
- MAC address emulation
- Wired LAN
- Near-field communication (NFC)

## Table 1. Advanced settings

| Setting                            | Description                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| IPv6 for PXE Boot                  | Allows you to manage IPv6 support for PXE boot. If you don't configure this setting, IPv6 support for PXE boot is **disabled**.                                                                               |
| Alternate Boot                     | Allows you to manage the use of an Alternate boot order to boot directly to a USB or Ethernet device by pressing both the Volume Down button and Power button during boot. If you don't configure this setting, Alternate boot is enabled. |
| Boot Order Lock                    | Allows you to lock the boot order to prevent changes. If you don't configure this setting, Boot Order Lock is disabled.                                                                                                        |
| USB Boot                           | Allows you to manage booting to USB devices. If you don't configure this setting, USB Boot is enabled.                                                                                                                 |
| Network Stack                      | Allows you to manage Network Stack boot settings. If you don't configure this setting,  the ability to manage Network Stack boot settings is **disabled**.                                                                                                           |
| Auto Power On                      | Allows you to manage Auto Power-on boot settings. If you don't configure this setting, Auto Power-on is enabled.                                                                                                        |
| Simultaneous Multi-Threading (SMT) | Allows you to manage Simultaneous Multi-Threading (SMT) to enable or disable hyperthreading. If you don't configure this setting, SMT is enabled.                                                  |
| Enable Battery limit               | Allows you to manage Battery limit functionality. If you don't configure this setting, Battery limit is **disabled** |
| Security                           | Displays the Surface UEFI **Security** page. If you don't configure this setting, the Security page is displayed.                                                                                                                 |
| Devices                            | Displays the Surface UEFI **Devices** page. If you don't configure this setting,  the Devices page is displayed.                                                                                                                     |
| Boot                               | Displays the Surface UEFI **Boot** page. If you don't configure this setting, the Boot page is displayed.                                                                                                                                                            |
| DateTime                           | Displays the Surface UEFI **DateTime** page. If you don't configure this setting, the DateTime page is displayed.                                                                                                                |
| EnableOSMigration                  | Allows you to migrate Surface Hub 2S from Windows 10 Team to Windows 10/11 Pro or Enterprise. If you don't configure this setting, Surface Hub 2S devices can run only the Windows 10 Team OS. Note: Dual booting between Windows 10 Team and Windows 10/11 Pro/Enterprise isn't available on Surface Hub 2S.                                                                                                           |
| Secured Core                       | Allows you to manage Secured Core functionality. If you don't configure this setting, Secured Core functionality is enabled on supported devices.                                                                                                         |
| Wake-on-LAN                        | Allows you to manage Wake-on-LAN functionality. If you don't configure this setting, Wake-on-LAN is **disabled** on supported devices.                                                                                                            |
| Wake-on-Power                      | Allows you to manage Wake-on-Power functionality. If you don't configure this setting, Wake-on-Power is disabled on supported devices.                                                                                                          |
