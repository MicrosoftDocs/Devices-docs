---
title: "Migrate to Windows 10 Pro or Enterprise on Surface Hub 2"
description: "This article describes the process of migrating from Windows 10 Team on Surface Hub 2 to Windows 10 Pro or Windows 10 Enterprise."
keywords: Surface Hub Desktop, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2020
ms.localizationpriority: Medium
---
# Migrate to Windows 10 Pro or Enterprise on Surface Hub 2

## Introduction

Surface Hub 2S comes pre-installed with Windows 10 Team, a customized edition of Windows 10 designed to facilitate easy collaboration in meeting room environments. Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC. 

> [!IMPORTANT]
>Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described on this page. Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before proceeding.


> [!NOTE]
> When you install Windows 10 Pro or Enterprise, you will need a new licence separate from your existing Windows 10 Team license. 


You start the migration from Windows 10 Team using a separate PC and downloadable tool -- **Surface UEFI Configurator** --  to create a package containing a new UEFI setting that you apply to Surface Hub 2S.  Surface UEFI Configurator functions as an interface into Surface Enterprise Management Mode (SEMM), designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment. To learn more about SEMM, see <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank">Microsoft Surface Enterprise Management Mode documentation</a>.

## Solution Components

- Surface Hub 2S device running Windows 10 Team operating system.
- Separate device running Windows 10.
- Surface UEFI Configurator tool to create the SEMM package.
- Windows 10 Pro or Enterprise OS image, version 1903 or greater.
- Two USB drives with 16GB of storage, FAT32 format.
- Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2, Windows Installer .MSI file.
- Internet connection.
- Imaging solution (optional).

 
## Migration and installation workflow summary

