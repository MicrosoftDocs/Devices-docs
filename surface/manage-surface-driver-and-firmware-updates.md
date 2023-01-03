---
title: Manage and deploy Surface driver and firmware updates 
description: This article provides links to downloadable packages containing driver and firmware updates for Surface devices and explains available management and deployment solutions.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
manager: frankbu
ms.localizationpriority: medium
ms.prod: surface
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 11/03/2022
appliesto:
- Windows 10
- Windows 11
---

# Manage and deploy Surface driver and firmware updates

How you manage Surface driver and firmware updates may vary depending on your environment and organizational requirements. In larger organizations, IT admins typically stage deployments internally and allocate time to test upgrades before rolling them out to user devices.

> [!NOTE]
> This article is intended for IT professionals and technical support agents and applies to Surface devices only. If you're looking for help to install Surface updates or firmware on a home device, see [Download drivers and firmware for Surface](https://support.microsoft.com/help/4023505).

While enterprise-grade software distribution solutions continue to evolve, the business rationale for centrally managing  updates remains the same: Maintain the security of Surface devices and keep them updated with the latest operating system and feature improvements. This IT practice is essential for sustaining a stable production environment and making sure that users aren't blocked from being productive.

## What's in Surface driver and firmware updates

Windows Installer .msi files contain all the required cumulative driver and firmware updates for Surface devices. Update packages may include some or all the following components:

- Wi-Fi and LTE
- Video
- Solid-state drive
- System aggregator module (SAM)
- Battery
- Keyboard controller
- Embedded controller (EC)
- Management engine (ME)
- Unified extensible firmware interface (UEFI)

## Download .msi files

This section provides direct links to downloadable packages containing driver and firmware updates for Surface devices. 

1. Select Windows 10 or Windows 11 as appropriate. 
2. For devices with multiple .msi files, select the .msi file name that matches the Surface model and version of Windows deployed in your organization.  


