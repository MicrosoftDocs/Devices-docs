---
title: Migrate to Windows 10/11 Pro or Enterprise on Surface Hub 2S
description: Guide on migrating Surface Hub 2S to Windows 10/11 Pro or Enterprise, including detailed steps and resources
ms.service: surface-hub
author: coveminer
ms.author: dpandre
manager: frankbu
ms.topic: how-to
ms.date: 09/19/2024
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
> The migration to Windows 10/11 on your Surface Hub 2S follows a detailed procedure outlined in this article. Please familiarize yourself with the [Solution components](#solution-components) and the [Migration & installation workflow](#migration--installation-workflow-summary) sections before proceeding.

> [!NOTE]
> Installing Windows 10/11 Pro or Enterprise on your Surface Hub 2S requires a new, separate license from the one originally provided with the device.

Begin the migration on a separate PC using the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703), which integrates various tools into a single, self-updating desktop application. Included is the Surface *UEFI Configurator*, which allows you to create a custom UEFI settings package for the Surface Hub 2S.

The *UEFI Configurator* serves as a gateway to the Surface Enterprise Management Mode (SEMM), facilitating centralized firmware settings management across Surface devices in an enterprise setting. For more details, visit [Get started with Surface Enterprise Management Mode](/surface/surface-enterprise-management-mode).

## Solution components

- Surface Hub 2S running Windows 10 Team.
- Separate PC running Windows 11 (or Windows 10).
- Surface IT Toolkit.
- Windows 10/11 Pro or Enterprise OS image, version 20H2 or later.
- Two USB drives, each with at least 16 GB of storage and formatted in FAT32. The first USB drive is used exclusively for the SEMM package and is automatically named *SEMM*; the second USB drive stores the Windows OS image along with the necessary drivers and firmware. In this documentation, the second USB drive is named *BOOTME*. 
- Windows Installer (MSI) file containing drivers and firmware for Windows 10/11 Pro and Enterprise on Surface Hub 2S.
- Internet connection.
- Imaging solution (optional).

## Migration & installation workflow summary

