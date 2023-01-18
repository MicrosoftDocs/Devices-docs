---
title: Create and test a device account (Surface Hub)
description: This topic introduces how to create and test the device account that Microsoft Surface Hub uses to communicate with Microsoft Exchange and Skype.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 04/01/2021
ms.localizationpriority: medium
---

# Create and test a device account (Surface Hub)

Creating a Surface Hub device account (also known as a resource account/room mailbox) allows the Surface Hub to receive, approve, or decline meeting requests and join meetings.

Once the device account is provisioned on a Surface Hub, people can add this account to a meeting invitation the same way that they would invite a conference room. 

You can configure the device account during the [Out-of-Box Experience (OOBE) setup](first-run-program-surface-hub.md). If needed, you can also change it later in **Settings** > **Surface Hub** > **Accounts**.

> [!TIP]
> As a companion to this article, we recommend reviewing the [Surface Hub and Microsoft Teams Rooms setup guide](https://go.microsoft.com/fwlink/?linkid=2221605). Get the most out of your Surface Hub and Microsoft Teams Rooms devices with Microsoft 365. This guide will customize your experience based on your environment. If you're hosted in Exchange Online and using Microsoft Teams, the guide will automatically create your device account with the correct settings.

## Configuration overview

This table explains the main steps and configuration decisions when you create a device account.
 
| Step | Description                     |  Purpose                             |
|------|---------------------------------|--------------------------------------|
| 1    | Create a logon-enabled room mailbox (Exchange Online or Exchange Server 2016 and later) | This type of mailbox allows the device to maintain a meeting calendar, receive meeting requests, and send mail. It must be logon-enabled in order to be used with a Surface Hub. |
| 2    | Configure mailbox properties | The mailbox must be configured with the correct properties to enable the best meeting experience on Surface Hub. For more information on mailbox properties, see [Mailbox properties](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Ensure that Exchange Web Services (EWS) is enabled, and multi-factor authentication (MFA) is disabled | The Surface Hub uses EWS to sync its calendar. If you don't allow EWS in your environment by default, the Hub mailbox would need to have it explicitly enabled. As the Surface Hub logs into Exchange in the background without user interaction, it cannot respond to any interactive prompts, such as MFA. The device account you create must be excluded from any such authentication requirements. Otherwise, Surface Hub can't sync mail and calendar info. |
| 4    | Enable the account for Teams or Skype for Business (Skype for Business Server 2015 and later) | Skype for Business or Teams must be enabled to use conferencing features like video calls and screen sharing. For more information on the licenses that enable Teams, see [Teams Meeting Room licensing](/MicrosoftTeams/rooms/rooms-licensing) and [Teams service description](/office365/servicedescriptions/teams-service-description). The Teams and SfB applications on the Surface Hub are not compatible with [Azure AD Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policies) requiring device information (e.g. compliance). The device account you create must be excluded from any such CA policies. Otherwise, Surface Hub is not able to use any conferencing features. |
| 5    | (Optional) Disable password expiration | To simplify management, you can turn off password expiration for the device account and allow Surface Hub to automatically rotate the device account password. For more information about password management, see [Password management](password-management-for-surface-hub-device-accounts.md).  |

> [!NOTE]  
> The Surface Hub device account doesn't support third-party federated Identity Providers (IdPs) and must authenticate via Active Directory or Azure Active Directory.

## Detailed configuration steps 

Device account setup steps can differ based on environment. Select your deployment scenario from the table below to find the appropriate steps, and make note of the "Format to use" column for configuring Surface Hubs once the accounts are provisioned.

| Organization deployment             |  Description                  |        Format to use during Surface Hub setup
|---------------------------------|--------------------------------------|
| [Online deployment (Microsoft 365)](/MicrosoftTeams/rooms/with-office-365?tabs=m365-admin-center) |Your organization's environment is deployed entirely on Microsoft 365. | username@domain.com |
| [Hybrid deployment (Exchange on-premises)](/MicrosoftTeams/rooms/with-office-365?tabs=exchange-server) | Your organization has a mix of services, with Exchange Server hosted on premises and Microsoft Teams online. | username@domain.com if [Hybrid Modern Authentication](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) is enabled in Exchange, DOMAIN\username otherwise |
| [Hybrid deployment (Exchange Online)](/skypeforbusiness/deploy/deploy-clients/hybrid-deployments) | Your organization has a mix of services, with Skype for Business Server hosted on premises and Exchange Online. | username@domain.com if [Hybrid Modern Authentication](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) is enabled in SfB, DOMAIN\username otherwise |
| [On-premises deployment (single forest)](/skypeforbusiness/deploy/deploy-clients/single-forest-on-premises-deployments) | Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted in a single-forest environment.  | DOMAIN\username |
| [On-premises deployment (multiple forests)](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted in a multi-forest environment. | ACCOUNTFOREST\username |

For online deployments, there is also a [deployment wizard available for Microsoft 365 admins](https://admin.microsoft.com/Adminportal/Home#/modernonboarding/surfacehubsetupguide) directly in the M365 admin center. This wizard can help create new device accounts, or validate existing resource accounts you have in order to help turn them into compatible Surface Hub device accounts.

## Learn more

- [Surface Hub and Microsoft Teams Rooms setup guide](https://go.microsoft.com/fwlink/?linkid=2221605)