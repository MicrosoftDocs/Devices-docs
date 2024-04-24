---
title: Configure UEFI settings for Surface devices
description: This article describes how to secure and manage UEFI settings for Surface devices deployed across your organization using Surface Enterprise Management Mode (SEMM).
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

# Configure UEFI settings for Surface devices

This article describes how to secure and manage Unified Extensible Firmware Interface (UEFI) settings for Surface devices deployed across your organization using  Surface UEFI Configurator and Surface Enterprise Management Mode (SEMM). The Surface UEFI Configurator, no longer available as a separate download, is now included in the new Surface IT Toolkit. 

## UEFI settings for SEMM-managed Surface devices

With SEMM, IT admins can manage hardware components at the firmware level. For example, you can turn off hardware components like cameras, microphones, and USB ports for security purposes. For a complete list of available settings, see [Surface UEFI SEMM settings reference.](surface-it-toolkit-semm-uefi-settings.md)

## Create a Surface UEFI configuration package

The Surface UEFI configuration package serves the dual purpose of applying newly configured UEFI settings to SEMM-managed Surface devices and enrolling them in SEMM. Creating this package necessitates a SEMM signing certificate to secure the UEFI settings on each device. For more information, see [SEMM certificate requirements](/surface/surface-enterprise-management-mode#semm-certificate-requirements).

## Protect UEFI settings with password

We strongly recommend setting a password when creating UEFI configuration packages. Firmware controls the initial operations of the hardware before the operating system loads. If unauthorized users access UEFI settings, they could potentially disable security features or make changes detrimental to the security and functionality of the device.

:::image type="content" source="images/ueficonfig-set-password.png" alt-text="Screenshot showing the addition of a password to protect UEFI settings from unauthorized persons."::: 

## UEFI Front Page

In the **UEFI Front Page** section, you can toggle the following categories **Security**, **Devices**, **Boot**, **Date/Time** to control which pages are available to end users who boot into Surface UEFI. (For more information about Surface UEFI settings, see [Manage Surface UEFI settings](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).) 

:::image type="content" source="images/ueficonfig-front-page.png" alt-text="Screenshot showing UEFI Front Page components."::: 

To create a Surface UEFI configuration package:

1. Open **Surface IT Toolkit**, select **UEFI Configurator** > **Configure Surface Device**.
2. Under **Import Certificate Protection**, select  **Add** to add your exported certificate file with private key (.pfx). Select **Next**.
:::image type="content" source="images/ueficonfig-start.png" alt-text="Screenshot of UEFI Configuration.":::
3. Select the devices to be configured. Choose from your Managed Devices or go to All Devices to select your device and model. Select **Next**.
:::image type="content" source="images/ueficonfig-select-devices.png" alt-text="Screenshot of device selection for UEFI Configuration.":::
4. In the Device Configuration Settings page, select the components you wish to configure. When finished, select **Next**.
:::image type="content" source="images/ueficonfig-device-config-settings.png" alt-text="Screenshot of Device Configuration Settings page.":::
5. When complete, select **Finish**
:::image type="content" source="images/ueficonfig-complete-package.png"alt-text="Screenshot of completed configuration for the Device package.":::

> [!TIP]
> Record the certificate thumbprint characters displayed on this page, as shown in Figure 6. You will need these characters to confirm enrollment of new Surface devices in SEMM. Click **End** to complete package creation and close Microsoft Surface UEFI Configurator.

6. Review your changes, select **Choose Folder** to save the UEFI configuration package, and select **Create**.
:::image type="content" source="images/ueficonfig-create-package.png"alt-text="Screenshot of Device Package creation page.":::

7. When finished, go to your selected folder to retrieve the package. This example package modifies a single UEFI setting, resulting in two files:

    - A SEMM enrollment package you can deploy to one or more devices.
    - A Reset package used to unenroll a SEMM-managed device.

:::image type="content" source="images/ueficonfig-package-contents.png"alt-text="Screenshot of UEFI configuration package files.":::

## Enroll a Surface device in SEMM

When the Surface UEFI configuration package is executed, the SEMM certificate and Surface UEFI configuration files are staged in the firmware storage of the Surface device. When the Surface device reboots, Surface UEFI processes these files and begins the process of applying the Surface UEFI configuration or enrolling the Surface device in SEMM.

Before you enroll a Surface device in SEMM, ensure that you have the last two characters of the certificate thumbprint on hand. You need these characters to confirm the device’s enrollment.

To enroll a Surface device in SEMM with a Surface UEFI configuration package: 

1. Run the Surface UEFI configuration package .msi file on the Surface device you want to enroll in SEMM. This provisions the Surface UEFI configuration file in the device’s firmware.
2. Select the **I accept the terms in the License Agreement** check box to accept the End User License Agreement (EULA), and select **Install** to begin the installation process.
3. Select **Finish** to complete the Surface UEFI configuration package installation and restart the Surface device when you're prompted to do so.
4. Surface UEFI loads the configuration file and determines that SEMM isn't enabled on the device. Surface UEFI begins the SEMM enrollment process, as follows:
   - Surface UEFI verifies that the SEMM configuration file contains a SEMM certificate.
   - Surface UEFI prompts you to enter the last two characters of the certificate thumbprint to confirm enrollment of the Surface device in SEMM.  
5. The Surface device is now enrolled in SEMM.

You can verify if a Surface device is successfully enrolled in SEMM by looking for **Microsoft Surface Configuration Package** in **Programs and Features**  or in the events stored in the **Microsoft Surface UEFI Configurator** log, found under **Applications and Services Logs** in Event Viewer.

## Configure more Surface UEFI settings

After a device is enrolled in SEMM, you can run other Surface UEFI configuration packages signed with the same SEMM certificate to apply new Surface UEFI settings. These settings are applied automatically the next time the device boots, without any interaction from the user. You can use application deployment solutions like Microsoft Endpoint Configuration Manager to deploy Surface UEFI configuration packages to Surface devices to change or manage the settings in Surface UEFI.

For more information about how to deploy Windows Installer (.msi) files with Configuration Manager, see [Deploy and manage applications with Microsoft Endpoint Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications).