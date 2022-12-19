---
title: "Configure password-less sign-in on Surface Hub"
description: "Learn how to simplify signing in to Surface Hub."

ms.prod: surface-hub

author: coveminer
ms.author: hachidan
manager: frankbu

ms.topic: how-to
ms.date: 07/21/2020
ms.localizationpriority: Medium
---

# Configure passwordless sign-in on Surface Hub

 
Passwordless sign-in simplifies access to your apps, meetings, and files. Surface Hub supports signing in using the Microsoft Authenticator app and FIDO2 security keys provided by your organization.

**Important:** This content is intended for users. To use passwordless sign-in, your IT admin must enable passwordless authentication for your organization. For more information, see:

- [Enable passwordless phone sign-in](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Enable passwordless security key sign-in](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## Configure sign-in using Microsoft Authenticator app

**Note:** Starting with Windows 10 Team 2020 Update, users can use their preferred email aliases in Azure AD, as well as their User Principal Name (UPN), to sign in using Microsoft Authenticator. For example, a user can use either their preferred alias (John.Doe@contoso.com) or their UPN (jdoe@contoso.com) to sign in.
 
The Microsoft Authenticator app helps you sign-in to Surface Hub using your mobile device. To configure sign-in using Microsoft Authenticator:


1. On your mobile device, download the Microsoft Authenticator app.
    - Google Android: On your Android device, go to Google Play to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).
    - Apple iOS: On your Apple iOS device, go to the App Store to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).
2. On your PC, [setup the Microsoft Authenticator app from the Security info page](/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) for your work or school account.
3. From the Microsoft Authenticator app on your mobile device, [turn on and use phone sign-in](/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) for your work or school account.

 
## Configure sign-in using FIDO2 security keys

> [!NOTE]
>  Passwordless sign-in on Surface Hub using FIDO2 security keys requires the Windows 10 Team 2020 Update.

> [!IMPORTANT]
> Surface Hub only supports USB security keys.
 
You can also sign into Surface Hub using a FIDO2 security key provided by your organization. 

### To configure sign-in using a security key:


1. On your PC, go to your [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page and sign in to your work or school account.
2. Select **Security info** from the left navigation pane or from the link in the **Security info** block, and then select **Add method** from the **Security info** page.
3. On the **Add a method** page, select **Security key** from the drop-down list, and then select **Add**.
4. On the **Security key** page, choose **USB device**.
5. Have your security key ready and select **Next**.
6. In the dialog box that appears, follow the instructions to insert the security key, create or enter a PIN, and perform the required gesture (either biometric or touch).
7. On the **Security key** page, give your security key a name, then select **Next**.
8. Select **Done** to complete the process.

## Sign-in to Surface Hub

Once you've configured passwordless sign-in, you can use it to make it easier to access your apps, meetings, and files on the Surface Hub:

- Quickly join your meetings and open recent Microsoft 365 files. For more information, see [**Sign in to see your meetings and files**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).
- Quickly sign in to Microsoft apps like Whiteboard, PowerPoint, Word, Excel, OneDrive, and Power BI.
- Quickly sign in to the new Microsoft Edge to access your favorites and browsing preferences. For more information, see [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).
- Once you've signed into Surface Hub, you can use other apps without having to sign in again until you select **End session**. Selecting **End session** deletes your credentials, files, and personal data from the device. For more information, see [End session](finishing-your-surface-hub-meeting.md).


## Learn more

- [Passwordless authentication options for Azure Active Directory](/azure/active-directory/authentication/concept-authentication-passwordless)
- [Passwordless sign-in with the Microsoft Authenticator app](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [Passwordless sign-in using FIDO2 security keys](/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

