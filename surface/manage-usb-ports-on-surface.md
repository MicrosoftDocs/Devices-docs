---
title: Manage USB ports on Surface devices
description: This article explains how to secure and manage USB-C and USB-A ports on Surface devices 
ms.prod: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 10/18/2023
ms.reviewer: dashap
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---

# Manage USB ports on Surface devices

With USB port functionality enabled by default on Surface devices, many devices with Surface UEFI allow admins to disable connectivity to USB ports. For example, you may wish to prevent users from copying data from USB thumb drives or external hard disks.

How you manage USB port functionality varies across Surface devices. Recently released devices—Surface Pro 8, Surface Go 3, and Surface Laptop Studio—allow you to use PowerShell to granularly manage the functionality of USB-C ports and disable USB-A. See [Table 1](#table-1-usb-port-management-options-for-surface-devices) below for a reference of available settings across Surface devices.

For USB-A ports supporting USB2 and USB3, you can disable the USB data protocol from the USB controller to prevent all functionality.

Managing USB-C ports with their support for DisplayPort and USB Power Delivery provides more options beyond disabling all functionality. For example, you can prevent data connectivity to stop users from copying data from USB storage but retain the ability to extend displays and charge the device via a USB-C dock.

Beginning with Surface Pro 8, Surface Laptop Studio, and Surface Go 3, both of these options are now available via the SEMM PowerShell scripts.

**To manage USB ports:**

1. Go to [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) and download **SEMM_PowerShell.zip**.
2. Open **ConfigureSEMM.ps1** and modify as appropriate.
3. To disable both USB-A and USB-C ports: For UsbPortSettingType, enable the following setting: **UsbPortHwDisabled.**

**Additional options for USB-C ports:**

1. Run **ConfigureSEMM.ps1** and modify as appropriate.
2. To turn off data only and continue to use USB-C ports for power and display functionality, enable the following mode:  **Mode 1 – Data Disabled.**
3. To turn off data, power, and display functionality, enable the following mode:  **Mode 2 – Fully Disabled.**

### Table 1. USB port management options for Surface devices

| Device                                                                                                                                                                   | USB-A options                     | USB-C options                                                                                                                                                  | Settings                                                                   | SEMM IDs |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------- |
| **Surface Laptop**<br> **Surface Laptop 2**<br>**Surface Pro**<br>**Surface Pro 4**<br>**Surface Pro 6**<br>**Surface Studio**<br> **Surface Studio 2**<br>  | Enable or disable data            | N/A: No USB-C port on device                                                                                                                                   | USBPortEnabled (default)<br><br> USBPortHWDisabled                          | 370-379  |
| **Surface Laptop SE**<br>**Surface Pro 7**<br>**Surface Pro 7+**<br>**Surface Pro 9 5G**<br>**Surface Go**<br>**Surface Go 2**<br>**Surface Laptop Go**<br>**Surface Laptop Go 2**<br>**Surface Laptop 3** (Intel only)<br>>**Surface Laptop 4** (Intel only)<br>**Surface Laptop 5** (Intel only)<br> **Surface Studio 2+**| Enable or disable data            |  Enabled data, display out, and power delivery<br><br>Disabled data, display out, and power delivery                                                            |  USBPortEnabled (default)<br><br>USBPortHWDisabled                          | 370-379  |
| **Surface Pro 8**<br> **Surface Pro 9**<br>**Surface Laptop Studio**<br>**Surface Laptop 5**<br>**Surface Studio 2+**<br>**Surface Go 3**<br>                                                                                                       | N/A: No USB-A port on device      | Enabled data, display-out, and  power delivery<br><br>Disabled data but enabled display-out and power delivery<br><br>Disabled data, display-out, and power delivery | UsbPortEnabled (default)<br>UsbPortDataDisabled<br>UsbPortHwDisabled | 380-389  |
| **Surface Book 2** and later <br>                                                                                                                        | Base USB ports are always enabled | Base USB ports are always enabled                                                                                                                              | n/a                                                                        |          |
| **Surface Book** with Performance Base<br>**Surface Book**                                                                                                               | Base USB ports are always enabled | N/A: No USB-C port on device                                                                                                                                   | n/a                                                                        |          |