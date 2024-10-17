---
title: "Reset & recovery for Surface Hub 2S & Surface Hub 3"
description: "Learn how to recover and reset Surface Hub 2S or Surface Hub 3."
ms.service: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: troubleshooting
ms.date: 01/24/2024
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S
- Surface Hub 3
---

# Reset & recovery for Surface Hub 2S & Surface Hub 3

If you encounter problems, you can recover Surface Hub 2S or Surface Hub 3 [via a USB drive](#recovery-from-a-usb-drive). Or you can [reset Surface Hub 2S](#reset-surface-hub-2s) directly via Windows settings.

## Recovery from a USB drive

With a USB drive, you can reinstall the device to factory settings--even if you have lost the BitLocker key or no longer have admin credentials to the Settings app.

1. From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s).

2. Ensure you download the appropriate image for your Surface Hub:

   >[!IMPORTANT]
   > For **Surface Hub 2S devices**: Use the **Windows 10 Team 2022 Update** recovery image.<br>
   > For **Surface Hub 3 devices and [Hub 2S devices already migrated to Teams Rooms](surface-hub-2s-migrate-to-mtr-w.md)**: Use the **Windows 11 IoT Enterprise with the Microsoft Teams Rooms on Windows experience** recovery image.  

3. In the search box on the taskbar, enter **recovery drive**, and select **Create a recovery drive** or **Recovery Drive** from the results. You may need to enter an admin password or confirm your choice.

4. In the **User Account Control** box, select **Yes**.

5. Clear the **Back up system files to the recovery drive** check box and then select **Next**.

6. Select your USB drive, then select **Next > Create**.  Some utilities need to be copied to the recovery drive, so this might take a few minutes.

   >[!TIP]
   > Use a USB 3.0 drive with 16 GB or 32 GB of storage, formatted as FAT32.

7. When the recovery drive is ready, select **Finish**.

8. Double-click the recovery image .zip file that you previously downloaded to open it.

9. Select all the files from the recovery image folder, copy them to the root of your USB drive, and then select **Choose to replace the files in the destination**.

10. Once the files have finished copying, select the **Safely Remove Hardware and Eject Media** icon on the taskbar and remove your USB drive.

11. Connect the USB drive to any USB-C or USB-A port on the Surface Hub. Turn off the Hub and then boot from the USB drive.

### Boot Surface Hub from USB drive

>[!TIP]
>If the device was unplugged or experienced an abrupt power outage or pulled power cord, wait at least 15 seconds before attempting to boot from USB.

1. While pressing the **Volume down** button, press the **Power** button.

2. Keep pressing both buttons until you see the Windows logo.

3. Release the **Power** button but continue to hold the **Volume down** button until the Install UI begins.

   ![Screenshot of Volume down and power buttons.](images/sh2-keypad.png)

4. On the language selection screen, select the display language for your Surface Hub.

5. Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**. If you're prompted for a BitLocker key, select **Skip this drive**. Surface Hub reboots several times and can take an hour or more to complete the recovery process.

6. When the first-time setup screen appears, remove the USB drive and complete first-time setup. 

## Reset Surface Hub 2S

For Surface Hub 2S only, you can recover the device via the Settings app. Sign in to your Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.

   > [!IMPORTANT]
   > Ensure you have your BitLocker key available before resetting the device, as you will be prompted for it later. See [Save your BitLocker key](save-bitlocker-key-surface-hub.md) to learn more.

1. To reset Surface Hub 2S, select **Get Started**.

2. When the **Ready to reset this device** window appears, select **Reset**.
  
   > [!TIP]
   > When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key. Skipping the prompt will cause the reset to fail. Once you enter the BitLocker key, the Hub reinstalls the operating system from the recovery partition. This may take up to one hour to complete.
  
3. To reconfigure the device, run the first-time Setup program.

4. If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record and re-enroll the new device. For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](/mem/intune/remote-actions/devices-wipe).

   ![Screenshot of Reset and recovery for Surface Hub.](images/sh2-reset.png)

## Troubleshooting and common problems

| Issue                                                                                                                                             | Notes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Unable to download recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) | Try downloading it on another network; ideally, a standalone device, not joined to a domain, with open access to the internet (no proxies).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| You're prompted for a recovery key                                                                                                               | Select the option to **Skip this drive.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| BMR fails at 99% or X%                                                                                                                            | Check the following potential issues:<br> - **Connections.** Ensure your USB drive is directly connected to the USB port in the [compute cartridge](/surface-hub/surface-hub-2s-pack-components#how-to-replace-and-pack-your-surface-hub-2s-compute-cartridge), located on the rear of Surface Hub 2S. Remove any in-between cables that may be in use.<br>- **Storage space.** Ensure your USB drive has enough space for the image (the BMR image might occupy more space on the drive than the available size).<br>- **Damaged recovery image.** Try recreating the image using the above steps to ensure it wasn't damaged during installation.<br>- **Possible hardware failure.** If available, try installing your USB drive on another Surface Hub and see if you can successfully boot to the drive. If so, this might indicate a hardware failure, which will require opening a support case.                             |
| **Preparing automatic repair** not showing                                                                                                        | - Check that you followed these steps, exactly as shown in the previous section, [Boot Surface Hub from USB drive](#boot-surface-hub-from-usb-drive), and repeated here:<br><br> 1. While pressing the Volume down button, press the Power button.<br>2. Keep pressing both buttons until you see the Windows logo.<br>3. Release the Power button but continue to hold the Volume down<br>button until the Install UI begins.<br><br>    - **Test on another Surface Hub.** If available, try installing your USB drive on another Surface Hub and see if you can successfully boot to the drive. If so, this might indicate a hardware failure, which will require opening a support case.                                                                                                                                                                                                                                                                                                                          |
| USB isn't recognized                                                                                                                             | - **Check image**. Ensure the image is created correctly. All recovery image files must be extracted from the original ZIP file and saved to the root of your USB drive [the root is the top level of your USB drive].<br>- **Check USB format.** Confirm you're using a supported USB drive. It must be a USB 3.0 drive with 16 GB or 32 GB of storage, formatted as FAT32. You can check if a laptop recognizes the USB and if the BMR image is present.<br>- If the USB drive is formatted correctly but still not working, try using a different USB brand.<br>- Use a USB-C flash drive instead and start the process from the beginning.<br>- Double-check that you completed the following step, as shown earlier from [Recovery from a USB drive](#recovery-from-a-usb-drive), and repeated here:<br><br>Connect the USB drive to any USB-C or USB-A port on the Surface Hub 2S or Surface Hub 3. Turn off the Hub and then boot from the USB drive.<br><br>Try connecting to another USB-C or USB-A port on Surface Hub 2S or Surface Hub 3. |

## Contact Support

If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).
