---
title: Reset and recovery for Surface Hub
description: Describes the reset and recovery processes for the Surface Hub, and provides instructions.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: 
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 03/10/2021
ms.localizationpriority: medium
---

# Reset and recovery for Surface Hub

This article describes how to reset a Microsoft Surface Hub.  

[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information. The information that is removed includes the following:

- The device account
- Account information for the device's local administrators
- Domain-join or Azure AD-join information
- Mobile Device Management (MDM) enrollment information
- Configuration information that was set by using MDM or the Settings app

You can specify whether the recovery process preserves other information that is stored on the Surface Hub. If the reset option cannot be used, the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) is available to reimage the Surface Hub SSD directly.

## Reset a Surface Hub

You may have to reset your Surface Hub for reasons such as the following:

- You are repurposing the device for a new meeting space and want to reconfigure it.
- You want to change how you locally manage the device.

During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.

> [!WARNING]
> The device reset process may take up to six hours. Do not turn off or unplug the Surface Hub until the process has finished. If you interrupt the process, the device becomes inoperable. The device requires warranty service in order to become functional again.

1. On your Surface Hub, open **Settings**.

   > [!div class="mx-imgBorder"]
   > ![Image that shows Settings app for Surface Hub.](images/sh-settings.png)

2. Select **Update & Security**.

   > [!div class="mx-imgBorder"]
   > ![Image that shows Update & Security group in Settings app for Surface Hub.](images/sh-settings-update-security.png)

3. Select **Recovery**, and then, under **Reset device**, select **Get started**.

   > [!IMPORTANT]
   > Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later. To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md). When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key. Skipping that prompt will cause reset to fail.
   
   > [!div class="mx-imgBorder"]
   > ![Image that shows the Reset device option in Settings app for Surface Hub.](images/sh-settings-reset-device.png)

   After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again. If the reset process encounters a problem, it rolls the Surface Hub back to the previously existing operating system image and then displays the Welcome screen.

## Recover a locked Surface Hub

If for some reason the Surface Hub becomes unusable and you are unable to initiate a reset from the Settings app, you can still reset the Surface Hub if you have the BitLocker recovery key.

1. Locate the power switch on the bottom of Surface Hub. The power switch is next to the power cord connection. For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).

2. While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.

3. Use the power switch to turn the Surface Hub back on. The device starts and displays the Surface Hub Logo screen. When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.  

4. Repeat step 3 two times, or until the Surface Hub displays the "Preparing Automatic Repair" message. After it displays this message, the Surface Hub displays the Windows RE screen.
 
5. Select **Reset**.

6. Select **Local reinstall.**

7. Select **Fully clean the drive.**
 
   ![recover and fully clean drive.](images/recover-fully-clean-drive.png)

8. You will be asked **Are you ready to reset this device?**. Select **Reset**. 
   
   ![recover and confirm reset.](images/recover-confirm-reset.png)


## Contact Support

If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).


## Related topics

[Manage Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub administrator's guide](surface-hub-administrators-guide.md)
