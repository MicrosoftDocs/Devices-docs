---
title: "Prepare your environment for Surface Hub 2S"
description: "Learn what you need to do to prepare your environment for Surface Hub 2S."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 2/26/2021
ms.localizationpriority: Medium
---

# Prepare your environment for Surface Hub 2S

## Office 365 readiness

If you use Exchange Online, Skype for Business Online, Microsoft Teams, or Microsoft Whiteboard, and intend to manage Surface Hub 2S with Intune, first review the [Office 365 requirements for endpoints](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).

Office 365 endpoints help optimize your network by sending all trusted Office 365 network requests directly through your firewall, bypassing all additional packet-level inspection or processing. This feature reduces latency and your perimeter capacity requirements.

Microsoft regularly updates the Office 365 service with new features and functionality, which may alter required ports, URLs, and IP addresses. To evaluate, configure, and stay up to date with changes, subscribe to the [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).

> [!NOTE]
> Surface Hub works with Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015, or Skype for Business Online.
Earlier platforms, such as Lync Server 2013, are not supported. Surface Hub is not supported in GCC-High or DoD environments.


## Device affiliation

Use Device affiliation to manage user access to the Settings app on Surface Hub 2S.
With the Windows 10 Team operating system (that runs on Surface Hub 2S),  only authorized users can adjust settings using the Settings app. Since choosing the affiliation can impact feature availability, plan appropriately to ensure that users can access features as intended.

> [!NOTE]
> You can only set Device affiliation during the initial out-of-box experience (OOBE) setup. If you need to reset Device affiliation, you’ll have to repeat OOBE setup.

## No affiliation

No affiliation is like having Surface Hub 2S in a workgroup with a different local Administrator account on each Surface Hub 2S. If you choose No affiliation, you must locally save the [BitLocker Key to a USB thumb drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq). You can still enroll the device with Intune; however, only the local admin can access the Settings app using the account credentials configured during OOBE. You can change the Administrator account password from the Settings app.

## Active Directory Domain Services

If you affiliate Surface Hub 2S with on-premises Active Directory Domain Services, you need to manage access to the Settings app using a security group on your domain. This helps ensure that all security group members have permissions to change settings on Surface Hub 2S. Also note the following:

- When Surface Hub 2S affiliates with your on-premises Active Directory Domain Services, the BitLocker key can be saved in the Active Directory Schema. For more information, see [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).

- Your organization’s Trusted Root CAs are pushed to the same container in Surface Hub 2S, which means you don’t need to import them using a provisioning package.

- You can still enroll the device with Intune to centrally manage settings on your Surface Hub 2S.

## Azure Active Directory

When you choose to affiliate your Surface Hub 2S with Azure Active Directory (Azure AD), any user in the Global Admins Security Group can sign in to the Settings app on Surface Hub 2S. You can also configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S. This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access across an entire Azure AD domain. 

If you enabled Intune Automatic Enrollment for your organization, Surface Hub 2S will automatically enroll itself with Intune. The device’s BitLocker key is automatically saved in Azure AD. 

To learn more about managing Surface Hub with Azure AD, see: 

 - [Admin group management](admin-group-management-for-surface-hub.md)
 - [Configure non Global admin accounts on Surface Hub 2S](surface-hub-2s-nonglobal-admin.md)

