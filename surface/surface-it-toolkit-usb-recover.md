---
title: Recovery Tool (IT Toolkit)
description: This article describes how to use the Recovery Tool to restore a Surface device to its factory state. 
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

# Recovery tool (IT Toolkit)

This article describes how to use the Recovery Tool to restore a Surface device to its factory state. 

1. Open [Surface IT Toolkit](surface-it-toolkit.md) and go to the **Recovery Tool** section  to begin the process of creating a USB key.

2. Select **Create** to download and create a USB key with the latest recovery image for a Surface device. Alternatively, if you have a previously downloaded recovery image, select **Manage Existing**.

    :::image type="content" source="images/it-toolkit-recover-start.png" alt-text="Screenshot of Recovery Tool page.":::

3. On the **Select Device** screen, choose the specific Surface device that you wish to recover. The toolkit displays a list of managed devices and a dropdown menu for all supported devices. Select Next.

    :::image type="content" source="images/it-toolkit-recovery-select.png" alt-text="Screenshot of Select Device page.":::

4. If creating a new recovery USB, select the base language and version of Windows for the recovery image. Options for Windows 10 and Windows 11, along with different feature updates like 21H2 and 22H2, are available. Select **Next**.

    :::image type="content" source="images/it-toolkit-recovery-create-new.png" alt-text="Screenshot of page to select language, operating system, and Windows version.":::

5. Choose a specific language pack from global regions, including Americas, Asia Pacific, China, Japan, Western Europe and Arabic, or Eastern Europe. Select Next.

    :::image type="content" source="images/it-toolkit-recover-lang.png" alt-text="Screenshot of Language Pack options.":::

6. Confirm your selections including the device model, Windows build, Office build (if applicable), and language pack. 
7. Under **USB Key Selection**, choose the USB to use for the recovery image. Make sure the USB drive you intend to use is correctly identified and ready to be formatted.
8. Select **Create** to start the process. A progress bar indicates that the recovery USB is ready to use.
9. Once the USB creation process reaches 100%, a confirmation message indicates that the recovery USB is ready to use.

Throughout the process, ensure you have a stable internet connection for the download and that no data you wish to keep is on the USB drive when formatted during the process.

## Restore Surface device

After the USB key is created, use it to restore the chosen Surface device back to its original state:

1. Shut down your Surface device.
2. Insert the bootable USB drive into the USB port on your Surface device.
3. Press and hold the **Volume-down** button on the device.
4. While holding the **Volume-down** button, press and release the **Power button**. The Microsoft or Surface logo appears on your screen.
5. Continue to hold the **Volume-down** button until you see spinning dots beneath the logo.
6. Follow the on-screen instructions to boot from your USB drive.

## Recover earlier Surface devices

1. If you don't see your Surface device listed in the Recovery tool, under **All Devices**, you can download a recovery image from Microsoft Support. 

    :::image type="content" source="images/it-toolkit-recovery-devices.png" alt-text="Screenshot that shows an example of available recovery images for Surface Laptop.":::

2. Go to [Surface Recovery Image Download](https://support.microsoft.com/surface-recovery-image) page, select your product, enter the serial number, and download the appropriate image. 

## Version history

- v1.143.141. Initial release.