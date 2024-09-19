---
title: Migrate to Windows 10/11 Pro or Enterprise on Surface Hub 2S
description: How to migrate from Windows 10 Team on Surface Hub 2S to Windows 10/11 Pro or Windows 10/11 Enterprise.
ms.service: surface-hub
author: coveminer
ms.author: dpandre
manager: frankbu
ms.topic: how-to
ms.date: 09/18/2024
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S
- Windows 10
- Windows 11
---


# Migrate to Windows 10/11 Pro or Enterprise on Surface Hub 2S

- [Article version history](#version-history)

Surface Hub 2S is designed to facilitate collaboration in meeting-room environments. Instead, you can run Windows 10/11 Pro or Enterprise to use your Surface Hub 2S like any other PC. For Surface Hub 3, see [Migrate to Windows 11 Pro or Enterprise on Surface Hub 3](surface-hub-3-migrate-os.md).

> [!IMPORTANT]
> This migration process requires you to follow a specific procedure described in this article. Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before continuing.

> [!NOTE]
> When you install Windows 10/11 Pro or Enterprise, you need a new license distinct from the existing license provided with the device.

Start the migration using a separate PC and the downloadable [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703). The Surface IT Toolkit combines various standalone applications, including the *Surface UEFI Configurator* tool, into a modern, self-updating desktop appllication. Use UEFI Configurator to create a package with a new UEFI setting for Surface Hub 2S.  

Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM). It enables centralized management of firmware settings on Surface devices in a corporate environment. For more information, see [Get started with Surface Enterprise Management Mode](/surface/surface-enterprise-management-mode).

## Solution components

- Surface Hub 2S running Windows 10 Team
- Separate PC running Windows 11 (or Windows 10)
- Surface IT Toolkit
- Surface UEFI Configurator tool to create the SEMM package
- Windows 10/11 Pro or Enterprise OS image, version 20H2 or later
- Two USB drives with 16 GB of storage, FAT32 format
- Windows Installer (MSI) file containing drivers and firmware for Windows 10/11 Pro and Enterprise on Surface Hub 2S 
- Internet connection
- Imaging solution (optional)

## Migration and installation workflow summary

