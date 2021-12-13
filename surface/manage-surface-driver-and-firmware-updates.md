---
title: Manage and deploy Surface driver and firmware updates 
description: This article provides links to downloadable packages containing driver and firmware updates for Surface devices and explains available management and deployment solutions.
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: 
manager: laurawi
keywords: Surface, Surface Pro 8, Surface Go, Surface Laptop, Surface Studio, Surface Pro 3, firmware, update, device, manage, deploy, driver, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 12/13/2021
---

# Manage and deploy Surface driver and firmware updates

How you manage Surface driver and firmware updates varies depending on your environment and organizational requirements. On Surface devices, firmware is exposed to the operating system as a driver and is visible in Device Manager. This enables device firmware and drivers to be automatically updated using Windows Update or Windows Update for Business. Although this simplified approach may be feasible for startups and small or medium-sized businesses, larger organizations typically need IT admins to distribute updates internally. This may involve comprehensive planning, application compatibility testing, and piloting and validating updates before final approval and distribution across the network.

> [!NOTE]
> This article is intended for technical support agents and IT professionals and applies to Surface devices only. If you're looking for help to install Surface updates or firmware on a home device, see [Update Surface firmware and Windows 10](https://support.microsoft.com/help/4023505).

While enterprise-grade software distribution solutions continue to evolve, the business rationale for centrally managing  updates remains the same: Maintain the security of Surface devices and keep them updated with the latest operating system and feature improvements. This is essential for sustaining a stable production environment and making sure that users aren't blocked from being productive. This article provides an overview of recommended tools and processes for larger organizations to accomplish these goals.

## Central update management in commercial environments

