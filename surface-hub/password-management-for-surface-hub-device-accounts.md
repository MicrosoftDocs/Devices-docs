---
title: Password management (Surface Hub)
description: Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 07/27/2017
ms.localizationpriority: medium
---

# Password management (Surface Hub)

Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device. For security reasons, you may want to change (or "rotate") this password regularly. However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled. You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.

To simplify password management for your Surface Hub device accounts, there are two options:

1. Turn off password expiration for the device account.
2. Allow the Surface Hub to automatically rotate the device account’s password.

## Turn off password rotation for the device account

Set the device account’s **PasswordNeverExpires** property to True. You should verify whether this meets your organization’s security requirements.

## Allow the Surface Hub to automatically rotate the device account’s password

The Surface Hub can automatically change a device account's password without requiring you to manually update it. You can enable this feature in **Settings** > **Surface Hub** > **Accounts**. If you turn on Password Rotation, the Surface Hub will attempt to change the password every 7 days during maintenance hours. Passwords do not change during a meeting. If 7 days have passed since the last password rotation, but the Surface Hub was off, it will attempt to change the password immediately when turned on or every 10 minutes until successful.

The automatically generated passwords contain 15-32 characters including a combination of uppercase and lowercase letters, numbers, and special characters. Note that when the device account's password is changed, you will not be shown the new password. If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Microsoft 365 admin portal to reset the password.

> [!IMPORTANT]
> The [device affiliation](prepare-your-environment-for-surface-hub.md) option selected during initial setup of the Surface Hub has an impact on which device account format can be used with password rotation. Hubs affiliated with an on-premise Active Directory can only rotate passwords of device accounts entered in **domain\username** format. Hubs affiliated with an Azure Active Directory can only rotate passwords of device accounts entered in `username@domain.com` format, but only if the account is cloud-only or if the AAD domain is configured for [cloud authentication](/azure/active-directory/hybrid/choose-ad-authn#cloud-authentication) and [password writeback](/azure/active-directory/authentication/concept-sspr-writeback).
