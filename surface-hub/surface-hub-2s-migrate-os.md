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

Surface Hub 2S is primarily designed to enhance collaboration in meeting-room settings. However, it can also be configured to run Windows 10/11 Pro or Enterprise, transforming it into a versatile PC. For guidance on migrating Surface Hub 3, refer to [Migrate to Windows 11 Pro or Enterprise on Surface Hub 3](surface-hub-3-migrate-os.md).

> [!IMPORTANT]
> The migration to Windows 10/11 on your Surface Hub 2S follows a detailed procedure outlined in this article. Please familiarize yourself with the [Solution components](#solution-components) and the [Migration and installation workflow](#migration-and-installation-workflow-summary) sections before proceeding.

> [!NOTE]
> Installing Windows 10/11 Pro or Enterprise on your Surface Hub 2S requires a new, separate license from the one originally provided with the device.

Begin the migration on a separate PC using the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703), which integrates various tools into a single, self-updating desktop application. Among these tools is the *Surface UEFI Configurator*, which allows you to create a custom UEFI settings package for the Surface Hub 2S.

The Surface UEFI Configurator serves as a gateway to the Surface Enterprise Management Mode (SEMM), facilitating centralized firmware settings management across Surface devices in an enterprise setting. For more details, visit [Get started with Surface Enterprise Management Mode](/surface/surface-enterprise-management-mode).

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

