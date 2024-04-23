---
title: Configure Surface devices with PowerShell 
description: This article describes the PowerShell scripts built into the Surface IT Toolkit.
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
---

# Configure Surface devices with PowerShell 

The Surface IT Toolkit includes a centralized library of scripts is designed to enhance the management capabilities of IT admins, providing precision control over Surface devices, Docks, and Hubs. Whether you’re enrolling new devices into the Surface Enterprise Management Mode (SEMM), managing UEFI firmware settings, or ensuring devices are compliant with your organization's policies, these scripts offer an alternative to using the UI-based UEFI Configurator tool. 

To access the scripts, open **Surface IT Toolkit**, select **UEFI Configurator** > **PowerShell Scripts** and copy the scripts into your dev environment. 

## Surface Device Scripts

This collection enables IT admins to configure SEMM on individual Surface devices efficiently. From setting up new devices to managing UEFI settings and permissions, these scripts ensure that the devices adhere to enterprise security standards.

**Key Scripts**:

- **Configure SEMM**: For creating configuration packages tailored to specific organizational requirements.
- **Additional Scripts**: View scripts for various advanced management tasks, as shown in the following table. 

| Script                    | Summary                                                         |
|---------------------------|-----------------------------------------------------------------|
| ApplyProvisioningPackage  | Used to apply existing Owner and Permissions packages, determining who has authority to make changes to UEFI settings. |
| ApplySettingsPackage      | Applies an existing UEFI settings package to a device.         |
| CreateOwnerPackage        | Generates an Owner package setting organizational certificate-based ownership of the UEFI. |
| CreateOwnerUpgradePackage | Creates a package to replace an expiring certificate on an already-enrolled device. |
| CreatePermissionPackages  | Produces a package that sets permissions for UEFI setting changes. |
| CreateSettingsPackage     | Generates a package containing desired UEFI settings.           |
| CreateTestCertificates    | Creates self-signed certificates for SEMM testing in non-production environments. |
| CurrentSettings           | Displays the UEFI settings currently configured on the host device. |
| ResetSEMM                 | Constructs a reset package to remove SEMM from a device.       |
| ShowSettingsOptions       | Shows available UEFI settings that can be configured.          |
| VerifySettings            | Verifies UEFI settings against those configured on the host device and in applied packages. |



## Surface Dock Scripts

Facilitate the integration of Surface Docks into your device management framework. These scripts offer an alternative to the UI-based UEFI Configurator tool, for precison control of Surface Docks connected to your Surface devices.


### Surface Thunderbolt 4 Dock Scripts

Built for Thunderbolt 4 Docks, these PowerShell scripts offer policy creation, provisioning, and dynamic USB-C disablement.

| Script                                  | Summary                                                                                           |
|-----------------------------------------|---------------------------------------------------------------------------------------------------|
| CreateSurfaceThunderbolt(TM)4DockCertificates | Generates self-signed certificates for testing SEMM with Surface Thunderbolt™ 4 Dock in non-production environments. |
| ResetSEMM - Thunderbolt(TM)4Dock        | Creates a package to remove SEMM from a Surface Thunderbolt™ 4 Dock.                               |
| VerifyDockSettings                      | Displays the settings currently applied to the connected Surface Thunderbolt™ 4 Dock.              |



### Surface Dock 2 Scripts

Built for Surface Dock 2, these PowerShell scripts offer management for port and firmware settings.

| Script                      | Summary                                                                                   |
|-----------------------------|-------------------------------------------------------------------------------------------|
| CreateSurfaceDock2Certificates | Generates self-signed certificates to test SEMM for Surface Dock 2 in non-production environments. |
| Reset SEMM                  | Creates a reset package that can be used to remove SEMM from a Surface Dock 2.            |
| VerifyDockSettings          | Displays the applied settings of the connected Surface Dock 2.                            |


## Why use Surface PowerShell scripts?

- **Automation**: Automate repetitive tasks to save time and reduce the likelihood of errors during device setup and management.
- **Customization**: Tailor the device settings to meet the unique needs of your organization.
- **Security**: Maintain high security by controlling UEFI settings and SEMM configurations.
- **Documentation**: Each script comes with detailed comments to guide you through usage and deployment.

The PowerShell Scripts within the Surface IT Toolkit's UEFI Configurator offer a robust solution for the fine-tuned management of Surface devices and accessories, aligning with enterprise security, compliance, and operational efficiency goals.