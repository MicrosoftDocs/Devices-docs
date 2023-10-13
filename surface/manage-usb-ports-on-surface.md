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

## Get started

- IT admins can perform many USB and related port management tasks using the Surface UEFI Configurator tool to prepare .msi packages for deployment to Surface devices. Go to Manage ports via UEFI Configurator on this page. 
- Alternatively, for the most advanced scenarios, you can modify downloadable Powershell scripts for deployment to target devices via Microsoft Configuration Manager. To to Manage ports via Powershell on this page. 

## Manage ports via UEFI Configurator

## Manage ports via Powershell

You can use PowerShell to granularly manage the functionality of USB-C ports and disable USB-A. See [Table 1](#table-1-usb-port-management-options-for-surface-devices) below for a reference of available settings across Surface devices.

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
| **Surface Laptop**<br> **Surface Laptop 2**<br>**Surface Pro**<br>**Surface Pro 4**<br>**Surface Pro 6**<br>**Surface Studio**<br> **Surface Studio 2**<br>              | Enable or disable data            | N/A: No USB-C port on device                                                                                                                                   | USBPortEnabled (default)<br><br> USBPortHWDisabled                          | 370-379  |
| **Surface Laptop SE**<br>**Surface Pro 7**<br>**Surface Pro 7+**<br>**Surface Pro 9 5G**<br>**Surface Go**<br>**Surface Go 2**<br>**Surface Laptop Go**<br>**Surface Laptop Go 2**<br>**Surface Laptop Go 3**<br>**Surface Laptop 3** (Intel only)<br>**Surface Laptop 4** (Intel only)<br>**Surface Laptop 5** (Intel only)<br> **Surface Studio 2+**| Enable or disable data            |  Enabled data, display out, and power delivery<br><br>Disabled data, display out, and power delivery                                                            |  USBPortEnabled (default)<br><br>USBPortHWDisabled                          | 370-379  |
| **Surface Book 2** and later <br>                                                                                                                        | Base USB ports are always enabled | Base USB ports are always enabled                                                                                                                              | n/a                                                                        |          |
| **Surface Book** with Performance Base<br>**Surface Book**                                                                                                               | Base USB ports are always enabled | N/A: No USB-C port on device                                                                                                                                   | n/a                                                                        |          |

## SEMM Modes

 In SEMM, Mode 0 and Mode 1 refer to the two operational modes:
 
1. **Mode 0 (Deployment Mode):**
   - This is the default mode when SEMM is not configured.
   - In this mode, all firmware settings are available to the user, and there are no restrictions.
   - Devices can be freely enrolled into or unenrolled from SEMM when they are in Mode 0.
 
2. **Mode 1 (Enterprise Mode):**
   - This mode is activated when a device is enrolled into SEMM using a configuration package.
   - In Enterprise Mode, the firmware settings defined by the SEMM configuration package are applied, and users cannot modify these settings.
   - To make changes to the firmware settings or to unenroll a device from SEMM, the device must be reverted to Mode 0, which requires the SEMM certificate and the appropriate tools.
 
The ability to switch between these modes provides flexibility for IT administrators. You can set up devices with the necessary restrictions for enterprise use (Mode 1) and revert to a more open configuration (Mode 0) when needed, such as during device setup, maintenance, or decommissioning.
 
## Dynamic USB-C disablement for Surface Thunderbolt 4 Dock

Dynamic USB-C disablement allows IT admins to configure Surface Laptop Studio 2 devices to switch from Mode 1 to Mode 0 without deploying a new package or restarting the device.  
 
In this scenario, when Surface Laptop Studio 2 is connected to an authorized Surface Thunderbolt 4 Dock, the device is subject to the firmware settings defined by the SEMM configuration package. For example, IT admins can configure firmware settings as follows:
 
- Prevent users from transferring data via USB C but retain USB-C functionality to connect to an external display or power the device. This is configured by enabling **UsbPortDataDisabled** in PowerShell scripts targeted to Surface Laptop Studio 2 devices via Microsoft Configuration Manager.
- Prevent all USB-C functiontality. This is configured by enabling **UsbPortHwDisabled** in PowerShell scripts targeted to Surface Laptop Studio 2 devices via Microsoft Configuration Manager.

Dynamic USB-C disablement lets users resume normal use of USB-C functionality if they take the device home or outside the managed corporate environment.  Currently exclusive to Surface Laptop Studio 2 devices, the functionality will available for eligible Surface devices in the future.  


