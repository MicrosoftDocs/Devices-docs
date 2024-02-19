---
title: Microsoft Surface Data Eraser (Surface)
description: The Microsoft Surface Data Eraser tool allows you to securely wipe data from your Surface devices.
ms.assetid: 8DD3F9FE-5458-4467-BE26-E9200341CF10
ms.reviewer: chauncel
manager: frankbu
ms.localizationpriority: medium
ms.service: surface
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 09/21/2023
appliesto:
- Windows 10
- Windows 11
---

# Microsoft Surface Data Eraser

Find out how the Microsoft Surface Data Eraser tool can help you securely wipe data from your Surface devices.

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) is a tool that boots from a USB stick and allows you to perform a secure wipe of all data from a compatible Surface device. A Microsoft Surface Data Eraser USB stick requires only the ability to boot from USB. To learn more about the data wiping capabilities and practices Microsoft uses during the service process for Surface, see [Protecting your data if you send your Surface in for service](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy).

>[!IMPORTANT]
>Microsoft Surface Data Eraser uses the NVM Express (NVMe) format command to erase data as authorized in [NIST Special Publication 800-88 Revision 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf).

Compatible Surface devices include:

- Surface Laptop Studio (all generations)
- Surface Book (all generations)
- Surface Go (all generations)
- Surface Pro X (all generations)
- Surface Laptop (all generations)
- Surface Laptop Go (all generations)
- Surface Laptop SE
- Surface Studio (all generations)
- Surface Pro 2 and later
- Surface 3
- Windows 10 Pro and Enterprise on Surface Hub 2S

Some scenarios where Microsoft Surface Data Eraser can be helpful include:

- Prepare a Surface device to be sent for repair.
- Decommission a Surface device from corporate or organizational use.
- Repurpose a Surface device for a new user.
- Reimage devices containing sensitive data.

## How to create a Microsoft Surface Data Eraser USB stick

After the creation tool is installed, follow these steps to create a Microsoft Surface Data Eraser USB stick. Before you begin these steps, ensure that you have a USB 3.0 stick that is 4 GB or larger connected to the computer.

1. Run the DataEraserSetup.msi installation file that you downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703).

2. Select **Build** to begin the Microsoft Surface Data Eraser USB creation process, as shown in Figure 1.

   :::image type="content" source="images/microsoft-surface-data-eraser/fig1-build.png" alt-text="Figure 1. Begin the Microsoft Surface Data Eraser tool":::<br>
  *Figure 1. Begin the Microsoft Surface Data Eraser tool*

3. Select **Continue** to acknowledge that you have a USB drive of at least 4 GB connected, as shown in Figure 2.

   :::image type="content" source="images/microsoft-surface-data-eraser/fig2-continue.png" alt-text="Figure 2. Confirm USB drive of at least 4 GB is connected":::<br>
   *Figure 2. Confirm USB drive of at least 4 GB is connected*

4. Choose **x64 (for 2021+ devices only)** for 2021 or newer devices, choose **x64** for 2020 and older devices or **ARM64** for Surface Pro X from the **Architecture Selection** page, as shown Figure-3. Select **Continue**.

   :::image type="content" source="images/microsoft-surface-data-eraser/fig3-select.png" alt-text="Figure 3. Select device architecture":::

5. Select the USB drive of your choice from the **USB Thumb Drive Selection** page as shown in Figure 4, and then select **Start** to begin the USB creation process.

   :::image type="content" source="images/microsoft-surface-data-eraser/fig4-start.png" alt-text="Figure 4. USB thumb drive selection>":::<br>
   *Figure 4. USB thumb drive selection*

   >[!TIP]
   >If the Start button is disabled, check that your removable drive has a total capacity of at least 4 GB.

6. After the creation process is finished, all binaries are copied to the USB drive. Select **Success**.

7. When the **Congratulations** screen is displayed, you can eject and remove the thumb drive. This thumb drive is now ready to be inserted into a Surface device, booted from, and wipe any data on the device. Select **Complete** to finish the USB creation process, as shown in Figure 5.

   :::image type="content" source="images/microsoft-surface-data-eraser/fig5-complete.png" alt-text="Complete the Microsoft Surface Data Eraser tool":::<br>
   *Figure 5. Complete the Microsoft Surface Data Eraser USB creation process*

8. Select **X** to close Microsoft Surface Data Eraser.

## How to use a Microsoft Surface Data Eraser USB stick

After you create a Microsoft Surface Data Eraser USB stick, you can boot a supported Surface device from the USB stick by following this procedure:

>[!NOTE]
>Surface Data Eraser on Surface Studio and Surface Studio 2 can take up to 6 minutes to boot into WinPE before disk erasure can occur.

1. Insert the bootable Microsoft Surface Data Eraser USB stick into the supported Surface device.

2. Boot your Surface device from the Microsoft Surface Data Eraser USB stick. To boot your device from the USB stick, follow these steps:

   a. Turn off your Surface device.
   b. Press and hold the **Volume Down** button.
   c. Press and release the **Power** button.
   d. Release the **Volume Down** button.

   >[!TIP]
   >If your device does not boot to USB using these steps, you may need to turn on the **Enable Alternate Boot Sequence** option in Surface UEFI. You can read more about Surface UEFI boot configuration in [Manage Surface UEFI Settings](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).

3. When the Surface device boots, a **SoftwareLicenseTerms** text file is displayed, as shown in Figure 5.

   ![Booting the Microsoft Surface Data Eraser USB stick.](images/data-eraser-3.png)

   *Figure 5. Booting the Microsoft Surface Data Eraser USB stick*

