---
title: Reset and recovery for Surface Hub (v1)
description: Shows how to reset and recover the original Surface Hub v1.
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: 
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: troubleshooting
ms.date: 01/23/2023
ms.localizationpriority: medium
appliesto:
- Surface Hub
---

# Reset and recovery for Surface Hub (v1)

You can reset Surface Hub to restore the operating system to the last cumulative Windows update. The following information is removed:

- All local user files and configuration data. 
- The device account.
- Account data for local administrators.
- Domain-join or Microsoft Entra join data.
- Mobile Device Management (MDM) enrollment data.
- Configuration data that was set by using MDM or the Settings app.

> [!TIP]
> If the reset option cannot be used, the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) can reimage the Surface Hub SSD directly.

## Reset a Surface Hub

You may have to reset Surface Hub for the following scenarios:

- You're repurposing the device for a new meeting space and want to reconfigure it.
- You want to change how you locally manage the device.

During the reset process, if you see a blank screen for long periods, wait and don't take any action.

> [!WARNING]
> The device reset process may take up to six hours. Do not turn off or unplug the Surface Hub until the process has finished. If you interrupt the process, the device becomes inoperable and requires warranty service to become functional again.

1. On your Surface Hub, open **Settings**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot that shows Settings app for Surface Hub.](images/sh-settings.png)

2. Select **Update & Security**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot that shows Update & Security group in Settings app for Surface Hub.](images/sh-settings-update-security.png)

3. Select **Recovery**, and then, under **Reset device**, select **Get started**.

   > [!IMPORTANT]
   > Ensure that your BitLocker key is available as you will be prompted for it later. To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md). When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key. Skipping that prompt will cause reset to fail.

   > [!div class="mx-imgBorder"]
   > ![Screenshot that shows the Reset device option in Settings app for Surface Hub.](images/sh-settings-reset-device.png)

   After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again. If the reset process encounters a problem, it rolls the Surface Hub back to the previously existing operating system image and then displays the Welcome screen.

## Recover a locked Surface Hub

If the Surface Hub becomes unusable and you can't reset it from the Settings app, you can still reset it if you have the BitLocker recovery key.

1. Locate the power switch on the bottom of Surface Hub. The power switch is next to the power cord connection. For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).

2. While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.

3. Use the power switch to turn the Surface Hub back on. The device starts and displays the Surface Hub Logo screen. When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.  

4. Repeat step 3 twice, or until Surface Hub displays the "Preparing Automatic Repair" message. After it displays this message, Surface Hub shows the Windows RE screen.

5. Select **Reset** > **Local reinstall** > **Fully clean the drive.**

   ![Screenshot that shows the process to recover and fully clean drive.](images/recover-fully-clean-drive.png)

8. You'll be asked **Are you ready to reset this device?**. Select **Reset**.

   ![Screenshot that shows the process to recover and confirm reset.](images/recover-confirm-reset.png)

## Contact Support

If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).

## Related articles

- [Surface Hub Recovery Tool](surface-hub-recovery-tool.md)
- [Manage Microsoft Surface Hub](manage-surface-hub.md)
