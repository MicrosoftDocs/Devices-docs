---
title: SSD removal in compatible Surface devices
description: This article, intended for qualified IT technicians, describes the recommended best practices for the removal and replacement of SSDs in Surface Laptop 4, Surface Laptop 3, Surface Pro 7+, Surface Pro X, and Surface Laptop Go. 
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 10/14/2022
ms.reviewer: 
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop Studio
- Surface Pro 9
- Surface Pro 9 with 5G
- Surface Pro 8
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop Go 2
- Surface Laptop 3
- Surface Laptop 4
- Surface Laptop 5
- Surface Studio 2+
- Windows 10
- Windows 11


ms.custom: 
- CI 121887
- CSSTroubleshoot 
---
# Best practices for SSD removal from compatible Surface devices

> [!IMPORTANT]
> This article is intended for use by qualified IT technicians in an enterprise organization only. It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:

- Surface Laptop Studio
- Surface Pro 9
- Surface Pro 9 with 5G
- Surface Pro 8
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop Go 2
- Surface Laptop 3
- Surface Laptop 4
- Surface Laptop 5
- Surface Studio 2+

> [!WARNING]
> Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.  Always use caution when you undertake such activities. Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440). We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."

## Prerequisites

> [!IMPORTANT]
> This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."

## Prepare for SSD removal

### Install the latest updates

Before you begin, make sure that your version of Windows has the latest updates installed:

1. Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.
2. Install all available updates.
3. Verify any passwords that are necessary to access the device.  

## Manage BitLocker

> [!NOTE]
> This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks. For more information, see  [BitLocker Recovery Guide](/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).

### If BitLocker encryption is disabled during SSD removal and replacement

If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:

1. In **Settings**, type **BitLocker** and then select **Manage BitLocker**.
2. Select **Turn Off BitLocker**.
3. Power down the device.

### If BitLocker encryption is enabled during SSD removal and replacement

If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:

1. In **Settings**, type **BitLocker**.
2. Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.
2. Insert a USB drive.
4. Save the recovery key to USB storage.  
5. Remove the USB drive.  
6. Power down the device.

## Remove and replace SSD

1. Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).
2. Put the original SSD into a new device and connect the new device to a wired internet connection.
3. Power on the new device. The device may go through a firmware update during startup.  

## After SSD removal and replacement

### Manage unencrypted SSDs

If the SSD is unencrypted during the transfer, follow these steps:

1. Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).  
2. Enter the password and sign in pending completion of two-factor authentication (if applicable).
3. After you are fully signed in, go to **Start** > **Account** > **Sign out**.  
4. Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.
    - If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.  
6. Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.  
7. Check for Windows activation by navigating to **Settings** > **Activation**.  If you see any error messages, select **Troubleshoot**.
8. Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.  

### Managing encrypted SSDs

> [!NOTE]
> You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.

If the SSD is encrypted during the transfer, follow these steps:

1. Insert the USB drive that contains the BitLocker recovery key into the second device.
2. Open the .txt file that contains the BitLocker recovery key.
3. Manually enter the BitLocker recovery key on the new device that contains the original SSD.  
4. After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).  
5. Enter the password and sign in, pending completion of two-factor authentication (if applicable).
6. After you are fully signed in, go to **Start** > **Account** > **Sign out**.  
7. Sign back in by using the password, and then set up Windows Hello and add a PIN.
8. If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.  
9. Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.  
10. To check Windows activation, select **Settings** > **Activation**.  If you see any error messages, select **Troubleshoot**.
11. To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.

## Learn more

- [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440)
- [BitLocker Recovery Guide](/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Still need help? Go to [Microsoft Community](https://answers.microsoft.com/).