4. Read the software license terms, and then close the Notepad file.

5. Accept or decline the software license terms by typing **Accept** or **Decline**. You must accept the license terms to continue.

6. The Microsoft Surface Data Eraser script detects the storage devices that are present in your Surface device and displays the details of the native storage device. To continue, press **Y** (this action runs Microsoft Surface Data Eraser and removes all data from the storage device) or press **N** (this action shuts down the device without removing data).

   >[!CAUTION]
   >The Microsoft Surface Data Eraser tool deletes all data, including Windows operating system files required to boot the device, in a secure and unrecoverable way. To boot a Surface device that has been wiped with Microsoft Surface Data Eraser, you first need to reinstall the Windows operating system. To remove data from a Surface device without removing the Windows operating system, you can use the **Reset your PC** function. However, this does not prevent your data from being recovered with forensic or data recovery capabilities. See [Recovery options in Windows 10](https://support.microsoft.com/help/12415/windows-10-recovery-options) for more information.

   ![Partition to be erased is displayed.](images/sda-fig5-erase.png)
  
   *Figure 6. Partition to be erased is displayed in Microsoft Surface Data Eraser*

7. If you pressed **Y** in step 6, due to the destructive nature of the data erasure process, another dialog box is displayed to confirm your choice.

8. Select **Yes** to continue erasing data on the Surface device.

   >[!TIP]
   >When you run Surface Data Eraser on the Surface Data Eraser USB drive, a log file is generated in the **SurfaceDataEraserLogs** folder.

## Changes and updates

Microsoft Surface Data Eraser is periodically updated by Microsoft. For information about the changes provided in each new version, see the following notes:

### 3.54.139.0

*Release Date: October 4, 2023*

This version of Surface Data Eraser includes:

- Support for Surface Laptop Studio 2, Surface Laptop Go 3, and Surface Go 4.

### 3.48.139.0

*Release Date: November 21, 2022*

This version of Surface Data Eraser includes bug fixes.

### 3.46.139.0.

*Release Date: October 28, 2022*

This version of Surface Data Eraser includes:

- Support for Surface Pro 9, Surface Laptop 5, and Surface Studio 2+.

### 3.45.139.0

*Release Date: June 7, 2022*

This version of Surface Data Eraser includes:

- Support for Surface Laptop Go 2.

### 3.42.139.0

*Release Date: October 5, 2021*

This version of Surface Data Eraser includes:

- Separate option for 2021 and support for newer devices including Surface Laptop Studio, Surface Pro 8, and Surface Go 3.

### 3.39.139.0

*Release Date: April 13, 2021*

This version of Surface Data Eraser includes:

- Support for Surface Laptop 4

### 2.34.139.0

*Release Date: January 15, 2021*

This version of Surface Data Eraser:

- Includes bug fixes

### 3.33.139

*Release Date: September 9, 2020*

This version of Surface Data Eraser includes bug fixes and adds support for:

- Architecture redesign to reduce the need to update with new product releases
- Notification available for new tool updates
- Customer content additions
- Windows 10 Pro and Enterprise on Surface Hub 2S

### 3.30.139

*Release Date: May 11, 2020*

This version of Surface Data Eraser adds support for:

- Surface Book 3
- Surface Go 2
- New SSD in Surface Go

### 3.28.137

*Release Date: November 11, 2019*

This version of Surface Data Eraser:

- Includes bug fixes

### Version 3.21.137

*Release Date: October 21, 2019*

This version of Surface Data Eraser is compiled for x86 and adds support for the following devices:

- Surface Pro 7, Surface Pro X, and Surface Laptop 3

### Version 3.2.78.0

*Release Date: December 4, 2018*

This version of Surface Data Eraser includes bug fixes

### Version 3.2.75.0

*Release Date: November 12, 2018*

This version of Surface Data Eraser:

- Adds support to Surface Studio 2
- Fixes issues with SD card

### Version 3.2.69.0

*Release Date: October 12, 2018*

This version of Surface Data Eraser adds support for the following devices:

- Surface Pro 6
- Surface Laptop 2

### Version 3.2.68.0

This version of Microsoft Surface Data Eraser adds support for Surface Go.

### Version 3.2.58.0

This version of Microsoft Surface Data Eraser adds support for the following:

- Extra storage devices (drives) for Surface Pro and Surface Laptop devices

### Version 3.2.46.0

This version of Microsoft Surface Data Eraser adds support for Surface Pro with LTE Advanced

### Version 3.2.45.0

This version of Microsoft Surface Data Eraser adds support for the following devices:

- Surface Book 2
- Surface Pro 1 TB

   >[!NOTE]
   >Surface Data Eraser v3.2.45.0 and above can be used to restore Surface Pro or Surface Laptop devices with the 1TB storage option in the scenario that the device shows two separate 512GB volumes or encounters errors when attempting to deploy or install Windows 10. See [Surface Pro Model 1796 and Surface Laptop 1TB display two drives](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives) for more information.

### Version 3.2.36.0

This version of Microsoft Surface Data Eraser adds support for the following devices:

- Surface Pro
- Surface Laptop

>[!NOTE]
>The Microsoft Surface Data Eraser USB drive creation tool is unable to run on Windows 10 S. To wipe a Surface Laptop running Windows 10 S, you must first create the Microsoft Surface Data Eraser USB drive on another computer with Windows 10/11 Pro or Windows 10/11 Enterprise.
