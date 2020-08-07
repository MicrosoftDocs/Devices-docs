---
title: SSD removal in compatible Surface devices
description: How to transfer an SSD from one Surface device to another.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom: 
- CI 121887
- CSSTroubleshoot 
---
# Best practices for SSD removal in compatible Surface devices

> [!IMPORTANT]
> This article is intended for use by qualified IT technicians in an enterprise organization only. It describes the recommended best practices for use by qualified IT technicians when removing and replacing SSDs in Surface devices with removable SSDs. 

> [!WARNING]
> Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.  Always use caution when undertaking such activities. Follow the safety precautions and procedures identified in the rSSD Removal Guide for Enterprise. Microsoft recommends that you seek professional assistance if you are unable to follow the safety precautions and procedures specified in the rSSD Removal Guide for Enterprise. 

## Prerequisites

> [!IMPORTANT]
> This article assumes you understand the General Safety Precautions and Safety policies and procedures described in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).

## Prepare for SSD removal 

### Install the latest updates 

Before you begin, make sure your version of Windows has the latest updates.

1.	Go to **Start** > **Settings** > **Update & Security** and select **Check for updates**. Install all available updates.  

2.	Confirm that you have any passwords needed to access the device.  
 
## Manage Bitlocker 

> [!NOTE]
> This section includes recommendations for organizations that have enabled BitLocker encryption for hard drives. For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan). 

### If BitLocker encryption is disabled during SSD removal and replacement

If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:

1.	In **Settings**, type **Bitlocker** and select **Manage Bitlocker**. 
2.	Select **Turn Off Bitlocker**. 
3.	Power down the device. 

### If BitLocker encryption is enabled during SSD removal and replacement

If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:

1.	Go to **Settings** and type **Bitlocker**.
2. Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.
2.	Insert a USB drive. 
3.	Save the recovery key to USB storage.  
4.	Remove the USB drive.  
5.	Power down the device. 

## Remove and replace the SSD 

1.	Remove the SSD using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440). 
2. Place the original SSD in a new device and connect the new device to a wired internet connection.
2.	Power on the new device. The device may go through a firmware update during startup.  
 
## After SSD removal and replacement

### Manage unencrypted SSDs 

If the SSD remains unencrypted during the transfer, complete the following: 

1.	Go to **Sign-In Options** > **Password** (represented as the key icon on the left side).  
2.	Enter the password and sign in pending completion of two-factor authentication (if applicable).
3.	Once fully signed in, go to **Start** > **Account** > **Sign out**.  
4.	Sign back in with the password and set up Windows Hello and a PIN when prompted. 
    - If the device was BitLocker-disabled to facilitate SSD removal and replacement and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.  
6.	Run **SDT** to confirm full device functionality.  
7.	Check for Windows activation by navigating to **Settings** > **Activation**.  If there are any error messages, select **Troubleshoot**. 
8.	Check the Office account by opening the **Office App**, then navigate to **File** > **Account** and check for any error messages.  

### Managing encrypted SSDs 

> [!NOTE]
> You will need a second device to read the BitLocker Recovery key that was saved on the USB drive. 

If the SSD remained encrypted during the transfer, complete the following:

1.	Insert the USB drive containing the Bitlocker Recovery key into the second device. 
2.	Open the .txt file containing the Bitlocker Recovery key. 
3.	Manually enter the Bitlocker Recovery key into the new device that contains the original SSD.  
4.	After you have successfully entered the BitLocker Recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).  
5.	Enter the password and sign in, pending completion of two-factor authentication (if applicable) 
6.	Once fully signed in, go to **Start** > **Account** > **Sign out**.  
7.	Sign back in with the password and set up Windows Hello and add a PIN. 
8.	If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.  
9.	Run **SDT** to confirm full device functionality.  
10.	Check Windows activation by navigating to **Settings** > **Activation**.  If there are any error messages, select **Troubleshoot**.
11.	To check the Office Account, open the **Office App**, then go to **File** > **Account** and check for any error messages.

## More information 

For more information, see the following articles:

- [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440)
- [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

Still need help? Go to [Microsoft Community](https://answers.microsoft.com/).