| Step  | Action                                                                                                 | Summary                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Verify the UEFI version on Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s)                                  | The UEFI version must be version *694.2938.768.0* or later.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Install Surface IT Toolkit and Surface Hub 2S drivers and firmware](#download-surface-it-toolkit-and-surface-hub-2s-drivers-and-firmware)                             | On a separate PC, download and install [Surface IT Tookit](hhttps://www.microsoft.com/download/details.aspx?id=46703). Also, download the [Drivers and Firmware for Windows 10/11 Pro and Enterprise OS on Surface Hub 2S and Surface Hub 3 MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</a> Save this package for use in step 5. |
| 3 | [Prepare the SEMM certificate](#prepare-the-semm-certificate)                                                                          | Prepare the certificate required to run the UEFI Configurator, or use your current certificate.                                                                                                                                                                                                                                                                                                      |
| 4 | [Create a SEMM package](#create-a-semm-package)                                                                               | Open Surface IT Toolkit and start Surface UEFI Configurator to create a SEMM package on a USB drive. This package will contain the configuration file you must apply on Surface Hub 2S.                                                                                                                                                                                         |
| 5 | [Load a USB flash drive with Windows 11 or Windows 10 image, the SEMM package, and drivers and firmware](#load-a-usb-flash-drive-with-a-windows-11-or-windows-10-image-semm-package-and-surface-hub-2s-drivers-and-firmware) | Create a USB drive that contains a Windows 11 or Windows 10 image. In this example, the drive is named *BOOTME*. Add the drivers and firmware for Windows 10/10 Pro and Enterprise OS on Surface Hub 2S (Step 2) and the SEMM package file (Step 4) to the *BOOTME* drive.                                                                                                                                                                                                  |
| 6 | [Update the UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use the *BOOTME* drive to boot Surface Hub 2S to the UEFI menu and install the SEMM package.|
| 7 | [Install Windows 10/11 Pro or Enterprise.](#install-windows-1011-pro-or-enterprise)                                        | Use the *BOOTME* drive to install Windows 10/11 Pro or Enterprise version *20H2* or later.                                                                                                                                                                                                                                                                                 |
| 8 | [Install drivers and firmware for Windows 10/11 Pro and Enterprise.](#install-surface-hub-2s-drivers-and-firmware)                                        | To ensure that your device has all the latest updates and drivers, install the [Drivers and firmware for Windows 10/11 Pro and Enterprise OS on Surface Hub 2S MSI file](https://www.microsoft.com/download/details.aspx?id=101974).                                                                                                                                                                                                                                                                                 |
| 9 | [Configure Surface Hub 2S as a personal productivity device.](#configure-recommended-settings)                                        |  Enable the recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.                                                                                                                                                                                                                                                                    |

### Verify the UEFI version on Surface Hub 2S

Before you migrate Surface Hub from Windows 10 Team to Windows 10/11 Desktop, you need UEFI version *694.2938.768.0* or later.

**To verify the UEFI version on your system:**

1. On the Surface Hub 2S Welcome screen, select **Start**, and then open the Surface app (**All Apps** > **Surface**).

1. Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.

   - If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.

       ![Screenshot shows the "Your Surface" page in the Surface app.](images/shm-fig1.png)

   - If the UEFI version is earlier than version *694.2938.768.0*, use one of the following methods to get a newer version.

#### Update UEFI via Windows Update

1. On your Surface Hub 2S, sign in as **Admin**.

    >[!Note]
    > You'll need to reset the device if you don't know your username or admin password. For more information, see [Reset and recovery for Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset).

1. Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and install all updates.

1. Restart the device.

1. Verify the UEFI version by using the Surface app. If the UEFI version isn't version *694.2938.768.0* or later, repeat these steps or use the following procedure to get the latest UEFI version.

#### Update the UEFI via bare metal recovery (BMR) image

1. Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**.

1. Enter your Hub serial number. It's on the back of the Hub next to the power connection.

1. Follow the directions to download the image onto a formatted USB drive by installing the Windows 10 Team 2020 Update.

1. The device enters the out-of-box experience (OOBE) setup after the update. You don't need to complete the setup. The UEFI version is already updated. Instead, power down the device by holding the power button until the screen turns off.

### Download Surface IT Toolkit and Surface Hub 2S drivers and firmware

On a separate PC, follow these steps:

1. Download the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703). The Surface IT Toolkit contains the [Surface UEFI Configurator](/surface/surface-it-toolkit-uefi-config) tool, formerly only available as a separate install.
2. Go to [Get started with Surface IT Toolkit](/surface/surface-it-toolkit#get-started-with-surface-it-toolkit) and follow the installation instructions.
2. Download the [Surface Hub 2S drivers and firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974): **SurfaceHub2S_Win10_19045_24.043.31687.0.MSI**. You'll use this file when you install the new operating system.

### Prepare the SEMM certificate

If this the first time using UEFI Configurator, you must prepare a certificate. This certificate ensures that after a device is enrolled in SEMM, UEFI settings can only be modified by using packages created with the approved certificate.

How you get a certificate might depend on the size or complexity of your organization:

- Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.

- Medium-sized businesses and others often choose to get certificates from partner providers. This option is recommended for organizations that don't have as much IT expertise or lack a dedicated IT security team.

- Alternatively, you can generate a self-signed certificate using a PowerShell script. For more information, see the [Surface Enterprise Management Mode certificate requirements](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). Or you can use PowerShell to create your own certificate. For more information, see the [Self-signed certificate](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) documentation.

The SEMM package that Surface UEFI Configurator creates must be secured with a certificate. The certificate verifies the signature of configuration files before UEFI settings can be applied. For more information, see the [SEMM](/surface/surface-enterprise-management-mode) documentation.

### Create a SEMM package

1. On a separate PC, open [Surface IT Toolkit](/surface/surface-it-toolkit), select **UEFI Configurator**, and then select **Configure devices**.

    :::image type="content" alt-text="Screenshot of Surface UEFI Configurator start screen." source="images/uefi-config-hub.png":::

2. On the Device Configuration and Certification page, configure the following items and then select **Next**.

- Under Choose Deployment Build, select **DFI**.
- Under Import Certificate Protection, select **Add**, browse for your certificate .pfx file and enter your password.
- Under Choose DFI Package Type, select **Configuration Package**.
- Under Select Device, choose **Surface Hub** and **Surface Hub 2S**

    :::image type="content" alt-text="Screenshot of Device Configuration and Certification." source="images/uefi-config-device.png":::

3. On the Device Configuration Settings page, go to **Advanced Settings**, select **UEFI Front Page**, and toggle **EnableOSMigration** to **On**.

:::image type="content" alt-text="Screenshot that shows how to enable the OS migration UEFI setting on Surface Hub 2S." source="images/enable-hub-os-migration.png":::

4. Insert a USB drive into your PC. Note that the USB drive will be formatted, and all files erased. Select **Create**.

    :::image type="content" alt-text="Screenshot that shows creation of SEMM packaage for Surface Hub 2S." source="images/create-hub-semm-package.png":::

5. When **Completed**, note the last two characters of the certificate thumbprint, and then select **Finish**. Your SEMM package *DfciUpdate.dfi* is ready.

    :::image type="content" alt-text="Screenshot that shows successful creation of SEMM package for Surface Hub 2S." source="images/finish-create-hub-semm-package.png":::

### Load a USB flash drive with a Windows 11 or Windows 10 image, SEMM package, and Surface Hub 2S drivers and firmware

You can install a Windows 10/11 Pro or Enterprise image (version *20H2* or later) by using one of the following options:

- Your current imaging solution.

- [Surface Deployment Accelerator](/surface/microsoft-surface-deployment-accelerator). Use this tool to create a bootable Windows 10/11 image. The image can include all current Windows 10/11 updates, Microsoft Office, other apps, and the required drivers and firmware.

- A USB flash drive that contains a Windows 10/11 Pro or Enterprise image. This option will not have Wi-Fi available until after the out-of-box experience (OOBE) setup. Once setup is complete, install the required [Surface Hub 2S drivers and firmware for Windows 10/11 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974) on the device.

The following steps show how to create a USB flash drive from installation media and then add the SEMM package file, drivers, and firmware for Windows 10/11 Pro and Enterprise OS to the Surface Hub 2S MSI file. If you use another deployment method, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section of this article.

> [!NOTE]
> After you finish the installation, you'll need a valid Windows 10/11 Pro or Windows 10/11 Enterprise license separate from your existing Windows 10 Team license.

1. To create a Windows 10/11 Pro installation, follow the instructions to download the media creation tool as appropriate:

    - [Windows 10 Pro](https://www.microsoft.com/software-download/windows10). 
    - [Windows 11 Pro](https://www.microsoft.com/software-download/windows11?msockid=2aa1d89a2f396aed21eeccdd2e146b0d)
    - For enterprise versions, go to the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home#/).

2. **Prepare the Installation Media:**
   - Insert a blank USB storage drive into your computer.

3. **Run the Media Creation Tool:**
   - Launch the tool and select **Create installation media**.
   - Follow the prompts to select your preferred language, edition, and architecture.
   - Choose USB flash drive as the media to use and follow the instructions to complete the creation process.

1. Copy the SEMM package file and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2S (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image. The BOOTME USB drive includes the following items:

   - Your Windows 10 bootable image.

   - The SEMM package file, copied to the root of the USB drive: *DfciUpdate.dfi*.

   - The drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2S (SurfaceHub2S_Win10_19045_24.043.31687.0.MSI). Copy this file to the root of the USB drive.

### Update UEFI on Surface Hub 2S to enable OS migration

1. Insert your BOOTME drive into the USB-A port on Surface Hub 2S.

1. To boot into UEFI:

   1. Turn off (shut down) your Surface Hub 2S.

   1. Press and hold **Volume +**, and then press and release the power button. Keep holding **Volume +** until the UEFI menu appears.

         ![Drawing shows the volume and power buttons.](images/shm-fig20.png)

1. When the device restarts, enter the UEFI password you created earlier, if applicable (recommended).

      ![System password screen.](images/shm-fig22.png)

1. From the UEFI menu, select **Management**. Then select  **Install from USB**.

      ![Screenshot shows where to select Management and then "Install from U S B".](images/shm-fig21.png)

1. Select **Restart now**, as the following image shows. The device will restart. It will display a white Microsoft logo in the middle of the window and then shut down.

      ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)

1. Press and release the power button. In the red dialog box, choose to activate Surface Enterprise Management Mode.

1. Enter your two-character certificate thumbprint and your UEFI settings password. Then select **OK**.

      ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)

   > [!NOTE]
   > After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied. You can no longer access Windows 10 Team. Instead, you must continue to the next step and install Windows 10/11 Pro or Windows 10/11 Enterprise.

   The device reboots. It displays the white logo in the middle of the screen and then shuts down again.

### Install Windows 10/11 Pro or Enterprise

1. If your bootable Windows 10/11 Pro or Enterprise drive isn't already in the Surface Hub 2S USB-A port, insert it now. Then press and release the power button.

   When the device starts, you'll see the white logo in the middle of the screen. Then, a spinning circle appears below the white logo.

1. If the Surface device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in). After you plug in the power cord again, the device should boot after a few seconds. Then, you'll see the white logo in the middle of the screen.

   If the device doesn't turn on, press and release the power button. Immediately after you see the logo in the middle of the screen, press and hold the Volume down button until you see the spinning circle below the white logo.

     ![Picture of the volume and power buttons.](images/shm-fig26.png)

1. When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10/11 Pro or Enterprise (version *20H2* or later).

### Install Surface Hub 2S drivers and firmware

To ensure that your Surface Hub 2S is up to date, install [drivers and firmware for Windows 10/11 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974). Then, reboot the device. Keep the Surface turned on for an hour, then reboot it again. You won't be prompted for the second reboot. This pause and extra reboot ensures that the firmware has been fully updated.

## Configure recommended settings

To configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10/11 Pro or Enterprise on Surface Hub 2S](surface-hub-2-post-install.md).

> [!NOTE]
> If you can't successfully migrate your device to Windows 10/11 Pro or Enterprise for Surface Hub 2S by following the steps outlined in this article, contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

### Manage SEMM enrollment

Enrolling a device into SEMM affects how you can manage it. For example, after you apply a SEMM package, all UEFI settings are unavailable (locked) in the device's UEFI menu. Default values for settings such as **IPv6 for PXE Boot** are also unavailable.

To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM. If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package. Use the UEFI Configurator tool and leave **EnableOSMigration** *off* (not *on* as in the original migration steps).

#### If you work with partners

If your company outsources the migration, you should have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you. Or, after you migrate the Hub, you can immediately unenroll it from SEMM. This step enables the local administration of UEFI to transfer the device to another party. But we strongly recommend using a UEFI password, which can be configured after migration. To learn more, see [Manage Surface UEFI settings](/surface/manage-surface-uefi-settings).

#### To roll back to Windows 10 Team

If you choose to restore your device to Windows 10 Team after the migration, we recommend that you first unenroll Hub from SEMM. To learn more, see [Unenroll Surface devices from SEMM](/surface/unenroll-surface-devices-from-semm).

>[!WARNING]
>To unenroll a device from SEMM and restore user control of Surface UEFI settings, you must have the SEMM certificate used to enroll the device in SEMM. If this certificate becomes lost or corrupted, it is not possible to unenroll from SEMM. Back up and protect your SEMM certificate accordingly.

To restore your device to Windows 10 Team, see [Reset and recovery for Surface Hub 2S](surface-hub-recover-reset.md). Before you roll back to Windows 10 Team, we recommend that you first unenroll the Surface Hub from SEMM. To learn more, see [Unenroll Surface devices from SEMM](/surface/unenroll-surface-devices-from-semm).

## Troubleshooting and common problems

| Issue                                                                                                                                                                                                                                                                                                            | Notes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Unable to migrate to Windows 10/11 Pro or Enterprise on Surface Hub V1.                                                                                                                                                                                                                             | By design, migration to Windows 10/11 Pro or Enterprise is not available on Surface Hub v1.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| UEFI menu does not appear when holding down the **Volume +** **power button**.                                                                                                                                                                                                                                    | - Ensure you hold down both buttons for approximately 10 seconds. After you see the Windows logo, release the **power button** while continuing to hold **Volume +**.<br>   - Try connecting the USB drive via **USB-C.**                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Surface Hub 2S does not automatically reboot after entering the two-character certificate thumbprint and your UEFI settings password.                                                                                                                                                                        | Press the Surface Hub 2S **Power button** to manually power the device back up.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| No audio from speakers following migration to Windows 10/11 Pro or Enterprise.                                                                                                                                                                                                                                    | To resolve, download and install the [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2S (MSI)](https://www.microsoft.com/download/details.aspx?id=101974).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| The volume rocker button is non-functional following migration to Windows 10/11 Pro or Enterprise.                                                                                                                                                                                                               | To resolve, download and install the [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2S (MSI)](https://www.microsoft.com/download/details.aspx?id=101974).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| How do I determine the serial number of Surface Hub 2S when running Windows 10/11 Pro or Enterprise?                                                                                                                                                                                                         | You can determine the serial number of your Surface Hub 2S running Windows 10/11 Pro or Enterprise just as in the Windows 10 Team OS:<br> <br>*You can find the serial number on the outside of the packaging, on the display by the power cord, or by using the [Surface app](/surface-hub/surface-hub-2-post-install#applications).* <br> <br>Alternatively, you can find the serial number via Command Prompt:<br><br>1. Type **CMD** in the search bar and press **Enter** to open a Command Prompt window.<br>2. Type the following command: <br>-  ```console wmic bios get serialnumber``` <br>3. The serial number will then be displayed within the Command Prompt window. |
| Unable to unenroll Surface Hub 2S from SEMM to roll back to Windows 10 Team.                                                                                                                                                                                                                             | If the SEMM certificate becomes lost or corrupt, SEMM cannot be removed or reset on Surface devices. With this in mind, please ensure you have the appropriate backups of the certificate and its password.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| In the Windows 10 Team OS, I used the [Surface App](https://apps.microsoft.com/store/detail/surface/9WZDNCRFJB8P) to view additional device and acc`essory information, troubleshoot, and access support. Since the migration to Windows 10/11 Pro or Enterprise, this app is no longer installed. | The Surface App is not installed on Windows 10/11 Pro or Enterprise by default, but you can install it manually by following the steps [here](/surface-hub/surface-hub-2-post-install#applications).                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Does migrating my Surface Hub 2S device to Windows 10/11 Pro or Enterprise impact the standard or extended warranty for the device?                                                                                                                                                                              | No, migrating to Windows 10/11 Pro or Enterprise does not change the warranty status of your Surface Hub 2S.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |

## Version history

The following table summarizes changes to this article.

| Version | Date               | Description                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.7  | September 19, 2023| Updated with info about the Surface IT Toolkit, which now includes the Surface UEFI Configurator tool. |
| v. 1.6  | January 16, 2023  | Added a new section for troubleshooting and common problems. |
| v. 1.5  | December 1, 2021  | Updated to show support for Windows 11. |
| v. 1.4  | December 14, 2020 | Provides [further info](#install-surface-hub-2s-drivers-and-firmware) about installing the MSI file for "Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2S," advising that a second reboot may be necessary depending on the state of your system.                                                          |
| v. 1.3  | December 3, 2020 | Updated with guidance about [managing SEMM enrollment.](#manage-semm-enrollment).                                                       |
| v. 1.2  | September 29, 2020 | Miscellaneous updates that address usability. feedback.                                                        |
| v. 1.1  | September 15, 2020 | Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS. |
| v. 1.0  | September 1, 2020  | New article.                                                                                           |