| Step  | Action                                                                                                 | Summary                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [Verify UEFI version on Surface Hub 2S meets minimum requirements](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | Ensure the UEFI version is **694.2938.768.0** or later.                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | Select the Download button on the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page, select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC. Download [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) and save it for use in Step 5. |
| 3 | [Prepare SEMM certificate](#prepare-semm-certificate)                                                                          | Prepare required certificate for running Surface UEFI Configurator or use your current certificate.                                                                                                                                                                                                                                                                                                      |
| 4 | [Create SEMM package](#create-semm-package)                                                                               | Launch Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the required configuration files to apply on Surface Hub 2S. Copy these SEMM package  files to a folder on your PC.                                                                                                                                                                                          |
| 5 | [Prepare USB flash drive containing Windows 10 image, SEMM package, and Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | Create a single USB drive (named **BOOTME** in this example) containing a Windows 10 image. Add your Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (Step 2) and SEMM package files (Step 4) to the **BOOTME** drive.                                                                                                                                                                                                  |
| 6 | [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | Use the **BOOTME** drive to boot Surface Hub 2S to the UEFI menu and install SEMM package.|
| 7 | [Install Windows 10 Pro or Enterprise version 1903 or later](#install-windows-10-pro-or-enterprise)                                        | Use the **BOOTME** drive to Install **Windows 10 Pro or Enterprise** version 1903 or later.                                                                                                                                                                                                                                                                                 |
| 8 | [Install Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](#install-surface-hub-2-drivers-and-firmware)                                        | To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974).                                                                                                                                                                                                                                                                                  |
| 9 | [Fully configure Surface Hub 2S as a personal productivity device](#next-steps)                                        |  Enable recommended settings and applications to optimize use of Surface Hub 2S as a personal productivity device.                                                                                                                                                                                                                                                                    |

### Verify UEFI version on Surface Hub 2S meets minimum requirements

The minimum UEFI version required prior to migrating the Surface Hub from Windows 10 Team to Windows 10 Desktop is **694.2938.768.0**.
 
**To verify the current UEFI version on your system:**

1. On Surface Hub 2S home screen, select **Start** and open the **SurfaceApp** (**All Apps** > **Surface**).

2. Select **Your Surface** to display information about the Surface Hub, including the current UEFI version on the device. If the UEFI version is **694.2938.768.0** or later as shown below, the UEFI is eligible for you to create the SEMM package to enable OS migration.

	![Open Surface App & select Your Surface](images/shm-fig1.png)
 
3. If the UEFI version is earlier than version **694.2938.768.0**, you will need to obtain a current version using Windows Update.

**To update UEFI from Windows Update:**

1. On your Surface Hub 2S, sign in as an **Admin**, go to **All apps** > **Settings** > **Update and Security** > **Windows Update** and install all updates, then restart the device. Verify the UEFI version using the Surface App. **Note:** If you do not know your username or admin password, you will need to reset the device. To learn more, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).

2. Repeat these steps until the UEFI version is **694.2938.768.0** or later.

3. If you still do not see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations. You may need to reset your device (**Settings** > **Update & security** > **Reset device**).

### Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware

On a separate PC:

- Select the Download button on the [Surface Tools for IT page](https://www.microsoft.com/download/details.aspx?id=46703), select and download the Surface UEFI Configurator .MSI file and install it on a separate PC. The Surface UEFI Configurator tool cannot be run on a Surface Hub 2S while Windows 10 Team edition is installed.

- Download [Surface Hub 2 Drivers and Firmware Windows Installer .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) to be applied when installing the new operating system.

### Prepare SEMM certificate

If this is your first time using Surface UEFI Configurator, you’ll need to prepare a certificate. This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify UEFI settings. How you acquire a certificate may vary depending on the size or complexity of your organization:

- Large enterprise organizations typically maintain their own certificate infrastructure to generate certificates per standard security practices.

- Medium-sized businesses and others may choose to obtain a certificate from third party providers. This is the recommended option for organizations without sufficient IT expertise or a dedicated IT security team.

- Alternatively, you can generate a self-signed certificate with a PowerShell script per the following documentation: [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements). Or use PowerShell to create your own certificate per the following documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).

The SEMM package created by using the Surface UEFI Configurator tool must be secured with a certificate to verify the signature of configuration files before UEFI settings can be applied. To learn more, see [Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.
 
 
### Create SEMM package

1. Install the **Surface UEFI Configurator** tool, as downloaded earlier, to a separate PC. 

2. Open **Surface UEFI Configurator** and select **Start**.

   ![Open Surface UEFI Configurator](images/shm-fig2.png)
   
3. Select **Surface Devices** and then select **Next**.

   ![Select Surface devices](images/shm-fig3.png)
  
4. Select **Configuration Package**.

   ![Select Configuration package](images/shm-fig4.png)
  
5. Select **Certificate Protection**.

   ![Select certificate protection](images/shm-fig5.png)

6. You will be prompted to add your certificate .pfx file.

   ![You will be prompted to add your certificate](images/shm-fig6.png)
   
7. Enter your **Certificate password** and select **OK**.

   ![Enter your certificate password and select OK](images/shm-fig7.png)

8. Select **Password Protection** to add a password to Surface UEFI. This password will be required whenever you boot to UEFI. It is **strongly recommended** to set a UEFI password you will use on Surface Hub 2S.

   ![Click Password Protection](images/shm-fig8.png)
   
9. Set a **UEFI password** and select **OK**.

   > [!IMPORTANT]
   > Save the password in a secure location accessible to IT admins in your organization responsible for managing Surface Hubs. If the password is lost, there is no recovery process. 

   ![Enter your UEFI password](images/shm-fig9.png)

10. Select **Surface Hub 2S** and then select **Next**.

    ![Select Surface Hub 2S](images/shm-fig10.png)
   
11. Select **Next**.

    ![Select Next](images/shm-fig10a.png)

12. To allow installation of Windows 10 Pro or Enterprise, select **EnableOsMigration.**

    ![Select Enable OS Migration](images/shm-fig11.png)
    
13. Set **EnableOSMigration** to **On** and select **Next**.

    ![Set Enable OS Migration to On](images/shm-fig12.png)

> [!NOTE]
> After you apply a SEMM package, all UEFI settings will display as grayed out (locked) in the UEFI menu on the device. This includes default values for other settings such as IPv6 for PXE Boot. To modify UEFI settings after completing the migration, you will need to apply another SEMM package or unenroll the device from SEMM. If you apply another SEMM package to modify the UEFI settings, you must use the original Certificate when building the new SEMM package using the UEFI Configurator tool and leave the "EnableOSMigration" OFF (and not "on" as shown in the original migration steps).

#### Save SEMM package to USB drive

1. Connect a USB Drive to your PC. Choose **Hub 2S** and then select **Next**.

   ![Select USB](images/shm-fig13.png)

> [!WARNING]
> All existing data on the USB drive is erased when building the SEMM package. Before building the SEMM package, remove any files from the USB drive that you wish to save.
   
2. Select **Build**.

   ![Select Build](images/shm-fig14.png)

3. Capture a screenshot of this page and then select **End**. Your SEMM package is now ready and contains the SEMM package **DfciUpdate.dfi** and a text file with the SEMM thumbprint (the last two characters of the certificate’s thumbprint).

   ![Select End](images/shm-fig15.png)
   
4. Save the certificate thumbprint’s last 2 characters, which is required to activate SEMM when you apply the package on Surface Hub 2S.

### Prepare USB flash drive containing Windows 10 image, SEMM package, and Surface Hub 2 Drivers and Firmware

You can install a Windows 10 Pro or Enterprise image (version 1903 or later) using one of the following options:

- Your current imaging solution.

- [Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) lets you create a bootable Windows 10 image which can include all current Windows 10 updates, Office, other apps of your choice, as well as the required drivers and firmware. 

- USB flash drive with Windows 10 Pro or Enterprise image, followed by installing  [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
This procedure describes creating a USB flash drive from installation media and then adding the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 .MSI file. If you’re using other deployment methods, proceed to the section [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration).

> [!NOTE]
> Once installed, you will need a valid license for Windows 10 Pro or Windows 10 Enterprise that is separate from your existing Windows 10 Team license.

1. To create a Windows 10 Pro installation, follow the instructions on the [Download Windows 10](https://www.microsoft.com/software-download/windows10) page for using the **Media Creation** tool. To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).

2. Insert a new **USB storage** drive. Launch the **Media Creation** tool, select **Create installation media** and then select **Next**.

   ![Create Installation media](images/shm-fig16.png)
   
3. Select language, Windows 10, and 64-bit (x64) and then select **Next**.

   ![Select Language, Windows 10, and 64-bit & select Next](images/shm-fig17.png)
   
4. Select **USB flash drive** and select **Next**.

   ![Select USB flash drive and select Next](images/shm-fig18.png)
   
5. When the download completes, select **Finish**.

   ![Select Finish](images/shm-fig19.png)
   
6. Copy the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (.MSI file) to the ROOT of the USB flash drive (**BOOTME**) containing your Windows 10 image. BOOTME USB drive contains:

    - Your Windows 10 bootable image.
    
    - SEMM package files (copied to the root of the USB drive)
    
      - DfciUpdate.dfi.
      - Text file with the SEMM thumbprint. (In this example: SurfaceUEFI_2020Aug25_1058.txt.) The auto-generated date timestamp corresponds to the date that you created the file using Surface UEFI Configurator.

   - Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi), also copied to the root of the USB drive.

### Update UEFI on Surface Hub 2S to enable OS migration

1. Insert your **BOOTME** drive into the USB-A port on Surface Hub 2S. (See the previous section for the list of required files.)

2. To boot into UEFI:

   1. Power off (shutdown) your Surface Hub 2S.
   1. Press and hold **Volume +** and then press and release the **Power** button.
   1. Keep holding **Volume +** until the UEFI menu appears.
   
      ![Keep holdling Volume + until the UEFI menu appears](images/shm-fig20.png)
      
3. When the device restarts, enter the UEFI password you created earlier, if applicable (strongly recommended).

   ![When the device restarts, enter your UEFI paassword](images/shm-fig22.png)
   
4. In the UEFI menu, select **Management** > **Install from USB**.

   ![Select Management & Install from USB](images/shm-fig21.png)
   
5. Select **Restart now**, as shown below. The device will reboot and display the white 4-square logo in the middle of screen and then shut down.

   ![Select Restart Now](images/shm-fig25.png)
   
6. Press and release the power button, a red screen will display prompting you to activate Surface Enterprise Management Mode. 

7. Enter your two-character **certificate thumbprint**, your **UEFI settings password** and then select **OK**.

   ![Enter your 2 character certificate thumbprint](images/shm-fig23.png)
 
   > [!NOTE]
   > Once you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied. You will no longer be able to access Windows 10 Team and must proceed to the next step and install Windows 10 Pro or Windows 10 Enterprise. 

8. The device will reboot, display the white 4-square logo in the middle of the screen, and then it will shut down again.

### Install Windows 10 Pro or Enterprise

1. If your bootable Windows 10 Pro or Enterprise drive is not already in the Surface Hub 2 USB-A port, insert it now and then press and release the power button.

2. The device will start, you will see the white 4-square in the middle of the screen, and then you will see a spinning circle below the white four-square logo.

3. If the device does not automatically boot to the USB drive, power off the device (unplug the power cord and plug it back in). After plugging the power cord back in, the device should boot after a few seconds to the white 4-square logo in the middle of screen, or you can press and release the power button to turn the device back on. Immediately after you see the 4-square logo in the middle of the screen, press and hold the volume down button until you see the spinning circle below the white four-square logo.
 
   ![Boot to Windows 10 from USB](images/shm-fig26.png)
   
4. When the out-of-box experience (OOBE) setup launches, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).

### Install Surface Hub 2 drivers and firmware

 - To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).
 
### Next steps

To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).

> [!NOTE]
>If following the steps outlined in this document is unsuccessful in migrating your device to Windows 10 Pro or Enterprise for Surface Hub 2, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).

### Rolling back to Windows 10 Team

If you would Like to restore your device to Windows 10 Team, refer to [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).

## Version history

| Version | Date               | Description                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| v. 1.2  | September 29, 2020 | Miscellaneous updates per usability feedback.                                                        |
| v. 1.1  | September 15, 2020 | Placed additional note in the Introduction clarifying licensing requirements for installing a new OS. |
| v. 1.0  | September 1, 2020  | New article.                                                                                           |