Microsoft has streamlined tools for managing devices – including driver and firmware updates -- into a single unified experience that is named [Microsoft Endpoint Manager admin center](https://devicemanagement.microsoft.com/) and is accessed from [devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home).

## Downloadable Surface update packages

Specific versions of Windows 10 have separate .msi files, each containing all the required cumulative driver and firmware updates for Surface devices. Update packages may include some or all the following components:

- Wi-Fi and LTE
- Video
- Solid state drive
- System aggregator module (SAM)
- Battery
- Keyboard controller
- Embedded controller (EC)
- Management engine (ME)
- Unified extensible firmware interface (UEFI)

## Download .msi files

This section provides direct links to downloadable packages containing driver and firmware updates. 

### Surface Pro

- [Surface Pro 8](https://www.microsoft.com/en-us/download/details.aspx?id=103503)
- [Surface Pro 7+ and Surface Pro 7+ (LTE)](https://www.microsoft.com/en-us/download/details.aspx?id=102633)
- [Surface Pro 7](https://www.microsoft.com/download/details.aspx?id=100419)
- [Surface Pro 6](https://www.microsoft.com/download/details.aspx?id=57514)
- [Surface Pro 5 (LTE)](https://www.microsoft.com/download/details.aspx?id=56278)
- [Surface Pro 5 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=55484)
- [Surface Pro 4](https://www.microsoft.com/download/details.aspx?id=49498)
- [Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826)
- [Surface Pro 2](https://www.microsoft.com/download/details.aspx?id=49042)
- [Surface Pro](https://www.microsoft.com/download/details.aspx?id=49038)

### Surface Laptop

- [Surface Laptop Go](https://www.microsoft.com/download/details.aspx?id=102261)
- [Surface Laptop 4 with Intel Processor](https://www.microsoft.com/download/details.aspx?id=102924)
- [Surface Laptop 4 with AMD Processor](https://www.microsoft.com/download/details.aspx?id=102923)
- [Surface Laptop 3 with Intel Processor](https://www.microsoft.com/download/details.aspx?id=100429)
- [Surface Laptop 3 with AMD Processor](https://www.microsoft.com/download/details.aspx?id=100428)
- [Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)
- [Surface Laptop](https://www.microsoft.com/en-us/download/details.aspx?id=55489)

### Surface Laptop Studio

- [Surface Laptop Studio](https://www.microsoft.com/en-us/download/details.aspx?id=103505)

### Surface Book

- [Surface Book 3](https://www.microsoft.com/download/details.aspx?id=101315)
- [Surface Book 2](https://www.microsoft.com/download/details.aspx?id=56261)
- [Surface Book](https://www.microsoft.com/download/details.aspx?id=49497)

### Surface Go

- [Surface Go 3](https://www.microsoft.com/en-us/download/details.aspx?id=103504)
- [Surface Go 2](https://www.microsoft.com/download/details.aspx?id=101304)
- [Surface Go (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=57439)
- [Surface Go (LTE)](https://www.microsoft.com/download/details.aspx?id=57601)

### Surface Studio

- [Surface Studio 2](https://www.microsoft.com/download/details.aspx?id=57593)
- [Surface Studio](https://www.microsoft.com/download/details.aspx?id=54311)

### Surface 3

- [Surface 3 (Wi-Fi)](https://www.microsoft.com/download/details.aspx?id=49040)
- [Surface 3 (LTE) - ATT](https://www.microsoft.com/download/details.aspx?id=49039)
- [Surface 3 (LTE) - Verizon](https://www.microsoft.com/download/details.aspx?id=49920)
- [Surface 3 (LTE) - North America Carrier Unlocked](https://www.microsoft.com/download/details.aspx?id=49037)
- [Surface 3 (LTE) - Outside of North America and Y!mobile in Japan](https://www.microsoft.com/download/details.aspx?id=49041)

### Surface Hub

If you have migrated Surface Hub to run Windows 10 Pro or Windows 10 Enterprise, see the following download:

- [Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974)

> [!TIP]
> For earlier devices that include separate files for different Windows versions, select the .msi file name that matches the Surface model and version of Windows. The .msi file name includes the minimum supported Windows build number that's required to install the drivers and firmware. For example, to update a Surface Book 2 that has build 18362 of Windows 10, choose **SurfaceBook2_Win10_18362_19.101.13994.msi.** For a Surface Book 2 that has build 16299 of Windows 10, choose **SurfaceBook2_Win10_16299_1803509_3.msi**.

## Manage updates with Configuration Manager and Intune

Microsoft Endpoint Configuration Manager allows you to synchronize and deploy Surface firmware and driver updates with the Configuration Manager client. Integration with Microsoft Intune lets you see all your managed, co-managed, and partner-managed devices in one place. This is the recommended solution for large organizations to manage Surface updates.

For detailed steps, see the following resources:

- [Manage Surface driver updates in Configuration Manager](manage-surface-driver-updates-configuration-manager.md)
- [Deploy applications with Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
- [Endpoint Configuration Manager documentation](/configmgr/)

### Manage updates with Microsoft Deployment Toolkit

The Microsoft Deployment Toolkit (MDT) is included in Endpoint Configuration Manager. It contains optional deployment tools that you may want to use, depending on your environment. These include the Windows Assessment and Deployment Kit (Windows ADK), Windows System Image Manager (Windows SIM), Deployment Image Servicing and Management (DISM), and User State Migration Tool (USMT). You can download the latest version of MDT from the [Microsoft Deployment Toolkit download page](https://www.microsoft.com/download/details.aspx?id=54259).

For detailed steps, see the following resources:

- [Microsoft Deployment Toolkit documentation](/configmgr/mdt/)
- [Deploy Windows 10 with the Microsoft Deployment Toolkit](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](deploy-windows-10-to-surface-devices-with-mdt.md)

Surface driver and firmware updates are packaged as Windows Installer (*.msi) files. To deploy these Windows Installer packages, you can use Endpoint Configuration Manager or MDT. For information about how to select the correct .msi file for a device and operating system, refer to the guidance in the following sections about downloading .msi files.

For instructions about how to deploy updates by using Endpoint Configuration Manager, see [Deploy applications with Configuration Manager](/configmgr/apps/deploy-use/deploy-applications). For instructions about how to deploy updates by using MDT, see [Deploy a Windows 10 image using MDT](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).

**WindowsPE and Surface firmware and drivers**

Endpoint Configuration Manager and MDT both use the Windows Preinstallation Environment (WindowsPE) during the deployment process. WindowsPE supports only a limited set of basic drivers such as those for network adapters and storage controllers. Drivers for Windows components that are not part of WindowsPE might produce errors. As a best practice, you can prevent such errors by configuring the deployment process to use only the required drivers during the WindowsPE phase.

### Endpoint Configuration Manager

Starting in Endpoint Configuration Manager, you can synchronize and deploy Microsoft Surface firmware and driver updates by using the Configuration Manager client. For additional information, see KB 4098906, [How to manage Surface driver updates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).

## Supported devices

Downloadable .msi files are available for Surface Pro 2 and later devices (except Surface Pro X which runs Windows 10 on ARM).

## Managing firmware with DFCI

By having Device Firmware Configuration Interface (DFCI) profiles [built into Intune](/intune/configuration/device-firmware-configuration-interface-windows), Surface UEFI management extends the modern management stack down to the UEFI hardware level. DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings (including startup options and built-in peripherals), and lays the groundwork for advanced security scenarios in the future. For more information, see the following:

- [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md)
- [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).

## Best practices for update deployment processes

To maintain a stable environment, we strongly recommend that you maintain parity with the most recent version of Windows 10.  For best practice recommendations, see [Build deployment rings for Windows 10 updates](/windows/deployment/update/waas-deployment-rings-windows-10-updates).

### Surface .msi naming convention

Since August 2019, .msi files are using the following naming convention:

- *Product*_*Windows release*_*Windows build number*_*Version number*_*Revision of version number (typically zero)*.

**Example**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

This file name provides the following information:

- **Product:** SurfacePro6
- **Windows release:** Win10
- **Build:** 18362
- **Version:** 19.073.44195 – This shows the date and time that the file was created, as follows:
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
- **Version:** 1900307 – This shows the date that the file was created and its position in the release sequence, as follows:
  - **Year:** 19 (2019)
  - **Number of release:** 003 (third release of the year)
  - **Product version number:** 07 (Surface Pro 6 is officially the seventh version of Surface Pro)
- **Revision of version:** 0 (first release of this version)

## Learn more

- [Download drivers and firmware for Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [How to manage Surface driver updates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [Deploy applications with Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
- [Endpoint Configuration Manager documentation](/configmgr/)
- [Microsoft Deployment Toolkit documentation](/configmgr/mdt/)
- [Deploy Windows 10 with the Microsoft Deployment Toolkit](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](deploy-windows-10-to-surface-devices-with-mdt.md)  
- [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md)
- [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).
- [Build deployment rings for Windows 10 updates](/windows/deployment/update/waas-deployment-rings-windows-10-updates)
