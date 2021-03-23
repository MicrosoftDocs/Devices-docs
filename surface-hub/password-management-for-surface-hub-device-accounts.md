---
title: Password management (Surface Hub)
description: Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: 
manager: laurawi
keywords: password, password management, password rotation, device account
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
---

# Password management (Surface Hub)

Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device. For security reasons, you may want to change (or "rotate") this password regularly. However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled. You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.

To simplify password management for your Surface Hub device accounts, there are two options:

1.  Turn off password expiration for the device account.
2.  Allow the Surface Hub to automatically rotate the device account’s password.


## Turn off password rotation for the device account

Set the device account’s **PasswordNeverExpires** property to True. You should verify whether this meets your organization’s security requirements.


## Allow the Surface Hub to automatically rotate the device account’s password

The Surface Hub can automatically change a device account's password without requiring you to manually update it. You can enable this feature in **Settings** > **Surface Hub** > **Account**. If you turn on Password Rotation, the Surface Hub will attempt to change the password every 7 days during maintenance hours. Passwords do not change during a meeting. If 7 days have passed since the last password rotation, but the Surface Hub was off, it will attempt to change the password immediately when turned on or every 10 minutes until successful.

The automatically generated passwords contain 15-32 characters including a combination of uppercase and lowercase letters, numbers, and special characters. Note that when the device account's password is changed, you will not be shown the new password. If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Microsoft 365 admin portal to reset the password.

> [!IMPORTANT]
> The format used when adding the device account to the Surface Hub has an impact on which [device affiliation](prepare-your-environment-for-surface-hub.md) option must be used in order for password rotation to work. If adding the account in **domain\username** format, affiliate the Hub with on-premises Active Directory during initial setup. If adding the account in **username@domain.com** format, affiliate the Hub with Azure Active Directory during initial setup. Otherwise, password rotation will not work.