| Surface device                                                                                                                                        | Downloadable .msi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Pro**                                                                                                                                       | - [Surface Pro 9 with Intel processor](https://www.microsoft.com/download/details.aspx?id=104680)<br>- [Surface Pro 8](https://www.microsoft.com/en-us/download/details.aspx?id=103503)<br>- [Surface Pro 7+ and Surface Pro 7+ (LTE)](https://www.microsoft.com/en-us/download/details.aspx?id=102633)<br>- [Surface Pro 7](https://www.microsoft.com/download/details.aspx?id=100419)<br>- [Surface Pro 6](https://www.microsoft.com/download/details.aspx?id=57514)<br>- [Surface Pro 5 (LTE)](https://www.microsoft.com/download/details.aspx?id=56278)<br>- [Surface Pro 5 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=55484)<br>- [Surface Pro 4](https://www.microsoft.com/download/details.aspx?id=49498)<br>- [Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826)<br>- [Surface Pro 2](https://www.microsoft.com/download/details.aspx?id=49042)<br>- [Surface Pro](https://www.microsoft.com/download/details.aspx?id=49038) |
| **Surface Laptop**                                                                                                                                    | - [Surface Laptop Go](https://www.microsoft.com/download/details.aspx?id=102261)<br>- [Surface Laptop Go 2](https://www.microsoft.com/download/details.aspx?id=104251)<br>- [Surface Laptop 5](https://www.microsoft.com/download/details.aspx?id=104679)<br>- [Surface Laptop 4 with Intel Processor](https://www.microsoft.com/download/details.aspx?id=102924)<br>- [Surface Laptop 4 with AMD Processor](https://www.microsoft.com/download/details.aspx?id=102923)<br>- [Surface Laptop 3 with Intel Processor](https://www.microsoft.com/download/details.aspx?id=100429)<br>- [Surface Laptop 3 with AMD Processor](https://www.microsoft.com/download/details.aspx?id=100428)<br>- [Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)<br>- [Surface Laptop](https://www.microsoft.com/en-us/download/details.aspx?id=55489)                                                                                                                                                                                    |
| **Surface Laptop Studio**                                                                                                                             | - [Surface Laptop Studio](https://www.microsoft.com/en-us/download/details.aspx?id=103505)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Surface Book**                                                                                                                                      | - [Surface Book 3](https://www.microsoft.com/download/details.aspx?id=101315)<br>- [Surface Book 2](https://www.microsoft.com/download/details.aspx?id=56261)<br>- [Surface Book](https://www.microsoft.com/download/details.aspx?id=49497)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Surface Go**                                                                                                                                        | - [Surface Go 3](https://www.microsoft.com/en-us/download/details.aspx?id=103504)<br>- [Surface Go 2](https://www.microsoft.com/download/details.aspx?id=101304)<br>- [Surface Go (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=57439)<br>- [Surface Go (LTE)](https://www.microsoft.com/download/details.aspx?id=57601)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Surface Studio**                                                                                                                                    | - [Surface Studio 2+](https://www.microsoft.com/download/details.aspx?id=104681)<br>- [Surface Studio 2](https://www.microsoft.com/download/details.aspx?id=57593)<br>- [Surface Studio](https://www.microsoft.com/download/details.aspx?id=54311)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Surface 3**                                                                                                                                         | - [Surface 3 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=49040)<br>- [Surface 3 (LTE) - ATT](https://www.microsoft.com/download/details.aspx?id=49039)<br>- [Surface 3 (LTE) - Verizon](https://www.microsoft.com/download/details.aspx?id=49920)<br>- [Surface 3 (LTE) - North America Carrier Unlocked](https://www.microsoft.com/download/details.aspx?id=49037)<br>- [Surface 3 (LTE) - Outside of North America and Y!mobile in Japan](https://www.microsoft.com/download/details.aspx?id=49041)                                                                                                                                                                                                                                                                                                                                                   |
| **Surface Hub running**  [**Windows 10 Pro or Windows 10 Enterprise**](/surface-hub/surface-hub-2s-migrate-os) | - [Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Surface Hub running Windows 10 Teams 2020 Update**                                                                                                  | - See [Manage Windows updates on Surface Hub](/surface-hub/manage-windows-updates-for-surface-hub)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Surface Dock 2**                                                                                                                                    | - [Surface Dock 2](https://www.microsoft.com/download/details.aspx?id=101317)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

 

> [!TIP]
> For earlier devices that include separate files for different Windows versions, select the .msi file name that matches the Surface model and version of Windows. The .msi file name includes the minimum supported Windows build number that's required to install the drivers and firmware. For example, to update a Surface Book 2 that has build 18362 of Windows 10, choose **SurfaceBook2_Win10_18362_19.101.13994.msi.** For a Surface Book 2 that has build 16299 of Windows 10, choose **SurfaceBook2_Win10_16299_1803509_3.msi**.

## Central update management in commercial environments

Tools for managing devices, including driver and firmware updates, are included in [Microsoft Endpoint Manager](/mem/). Microsoft Endpoint Manager includes Microsoft Intune, Windows Autopilot, and Microsoft Endpoint Configuration Manager.

### Manage updates with Configuration Manager and Intune

Microsoft Endpoint Manager is the recommended solution for large organizations to manage Surface updates. Configuration Manager allows you to synchronize and deploy Surface firmware and driver updates with the Configuration Manager client. Integration with Intune lets you see all your managed, co-managed, and partner-managed devices in one place. The Microsoft Surface Management Portal is a centralized place in the Microsoft Endpoint Manager admin center where you can self-serve, manage, and monitor your organization's Intune-managed Surface devices at scale.

For more information, see the following resources:

- [Manage Surface driver updates in Configuration Manager](/mem/configmgr/sum/deploy-use/surface-drivers)
- [Deploy applications with Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)
- [Overview of Microsoft Surface Management Portal](/mem/intune/fundamentals/surface-management-portal)
- [Configuration Manager documentation](/mem/configmgr/)
- [Intune documentation](/mem/intune/)

### Manage updates with Microsoft Deployment Toolkit

The Microsoft Deployment Toolkit (MDT) is a free tool for automating Windows deployment. It uses the task sequence engine from Configuration Manager, and can also install drivers and software updates during the deployment.

For more information, see the following resources:

- [Prepare for deployment with MDT](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [MDT documentation](/configmgr/mdt/)

### Windows PE and Surface firmware and drivers

Configuration Manager and MDT both use the Windows Preinstallation Environment (Windows PE) during the deployment process. Windows PE supports only a limited set of basic drivers such as network adapters and storage controllers. Drivers for Windows components that aren't part of Windows PE might produce errors. You can prevent such errors by configuring the deployment process to use only the required drivers during the Windows PE phase.

## Supported devices

Downloadable .msi files are available for Surface Pro 2 and later devices (except Surface Pro X, which runs Windows 10 on ARM processor).

## Managing firmware with DFCI

By having Device Firmware Configuration Interface (DFCI) profiles [built into Intune](/intune/configuration/device-firmware-configuration-interface-windows), Surface UEFI management extends the modern management stack down to the UEFI hardware level. DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings (including startup options and built-in peripherals), and lays the groundwork for advanced security scenarios in the future. For more information, see the following resources:

- [Manage DFCI on Surface devices](surface-manage-dfci-guide.md)
- [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## Best practices for update deployment processes

To maintain a stable environment, we strongly recommend that you keep parity with the most recent version of Windows 10.  For best practice recommendations, see [Prepare servicing strategy for Windows client updates](/windows/deployment/update/waas-deployment-rings-windows-10-updates).

### Surface .msi naming convention

Since August 2019, .msi files are using the following naming convention:

- *Product*_*Windows release*_*Windows build number*_*Version number*_*Revision of version number (typically zero)*.

**Example**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

This file name provides the following information:

- **Product:** SurfacePro6
- **Windows release:** Win10
- **Build:** 18362
- **Version:** 19.073.44195 – Version number shows the date and time that the file was created, as follows:
  - **Year:** 19 (2019)
  - **Month and week:** 073 (third week of July)
  - **Minute of the month:** 44195
- **Revision of version:** 0 (first release of this version)

### Legacy Surface .msi naming convention

Legacy .msi files (files that were built before August 2019) followed the same overall naming formula but used a different method to derive the version number.

**Example**

- SurfacePro6_Win10_16299_1900307_0.msi

This file name provides the following information:

- **Product:** SurfacePro6
- **Windows release:** Win10
- **Build:** 16299
- **Version:** 1900307 – Version number shows the date that the file was created and its position in the release sequence, as follows:
  - **Year:** 19 (2019)
  - **Number of release:** 003 (third release of the year)
  - **Product version number:** 07 (Surface Pro 6 is officially the seventh version of Surface Pro)
- **Revision of version:** 0 (first release of this version)

## Learn more

- [Prepare servicing strategy for Windows client updates](/windows/deployment/update/waas-deployment-rings-windows-10-updates)
- [Manage Surface driver updates in Configuration Manager](/mem/configmgr/sum/deploy-use/surface-drivers)
- [Deploy applications with Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)
- [Manage DFCI on Surface devices](surface-manage-dfci-guide.md)