| Step | Action | Summary |
|------|--------|---------|
| 1    | [Verify the UEFI version on Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s) | Ensure that the UEFI version is *694.2938.768.0* or later. |
| 2    | [Download Surface IT Toolkit and Surface Hub 2S drivers & firmware](#download-surface-it-toolkit-and-surface-hub-2s-drivers--firmware) | On a separate PC, download and install the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703) and download [Drivers and Firmware for Windows 10/11 Pro and Enterprise OS on Surface Hub 2S and Surface Hub 3 MSI file](https://www.microsoft.com/download/details.aspx?id=101974). Save these packages for use in later steps. |
| 3    | [Prepare the SEMM certificate](#prepare-the-semm-certificate) | Acquire or prepare the certificate necessary for the *UEFI Configurator*. |
| 4    | [Create a SEMM package using your first USB drive](#create-a-semm-package-using-your-first-usb-drive) | This drive should contain only the SEMM package to ensure configuration integrity. |
| 5    | [Load your second USB drive with Windows 11 or Windows 10 image, the SEMM package, & drivers & firmware](#load-your-second-usb-drive-with-a-windows-11-or-windows-10-image-semm-package-and-surface-hub-2s-drivers-and-firmware) | Prepare the second USB drive, named *BOOTME*, with a Windows 11 (or Windows 10) image. After creating the Windows image, add the downloaded drivers and firmware (from Step 2) to this drive. |
| 6    | [Update the UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) | Use the *BOOTME* drive to boot the Surface Hub 2S into the UEFI menu and install the SEMM package. |
| 7    | [Install Windows 10/11 Pro or Enterprise](#install-windows-1011-pro-or-enterprise) | Install Windows 10/11 Pro or Enterprise version *20H2* or later using the *BOOTME* drive. |
| 8    | [Install drivers and firmware for Windows 10/11 Pro and Enterprise](#install-surface-hub-2s-drivers--firmware) | Install the latest drivers and firmware updates using the [Drivers and Firmware for Windows 10/11 Pro and Enterprise OS on Surface Hub 2S MSI file](https://www.microsoft.com/download/details.aspx?id=101974). |
| 9    | [Configure Surface Hub 2S as a personal productivity device](#configure-recommended-settings) | Optimize Surface Hub 2S with recommended settings and applications for personal productivity use. |

### Verify the UEFI version on Surface Hub 2S

Before migrating from Windows 10 Team to Windows 10/11 Desktop on your Surface Hub 2S, confirm that the UEFI version is *694.2938.768.0* or later.

**To verify the UEFI version:**

1. From the Welcome screen on the Surface Hub 2S, select **Start**, navigate to **All Apps** > **Surface**, and open the Surface app.
2. Select **Your Surface** to view details about the device, including the current UEFI version.

   - If the UEFI version is *694.2938.768.0* or later, proceed to create the SEMM package for OS migration.
   - If the version is older, update the UEFI using one of the following methods.

#### Update UEFI via Windows Update

1. Sign in as **Admin** on the Surface Hub 2S.
2. Navigate to **All apps** > **Settings** > **Update and Security** > **Windows Update** and install all available updates.
3. Restart the device and recheck the UEFI version using the Surface app.
4. If the UEFI version still doesn't meet the requirements, consider updating via bare metal recovery.

#### Update the UEFI via bare metal recovery (BMR) image

1. Visit the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage), select **Surface Hub 2S**, and enter your device’s serial number.
2. Follow the instructions to download and apply the BMR image using a formatted USB drive.
3. After the update, the device will enter the out-of-box experience (OOBE). Power down the device immediately as the UEFI version will have been updated.

### Download Surface IT Toolkit and Surface Hub 2S Drivers & Firmware

On a separate PC, perform the following tasks:

1. Download the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703), which includes the Surface [*UEFI Configurator*](/surface/surface-it-toolkit-uefi-config).
2. Follow the installation instructions in [Get started with Surface IT Toolkit](/surface/surface-it-toolkit#get-started-with-surface-it-toolkit).
3. Download the [Surface Hub 2S drivers & firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974), **SurfaceHub2S_Win10_19045_24.043.31687.0.MSI**, to use during the new OS installation.

### Prepare the SEMM certificate

Before using the *UEFI Configurator* for the first time, you need to prepare a certificate to secure the SEMM package:

- **Large enterprises**: Generate certificates using your organization's security infrastructure.
- **Medium-sized businesses**: Consider obtaining certificates from trusted partner providers, especially if you lack dedicated IT security resources.
- **Self-signed certificates**: For smaller setups, you can generate a self-signed certificate using PowerShell. For details, see the [Self-signed certificate guide](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) and [Surface Enterprise Management Mode certificate requirements](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).

> [!WARNING]
> To unenroll a device from SEMM and restore user control of Surface UEFI settings, you must have the SEMM certificate used to enroll the device in SEMM. If this certificate becomes lost or corrupted, it is not possible to unenroll from SEMM. Back up and protect your SEMM certificate accordingly.

### Create a SEMM package using your first USB drive

To create a SEMM package for Surface Hub 2S, follow these steps using the Surface IT Toolkit on a separate PC:

1. Open the [Surface IT Toolkit](/surface/surface-it-toolkit), select **UEFI Configurator**, and then choose **Configure devices**.

    :::image type="content" alt-text="Screenshot of *UEFI Configurator* start screen." source="images/uefi-config-hub.png":::

2. On the Device Configuration and Certification page, configure the items as follows, then select **Next**:
   - **Choose Deployment Build**: Select **DFI**.
   - **Import Certificate Protection**: Select **Add**, browse to select your certificate (.pfx file), and enter the associated password.
   - **Choose DFI Package Type**: Select **Configuration Package**.
   - **Select Device**: Choose **Surface Hub** and **Surface Hub 2S**.

    :::image type="content" alt-text="Screenshot of Device Configuration and Certification." source="images/uefi-config-device.png":::

3. Navigate to the Device Configuration Settings page:
   - Go to **Advanced Settings**, select **UEFI Front Page**, and toggle **EnableOSMigration** to **On**.

    :::image type="content" alt-text="Screenshot that shows how to enable the OS migration UEFI setting on Surface Hub 2S." source="images/enable-hub-os-migration.png":::

4. Insert your first USB drive into your PC. This drive will be formatted, and all files on it will be erased. Select **Create** to build the SEMM package.

    :::image type="content" alt-text="Screenshot that shows creation of SEMM package for Surface Hub 2S." source="images/create-hub-semm-package.png":::

5. Upon completion, note the last two characters of the certificate thumbprint displayed, then select **Finish**. Your SEMM package, named *DfciUpdate.dfi*, is now ready for use.

    :::image type="content" alt-text="Screenshot that shows successful creation of SEMM package for Surface Hub 2S." source="images/finish-create-hub-semm-package.png":::

### Load your second USB drive with a Windows 11 or Windows 10 image, SEMM package, and Surface Hub 2S drivers and firmware

To install a Windows 10/11 Pro or Enterprise image (version *20H2* or later), use one of the following options. This document includes steps for use of a USB drive.

- **Existing imaging solutions**: Use your organization's current imaging solution.
- **Surface Deployment Accelerator**: Utilize this tool to create a comprehensive bootable image that includes the latest updates for Windows 10/11, Microsoft Office, other applications, and necessary drivers and firmware. Learn more and download from the [Surface Deployment Accelerator page](/surface/microsoft-surface-deployment-accelerator).
- **USB drive**: Manually create a bootable USB drive with a Windows 10/11 Pro or Enterprise image. Note, Wi-Fi connectivity will be unavailable until post-OOBE setup. After setup, download and install the [Surface Hub 2S drivers and firmware for Windows 10/11 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974).

#### Prepare your USB drive

1. **Download the Media Creation Tool**:
   - For Windows 10 Pro, visit [Microsoft's Windows 10 download page](https://www.microsoft.com/software-download/windows10).
   - For Windows 11 Pro, visit [Microsoft's Windows 11 download page](https://www.microsoft.com/software-download/windows11).
   - For enterprise versions, access the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home#/).

2. **Prepare the installation media**:
   - Insert your second USB drive into your computer. Name the drive *BOOTME*.  

3. **Run the Media creation tool**:
   - Open the tool and choose **Create installation media**.
   - Follow the on-screen prompts to select your language, edition, and system architecture.
   - Choose the USB drive as the destination and follow the steps to create the installation media.

4. **Transfer files to USB *BOOTME* drive**:
   - Copy the SEMM package file (*DfciUpdate.dfi*) from your first USB drive (named *SEMM*) to the root of the *BOOTME* USB drive.
   - Add the drivers and firmware MSI file (SurfaceHub2S_Win10_19045_24.043.31687.0.MSI) to the root of the *BOOTME* USB drive.

> [!NOTE]
> Ensure you have a valid Windows 10/11 Pro or Enterprise license distinct from any pre-existing Windows 10 Team licenses.

### Update UEFI on Surface Hub 2S to enable OS migration

To update the UEFI for OS migration on your Surface Hub 2S, follow these steps:

1. **Prepare the device**:
   - Insert the BOOTME USB drive into the USB-A port on the Surface Hub 2S.

2. **Boot into UEFI**:
   - Turn off the Surface Hub 2S.
   - Press and hold the **Volume +** button, then press and release the power button. Continue holding **Volume +** until the UEFI menu appears on the screen.

3. **Access UEFI settings**:
   - When prompted, enter the UEFI password you set earlier, if you have one (this is recommended for security).

      ![System password screen.](images/shm-fig22.png)

4. **Install from USB**:
   - In the UEFI menu, navigate to **Management** and select **Install from USB** to initiate the update process from your USB drive.

      ![Screenshot shows where to select Management and then "Install from U S B".](images/shm-fig21.png)

5. **Restart the device**:
   - Select **Restart now** from the menu. The device displays a white Microsoft logo and then shuts down to complete the installation.

      ![Screenshot shows a message prompting you to restart.](images/shm-fig25.png)

6. **Activate SEMM**:
   - Turn on the Surface Hub 2S again. A red dialog box appears prompting you to activate the Surface Enterprise Management Mode (SEMM).
   - Enter the last two characters of your certificate thumbprint and your UEFI settings password, then select **OK** to proceed.

      ![Screenshot shows the confirm-activation dialog box where you enter your two-character certificate thumbprint and your UEFI settings password.](images/shm-fig23.png)

   > [!NOTE]
   > Activating SEMM with the **EnableOSMigration** setting will render Windows 10 Team inaccessible. You should now proceed to install Windows 10/11 Pro or Enterprise.

7. **Final reboot**:
   - The device reboots automatically, displaying the white logo again before shutting down, indicating that the UEFI update and SEMM activation are complete.

### Install Windows 10/11 Pro or Enterprise

1. **Prepare for installation**:
   - If not already done, insert the bootable Windows 10/11 Pro or Enterprise USB *BOOTME* drive into the USB-A port of the Surface Hub 2S and press the power button to turn on the device.
   - You should see a white logo followed by a spinning circle indicating the boot process.

2. **Troubleshooting boot issues**:
   - If the device doesn't boot from the USB drive, power it off, reconnect the power cord, and turn it on again.
   - If it still doesn’t boot from USB, after seeing the logo, press and hold the Volume down button until the spinning circle appears.

3. **Complete Windows setup**:
   - Follow the on-screen instructions during the out-of-box experience (OOBE) to install Windows 10/11 Pro or Enterprise (version *20H2* or later).

### Install Surface Hub 2S drivers & firmware

- After installing Windows, ensure the device is up-to-date by installing the [drivers & firmware for Windows 10/11 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974).
- Reboot the device, keep it on for an hour, then reboot again without prompt. This ensures the firmware is fully updated.

### Configure recommended settings

- To optimize the Surface Hub 2S as a personal productivity device, refer to [Configure Windows 10/11 Pro or Enterprise on Surface Hub 2S](surface-hub-2-post-install.md).

### Manage SEMM enrollment

#### General guidance

- Enrolling in SEMM locks all UEFI settings. To modify UEFI settings post-migration, either apply another SEMM package using the original certificate, or unenroll from SEMM.

#### Partner involvement

- If outsourcing migration, ensure the transfer of the SEMM certificate, SEMM package, and UEFI password for management continuity.
- To enable local UEFI administration after migration, consider unenrolling the device from SEMM immediately.

#### Rolling back to Windows 10 Team

- If you choose to restore your device to Windows 10 Team, see [Reset and recovery for Surface Hub 2S](surface-hub-recover-reset.md).
- Before you roll back to Windows 10 Team, we recommend that you first unenroll the Surface Hub from SEMM. To learn more, see [Unenroll Surface devices from SEMM](/surface/unenroll-surface-devices-from-semm).

> [!WARNING]
> Unenrolling from SEMM requires the original SEMM certificate. Loss or corruption of this certificate makes unenrollment impossible. Always back up and protect your SEMM certificate.

## Troubleshooting and common problems

Here are solutions to some common issues you might encounter during or after migrating your Surface Hub to Windows 10/11 Pro or Enterprise.

| Issue | Solution |
|-------|----------|
| **Unable to migrate to Windows 10/11 Pro or Enterprise on Surface Hub V1** | Migration to Windows 10/11 Pro or Enterprise isn't supported on Surface Hub V1 by design. |
| **UEFI menu does not appear when holding down the Volume + and power button** | - Hold both buttons for approximately 10 seconds; release the power button after seeing the Windows logo while continuing to hold Volume +.<br> - Try using the USB-C port for the USB drive. |
| **Surface Hub 2S does not reboot automatically after entering the certificate thumbprint and UEFI password** | Manually power the device by pressing the Power button. |
| **No audio or non-functional volume rocker button post-migration** | Download and install the [Drivers and Firmware for Windows 10/11 Pro and Enterprise on Surface Hub 2S (MSI)](https://www.microsoft.com/download/details.aspx?id=101974) to resolve these issues. |
| **Finding the serial number on Surface Hub 2S running Windows 10/11 Pro or Enterprise** | The serial number can be found in the same locations as on Windows 10 Team OS: on the packaging, by the power cord display, or via the [Surface app](/surface-hub/surface-hub-2-post-install#applications). Alternatively, retrieve it via Command Prompt:<br>1. Open Command Prompt, type `wmic bios get serialnumber`, and press Enter.<br>2. The serial number is displayed. |
| **Unable to unenroll from SEMM to roll back to Windows 10 Team** | Ensure you back up the SEMM certificate and its password, as SEMM can't be reset without these if they become lost or corrupt. |
| **Surface App missing post-migration** | The Surface App isn't preinstalled on Windows 10/11 Pro or Enterprise. Install it manually using the instructions [here](/surface-hub/surface-hub-2-post-install#applications). |
| **Impact of migration on warranty** | Migrating your Surface Hub 2S to Windows 10/11 Pro or Enterprise doesn't affect its standard or extended warranty. |

## Version history

The following table summarizes changes to this article.

| Version | Date               | Description                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.7  | September 19, 2023| Updated with info about the Surface IT Toolkit, which now includes the *UEFI Configurator* tool. |
| v. 1.6  | January 16, 2023  | Added a new section for troubleshooting and common problems. |
| v. 1.5  | December 1, 2021  | Updated to show support for Windows 11. |
| v. 1.4  | December 14, 2020 | Provides [further info](#install-surface-hub-2s-drivers--firmware) about installing the MSI file for "Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2S," advising that a second reboot may be necessary depending on the state of your system.                                                          |
| v. 1.3  | December 3, 2020 | Updated with guidance about [managing SEMM enrollment.](#manage-semm-enrollment).                                                       |
| v. 1.2  | September 29, 2020 | Miscellaneous updates that address usability. feedback.                                                        |
| v. 1.1  | September 15, 2020 | Placed a note in the introduction that clarifies licensing requirements for installing a new OS. |
| v. 1.0  | September 1, 2020  | New article.                                                                                           |
