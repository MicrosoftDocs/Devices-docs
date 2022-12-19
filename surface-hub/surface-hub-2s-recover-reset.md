---
title: "Reset and recovery for Surface Hub 2S"
description: "Learn how to recover and reset Surface Hub 2S."
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
manager: frankbu
ms.topic: how-to
ms.date: 11/09/2022
ms.localizationpriority: Medium
---

# Reset and recovery for Surface Hub 2S

If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore using a USB drive.

To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.

## Reset the device

   > [!IMPORTANT]
   > Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later. To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).

1. To reset the device, select **Get Started**.

2. When the **Ready to reset this device** window appears, select **Reset**.
  
   > [!TIP]
   > When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key. Skipping that prompt will cause the reset to fail. Once you enter the BitLocker key, the Hub reinstalls the operating system from the recovery partition. This may take up to one hour to complete.
  
3. To reconfigure the device, run the first-time Setup program.

4. If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device. For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](/intune/devices-wipe).

   > [!div class="mx-imgBorder"]
   > ![*Reset and recovery for Surface Hub 2S*.](images/sh2-reset.png)
   <br/>*Figure 1. Reset and recovery for Surface Hub 2S*

## Recover Surface Hub 2S by using a USB recovery drive

New in Surface Hub 2S, you can now reinstall the device by using a recovery image.

### Recovery from a USB drive

Using Surface Hub 2S, you can reinstall the device using a recovery image. By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key or if you no longer have admin credentials to the Settings app.

>[!TIP]
>Use a USB 3.0 drive with 16 GB or 32 GB of storage, formatted as FAT32.

1. From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.

2. In the search box on the taskbar, enter **recovery drive**, and select **Create a recovery drive** or **Recovery Drive** from the results. You may need to enter an admin password or confirm your choice.

3. In the **User Account Control** box, select **Yes**.

4. Make sure to clear the **Back up system files to the recovery drive** check box and then select **Next**.

5. Select your USB drive, and then select **Next > Create**.  Some utilities need to be copied to the recovery drive, so this might take a few minutes.

6. When the recovery drive is ready, select **Finish**.

7. Double-click the recovery image .zip file that you previously downloaded to open it.

8. Select all the files from the recovery image folder, copy them to the root of your USB drive, and then select **Choose to replace the files in the destination**.

9. Once the files have finished copying, select the **Safely Remove Hardware and Eject Media** icon on the taskbar and remove your USB drive.

10. Connect the USB drive to any USB-C or USB-A port on the Surface Hub 2S. Turn off the Hub and then boot from the USB drive.

#### Boot Surface Hub from USB drive

>[!NOTE]
>If the device was unplugged or experienced an abrupt power outage or pulled power cord, wait at least 15 seconds before attempting to boot from USB.

1. While pressing the Volume down button, press the Power button.

2. Keep pressing both buttons until you see the Windows logo.

3. Release the Power button but continue to hold the Volume down button until the Install UI begins.

   ![*Use Volume down and power buttons to initiate recovery*.](images/sh2-keypad.png)
   <br>*Figure 2. Volume and Power buttons*

4. On the language selection screen, select the display language for your Surface Hub 2S.

5. Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**. If you're prompted for a BitLocker key, select **Skip this drive**. Surface Hub 2S reboots several times and can take an hour or more to complete the recovery process.

6. When the first-time setup screen appears, remove the USB drive.

## Troubleshooting and common problems

| Issue                                                                                                                                             | Notes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Unable to download recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) | Try downloading it on another network; ideally, a standalone device, not joined to a domain, with open access to the internet (no proxies).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| You're prompted for a recovery key                                                                                                               | Select the option to **Skip this drive.**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| BMR fails at 99% or X%                                                                                                                            | Check the following potential issues:<br> - **Connections.** Ensure your USB drive is directly connected to the USB port in the [compute cartridge](/surface-hub/surface-hub-2s-pack-components#how-to-replace-and-pack-your-surface-hub-2s-compute-cartridge), located on the rear of Surface Hub 2S. Remove any in-between cables that may be in use.<br>- **Storage space.** Ensure your USB drive has enough space for the image (the BMR image might occupy more space on the drive than the actual available size).<br>- **Damaged recovery image.** Try recreating the image using the precise steps listed above to ensure it wasn't damaged during installation.<br>- **Possible hardware failure.** If available, try installing your USB drive on another Surface Hub and see if you can successfully boot to the drive. If so, this might indicate a hardware failure, which will require opening a support case.                             |
| **Preparing automatic repair** not showing                                                                                                        | - Check that you followed these steps, exactly as shown in the previous section, [Boot Surface Hub from USB drive](#boot-surface-hub-from-usb-drive), and repeated here:<br><br> 1. While pressing the Volume down button, press the Power button.<br>2. Keep pressing both buttons until you see the Windows logo.<br>3. Release the Power button but continue to hold the Volume down<br>button until the Install UI begins.<br><br>    - **Test on another Surface Hub.** If available, try installing your USB drive on another Surface Hub and see if you can successfully boot to the drive. If so, this might indicate a hardware failure, which will require opening a support case.                                                                                                                                                                                                                                                                                                                          |
| USB isn't recognized                                                                                                                             | - **Check image**. Ensure the image is created correctly. All recovery image files must be extracted from the original .ZIP file and be saved to the root of your USB drive [the root is the top level of your USB drive].<br>- **Check USB format.** Confirm you’re using a supported USB drive. It must be a USB 3.0 drive with 16 GB or 32 GB of storage, formatted as FAT32. You can check if a laptop recognizes the USB and that the BMR image is present.<br>- If the USB drive is formatted correctly but still not working, try using a different USB brand.<br>- Use a USB-C flash drive instead and start the process from the beginning.<br>- Double-check you completed the following step, as shown earlier in **Step 10** from [Recovery from a USB drive](#recovery-from-a-usb-drive), and repeated here:<br><br>Connect the USB drive to any USB-C or USB-A port on the Surface Hub 2S. Turn off the Hub and then boot from the USB drive.<br><br>Try connecting to another USB-C or USB-A port on Surface Hub 2S. |

## Contact Support

If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).
