---
title: Create and test a device account (Surface Hub)
description: This topic introduces how to create and test the device account that Microsoft Surface Hub uses to communicate with Microsoft Exchange and Skype.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: create and test device account, device account, Surface Hub and Microsoft Exchange, Surface Hub and Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/01/2021
ms.localizationpriority: medium
ms.audience: itpro
---

# Create and test a device account (Surface Hub)

Creating a Surface Hub device account (also known as a resource account/room mailbox) allows the Surface Hub to receive, approve, or decline meeting requests and join meetings.

Once the device account is provisioned on a Surface Hub, people can add this account to a meeting invitation the same way that they would invite a conference room. 

You can configure the device account during the [Out-of-Box Experience (OOBE) setup](first-run-program-surface-hub.md). If needed, you can also change it later in **Settings** > **Surface Hub** > **Accounts**.

## Configuration overview

This table explains the main steps and configuration decisions when you create a device account.
 
| Step | Description                     |  Purpose                             |
|------|---------------------------------|--------------------------------------|
| 1    | Create a logon-enabled room mailbox (Exchange Online or Exchange Server 2016 and later) | This type of mailbox allows the device to maintain a meeting calendar, receive meeting requests, and send mail. It must be logon-enabled in order to be used with a Surface Hub. |
| 2    | Configure mailbox properties | The mailbox must be configured with the correct properties to enable the best meeting experience on Surface Hub. For more information on mailbox properties, see [Mailbox properties](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Ensure that Exchange Web Services (EWS) is enabled, and multi-factor authentication (MFA) is disabled | The Surface Hub uses EWS to sync its calendar. If you don't allow EWS in your environment by default, the Hub mailbox would need to have it explicitly enabled. As the Surface Hub logs into Exchange in the background without user interaction, it cannot respond to any interactive prompts, such as MFA. The device account you create must be excluded from any such authentication requirements. Otherwise, Surface Hub can't sync mail and calendar info. |
| 4    | Enable the account for Teams or Skype for Business (Skype for Business Server 2015 and later) | Skype for Business or Teams must be enabled to use conferencing features like video calls, IM, and screen sharing. For more information on the licenses that enable Teams, see [Teams Meeting Room licensing](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-licensing) and [Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description). |
| 5    | (Optional) Disable password expiration | To simplify management, you can turn off password expiration for the device account and allow Surface Hub to automatically rotate the device account password. For more information about password management, see [Password management](password-management-for-surface-hub-device-accounts.md).  |
| 6    | (Optional) Configure Exchange policies to allow ActiveSync | With certain on-premises Exchange Server & Active Directory deployments, ActiveSync will be used to sync the device account mail and calendar info. For more information about the policies to configure, see [ActiveSync policies for Surface Hub accounts](apply-activesync-policies-for-surface-hub-device-accounts.md). |

> [!NOTE]  
> The Surface Hub device account doesn't support third-party federated Identity Providers (IdPs) and must authenticate via Active Directory or Azure Active Directory.

## Detailed configuration steps 

We recommend setting up your Surface Hub device accounts using remote Windows PowerShell. Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new resource accounts, or validate existing resource accounts you have in order to help you turn them into compatible Surface Hub device accounts. If you prefer, you can choose an option from the table below, and follow the detailed PowerShell steps based on your organization deployment.

| Organization deployment             |  Description                  |        Format to use during Surface Hub setup
|---------------------------------|--------------------------------------|
| [Online deployment (Microsoft 365 or Office 365)](https://docs.microsoft.com/microsoftteams/rooms/with-office-365) |Your organization's environment is deployed entirely on Microsoft 365 or Office 365. | username@domain.com |
| [Hybrid deployment (Exchange on-premises)](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-on-premises) | Your organization has a mix of services, with Exchange Server hosted on premises and Microsoft Teams online. | username@domain.com if [Hybrid Modern Authentication](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) is enabled in Exchange, DOMAIN\username otherwise |
| [Hybrid deployment (Exchange Online)](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-online) | Your organization has a mix of services, with Skype for Business Server hosted on premises and Exchange Online. | username@domain.com if [Hybrid Modern Authentication](https://docs.microsoft.com/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) is enabled in SfB, DOMAIN\username otherwise |
| [On-premises deployment (single forest)](https://docs.microsoft.com/microsoftteams/rooms/with-skype-for-business-server-2015) | Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted in a single-forest environment.  | DOMAIN\username |
| [On-premises deployment (multiple forests)](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted in a multi-forest environment. | ACCOUNTFOREST\username |


## Account verification and testing

There are two methods available that you can use to validate and test a Surface Hub device account: [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) and the [Surface Hub Hardware Diagnostic app](https://www.microsoft.com/store/apps/9nblggh51f2g). The account provisioning script can validate a previously-created device account using PowerShell from your PC. The Surface Hub Hardware Diagnostic app is installed on your Surface Hub and provides detailed feedback about signin and communication failures. Both are valuable tools to test newly created device accounts and should be used to ensure optimal account availability.