| Step | Action | Summary |
|------|--------|---------|
| 1    | [Verify the UEFI version on Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s) | Ensure that the UEFI version is *694.2938.768.0* or later. |
| 2    | [Install Surface IT Toolkit and Surface Hub 2S drivers and firmware](#download-surface-it-toolkit-and-surface-hub-2s-drivers-and-firmware) | On a separate PC, download and install the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703) and [Drivers and Firmware for Windows 10/11 Pro and Enterprise OS on Surface Hub 2S and Surface Hub 3 MSI file](https://www.microsoft.com/download/details.aspx?id=101974). Save these packages for use in later steps. |
| 3    | [Prepare the SEMM certificate](#prepare-the-semm-certificate) | Acquire or prepare the certificate necessary for the UEFI Configurator. |
| 4    | [Create a SEMM package](#create-a-semm-package) | Use the Surface IT Toolkit and the Surface UEFI Configurator to create a SEMM package on a USB drive. This package will contain the configuration file needed for the Surface Hub 2S. |
| 5    | [Load a USB flash drive with Windows 11 or Windows 10 image, the SEMM package, and drivers and firmware](#load-a-usb-flash-drive-with-a-windows-11-or-windows-10-image-semm-package-and-surface-hub-2s-drivers-and-firmware) | Prepare a USB drive, named *BOOTME*, with a Windows 10 or Windows 11 image. Add the downloaded drivers and firmware (from Step 2) and the SEMM package (from Step 4) to this drive. |
| 6    | [Update the UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) | Use the *BOOTME* drive to boot the Surface Hub 2S into the UEFI menu and install the SEMM package. |
| 7    | [Install Windows 10/11 Pro or Enterprise](#install-windows-1011-pro-or-enterprise) | Install Windows 10/11 Pro or Enterprise version *20H2* or later using the *BOOTME* drive. |
| 8    | [Install drivers and firmware for Windows 10/11 Pro and Enterprise](#install-surface-hub-2s-drivers-and-firmware) | Install the latest drivers and firmware updates using the [Drivers and Firmware for Windows 10/11 Pro and Enterprise OS on Surface Hub 2S MSI file](https://www.microsoft.com/download/details.aspx?id=101974). |
| 9    | [Configure Surface Hub 2S as a personal productivity device](#configure-recommended-settings) | Optimize Surface Hub 2S with recommended settings and applications for personal productivity use. |


### Verify the UEFI version on Surface Hub 2S

Before migrating from Windows 10 Team to Windows 10/11 Desktop on your Surface Hub 2S, confirm that the UEFI version is *694.2938.768.0* or later.

**To verify the UEFI version:**

1. From the Welcome screen on the Surface Hub 2S, select **Start**, navigate to **All Apps** > **Surface**, and open the Surface app.
2. Select **Your Surface** to view details about the device, including the current UEFI version.

   - If the UEFI version is *694.2938.768.0* or later, proceed to create the SEMM package for OS migration.
   - If the version is older, update the UEFI using one of the methods below.

#### Update UEFI via Windows Update

1. Sign in as **Admin** on the Surface Hub 2S.
2. Navigate to **All apps** > **Settings** > **Update and Security** > **Windows Update** and install all available updates.
3. Restart the device and recheck the UEFI version using the Surface app.
4. If the UEFI version still does not meet the requirements, consider updating via bare metal recovery.

#### Update the UEFI via Bare Metal Recovery (BMR) Image

1. Visit the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage), select **Surface Hub 2S**, and enter your device’s serial number.
2. Follow the instructions to download and apply the BMR image using a formatted USB drive.
3. After the update, the device will enter the out-of-box experience (OOBE). Power down the device immediately as the UEFI version will have been updated.

### Download Surface IT Toolkit and Surface Hub 2S Drivers and Firmware

On a separate PC, perform the following:

1. Download the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703), which includes the [Surface UEFI Configurator](/surface/surface-it-toolkit-uefi-config).
2. Follow the installation instructions in [Get started with Surface IT Toolkit](/surface/surface-it-toolkit#get-started-with-surface-it-toolkit).
3. Download the [Surface Hub 2S drivers and firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974), **SurfaceHub2S_Win10_19045_24.043.31687.0.MSI**, to use during the new OS installation.

### Prepare the SEMM Certificate

Before using the UEFI Configurator for the first time, prepare a certificate to secure the SEMM package:

- **Large enterprises** should generate certificates using their established security infrastructure.
- **Medium-sized businesses** may opt for certificates from trusted partner providers, especially if they lack dedicated IT security resources.
- **Self-signed certificates** can be created using PowerShell for smaller setups. For details, refer to [Self-signed certificate guide](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) and [Surface Enterprise Management Mode certificate requirements](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).

>[!WARNING]
>To unenroll a device from SEMM and restore user control of Surface UEFI settings, you must have the SEMM certificate used to enroll the device in SEMM. If this certificate becomes lost or corrupted, it is not possible to unenroll from SEMM. Back up and protect your SEMM certificate accordingly.

### Create a SEMM package

To create a SEMM package for Surface Hub 2S, follow these steps using the Surface IT Toolkit on a separate PC:

1. Open the [Surface IT Toolkit](/surface/surface-it-toolkit), select **UEFI Configurator**, and then choose **Configure devices**.

    :::image type="content" alt-text="Screenshot of Surface UEFI Configurator start screen." source="images/uefi-config-hub.png":::

2. On the Device Configuration and Certification page, configure the items as follows, then click **Next**:
   - **Choose Deployment Build**: Select **DFI**.
   - **Import Certificate Protection**: Click **Add**, browse to select your certificate (.pfx file), and enter the associated password.
   - **Choose DFI Package Type**: Select **Configuration Package**.
   - **Select Device**: Choose **Surface Hub** and **Surface Hub 2S**.

    :::image type="content" alt-text="Screenshot of Device Configuration and Certification." source="images/uefi-config-device.png":::

3. Navigate to the Device Configuration Settings page:
   - Go to **Advanced Settings**, select **UEFI Front Page**, and toggle **EnableOSMigration** to **On**.

:::image type="content" alt-text="Screenshot that shows how to enable the OS migration UEFI setting on Surface Hub 2S." source="images/enable-hub-os-migration.png":::

4. Insert a USB drive into your PC. This drive will be formatted, and all files on it will be erased. Click **Create** to build the SEMM package.

    :::image type="content" alt-text="Screenshot that shows creation of SEMM packaage for Surface Hub 2S." source="images/create-hub-semm-package.png":::

5. Upon completion, note the last two characters of the certificate thumbprint displayed, then select **Finish**. Your SEMM package, named *DfciUpdate.dfi*, is now ready for use.

    :::image type="content" alt-text="Screenshot that shows successful creation of SEMM package for Surface Hub 2S." source="images/finish-create-hub-semm-package.png":::

### Load a USB flash drive with a Windows 11 or Windows 10 image, SEMM package, and Surface Hub 2S drivers and firmware

To install a Windows 10/11 Pro or Enterprise image (version *20H2* or later), consider one of these options:

- **Existing Imaging Solutions**: Use your organization's current imaging solution.
- **Surface Deployment Accelerator**: Utilize this tool to create a comprehensive bootable image that includes the latest updates for Windows 10/11, Microsoft Office, additional applications, and necessary drivers and firmware. Learn more and download from the [Surface Deployment Accelerator page](/surface/microsoft-surface-deployment-accelerator).
- **USB Flash Drive**: Manually create a bootable USB drive with a Windows 10/11 Pro or Enterprise image. Note, Wi-Fi connectivity will be unavailable until post-OOBE setup. After setup, download and install the [Surface Hub 2S drivers and firmware for Windows 10/11 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974).


#### Prepare your USB drive

1. **Download the Media Creation Tool**:
   - For Windows 10 Pro, visit [Microsoft's Windows 10 download page](https://www.microsoft.com/software-download/windows10).
   - For Windows 11 Pro, visit [Microsoft's Windows 11 download page](https://www.microsoft.com/software-download/windows11).
   - For enterprise versions, access the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home#/).

2. **Prepare the Installation Media**:
   - Insert a blank USB storage drive into your computer.

3. **Run the Media Creation Tool**:
   - Open the tool and choose **Create installation media**.
   - Follow the on-screen prompts to select your language, edition, and system architecture.
   - Choose the USB flash drive as the destination and follow the steps to create the installation media.

4. **Transfer Files to USB Drive**:
   - Copy the SEMM package file (*DfciUpdate.dfi*) to the root of the USB drive.
   - Add the drivers and firmware MSI file (SurfaceHub2S_Win10_19045_24.043.31687.0.MSI) to the root of the drive.

> [!NOTE]
> Ensure you have a valid Windows 10/11 Pro or Enterprise license distinct from any pre-existing Windows 10 Team licenses.

### Update UEFI on Surface Hub 2S to enable OS migration

To update the UEFI for OS migration on your Surface Hub 2S, follow these steps:

1. **Prepare the device**:
   - Insert the BOOTME USB drive into the USB-A port on the Surface Hub 2S.

2. **Boot into UEFI**:
   - Turn off the Surface Hub 2S.
   - Press and hold the **Volume +** button, then press and release the power button. Continue holding **Volume +** until the UEFI menu appears on the screen.

         ![Screenshot that shows the volume and power buttons.](images/shm-fig20.png)
3. **Access UEFI settings**:
   - When prompted, enter the UEFI password you set earlier, if you have one (this is recommended for security).

      ![System password screen.](images/shm-fig22.png)

4. **Install from USB**:
   - In the UEFI menu, navigate to **Management** and select **Install from USB** to initiate the update process from your USB drive.

      ![Screenshot shows where to select Management and then "Install from U S B".](images/shm-fig21.png)

5. **Restart the device**:
   - Select **Restart now** from the menu. The device will display a white Microsoft logo and then shut down to complete the installation.

      ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)

6. **Activate SEMM**:
   - Turn on the Surface Hub 2S again. A red dialog box will appear prompting you to activate the Surface Enterprise Management Mode (SEMM).
   - Enter the last two characters of your certificate thumbprint and your UEFI settings password, then select **OK** to proceed.

      ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)

   > [!NOTE]
   > Activating SEMM with the **EnableOSMigration** setting will render Windows 10 Team inaccessible. You should now proceed to install Windows 10/11 Pro or Enterprise.

7. **Final Reboot**:
   - The device will reboot automatically, displaying the white logo again before shutting down, indicating that the UEFI update and SEMM activation are complete.

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
