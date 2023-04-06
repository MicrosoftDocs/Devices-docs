---
title: Create and test a device account on Surface Hub
description: This article introduces how to create and test the device account that Microsoft Surface Hub uses to communicate with Microsoft Exchange and Skype.
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 03/27/2023
ms.localizationpriority: medium
---

# Create and test a device account on Surface Hub

Creating a Surface Hub device account (also known as a resource account/room mailbox) allows the Surface Hub to receive, approve, or decline meeting requests and join meetings.

Once the device account is provisioned on a Surface Hub, people can add this account to a meeting invitation the same way that they would invite a conference room. 

You can configure the device account during the [Out-of-Box Experience (OOBE) setup](first-run-program-surface-hub.md). If needed, you can also change it later in **Settings** > **Surface Hub** > **Accounts**.

> [!TIP]
> As a companion to this article, we recommend using the [Surface Hub and Microsoft Teams Rooms automated setup guide](https://go.microsoft.com/fwlink/?linkid=2221605) when signed in to the Microsoft 365 Admin Center. This guide will customize your experience based on your environment. If you're hosted in Exchange Online and using Microsoft Teams, the guide will automatically create your device account with the correct settings. Or use it to validate existing resource accounts to help turn them into compatible Surface Hub device accounts. To review best practices without signing in and activating automated setup features, go to the [M365 Setup portal](https://go.microsoft.com/fwlink/?linkid=2222648). 

## Configuration overview

This table explains the main steps and configuration decisions when you create a device account.
 
| Step | Description                     |  Purpose                             |
|------|---------------------------------|--------------------------------------|
| 1    | Create a logon-enabled room mailbox (Exchange Online or Exchange Server 2016 and later) | This type of mailbox allows the device to maintain a meeting calendar, receive meeting requests, and send mail. It must be logon-enabled in order to be used with a Surface Hub. |
| 2    | Configure mailbox properties | The mailbox must be configured with the correct properties to enable the best meeting experience on Surface Hub. For more information on mailbox properties, see [Mailbox properties](exchange-properties-for-surface-hub-device-accounts.md). |
| 3    | Ensure that Exchange Web Services (EWS) is enabled, and multi-factor authentication (MFA) is disabled | The Surface Hub uses EWS to sync its calendar. If you don't allow EWS in your environment by default, the Hub mailbox would need to have it explicitly enabled. As the Surface Hub logs into Exchange in the background without user interaction, it can't respond to any interactive prompts, such as MFA. The device account you create must be excluded from any such authentication requirements. Otherwise, Surface Hub can't sync mail and calendar info. |
| 4    | Enable the account for Teams or Skype for Business (Skype for Business Server 2015 and later) | Skype for Business or Teams must be enabled to use conferencing features like video calls and screen sharing. For more information on the licenses that enable Teams, see [Teams Meeting Room licensing](/MicrosoftTeams/rooms/rooms-licensing) and [Teams service description](/office365/servicedescriptions/teams-service-description). The Teams and SfB applications on the Surface Hub aren't compatible with [Azure AD Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policies) requiring device information (for example, compliance). The device account you create must be excluded from any such CA policies. Otherwise, Surface Hub isn't able to use any conferencing features. |
| 5    | Ensure the device account has a Teams Rooms license to meet new requirements.| Teams Rooms devices logged in with resource accounts that don't have one of the above supported Teams Rooms licenses assigned to them won't be able to sign in after July 1, 2023. <br><br> - Use a sample PowerShell script to [check Teams Rooms licenses on multiple devices](/MicrosoftTeams/rooms/license-check#check-the-license-of-multiple-microsoft-teams-rooms-devices). <br><br> - To learn more, see [New Microsoft Teams Rooms licensing requirements for Surface Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-microsoft-teams-rooms-licensing-requirements-for-surface-hub/ba-p/1669712) |
| 6    | (Optional) Disable password expiration | To simplify management, you can turn off password expiration for the device account and allow Surface Hub to automatically rotate the device account password. For more information about password management, see [Password management](password-management-for-surface-hub-device-accounts.md).  |

> [!NOTE]  
> The Surface Hub device account doesn't support third-party federated Identity Providers (IdPs) and must authenticate via Active Directory or Azure Active Directory.

## Detailed configuration steps 

Device account setup steps can differ based on environment. Select your deployment scenario from the following table to find the appropriate steps, and make note of the "Format to use" column for configuring Surface Hubs after the accounts are provisioned.

| Organization deployment             |  Description                  |        Format to use during Surface Hub setup
|---------------------------------|--------------------------------------|
| [Online deployment (Microsoft 365)](/MicrosoftTeams/rooms/with-office-365?tabs=m365-admin-center) |Your organization's environment is deployed entirely on Microsoft 365. | username@domain.com |
| [Hybrid deployment (Exchange on-premises)](/MicrosoftTeams/rooms/with-office-365?tabs=exchange-server) | Your organization has a mix of services, with Exchange Server hosted on premises and Microsoft Teams online. | username@domain.com if [Hybrid Modern Authentication](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) is enabled in Exchange, DOMAIN\username otherwise |
| [Hybrid deployment (Exchange Online)](/skypeforbusiness/deploy/deploy-clients/hybrid-deployments) | Your organization has a mix of services, with Skype for Business Server hosted on premises and Exchange Online. | username@domain.com if [Hybrid Modern Authentication](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) is enabled in SfB, DOMAIN\username otherwise |
| [On-premises deployment (single forest)](/skypeforbusiness/deploy/deploy-clients/single-forest-on-premises-deployments) | Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted in a single-forest environment.  | DOMAIN\username |
| [On-premises deployment (multiple forests)](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted in a multi-forest environment. | ACCOUNTFOREST\username |

## Microsoft Exchange properties for device account

Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub. The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.

> [!TIP]  
> Automate configuration of recommended Exchange settings via the [Surface Hub and Microsoft Teams Rooms automated setup guide](https://go.microsoft.com/fwlink/?linkid=2221605).

| Property              | Description          | Value                       | Impact                     |
| --------------------- | ------------------------------------- | ----------------------------- | ----------------------------------------------------------- |
| AutomateProcessing    | The AutomateProcessing parameter enables or disables calendar processing on the mailbox.     | AutoAccept            | Surface Hub will be able to automatically accept or decline meeting requests based on its availability.                                |
| AddOrganizerToSubject | The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.  | $False | The welcome screen won't show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject). |
| AllowConflicts        | The AllowConflicts parameter specifies whether to allow conflicting meeting requests.   | $False  | Surface Hub will decline meeting requests that conflict with another meeting’s time.    |
| DeleteComments        | The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.   | $False    | The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.                         |
| DeleteSubject         | The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.    | $False     | Meeting request subjects can be shown on the Surface Hub.  |
| RemovePrivateProperty | The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.     | $False     | Private meeting subjects will show as Private on the welcome screen.       |
| AddAdditionalResponse | The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.    | $True     | When a response is sent to a meeting request, custom text will be provided in the response.     |
| AdditionalResponse    | The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.<br>**Note**  This text won't be sent unless AddAdditionalResponse is set to $True. | Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources. | An additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.                  |

## Apply ActiveSync policies to device accounts 

Surface Hubs on Windows 10 Team 1703 and earlier versions used AGctiveSync to sync mail & calendar.

The Surface Hub requirements for ActiveSync policies in your organization are as follows:

- There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub's device account. If there's such a blocking policy, you need to add the Surface Hub as an allowed device.
- You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False. Other mobile device mailbox policy settings aren't compatible with the Surface Hub.

## Allowing the DeviceID

Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs. To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).

## Setting PasswordEnabled

The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0. To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).


## Learn more

- [Prepare your environment for Surface Hub](prepare-your-environment-for-surface-hub.md)
- [Surface Hub and Microsoft Teams Rooms automated setup guide](https://go.microsoft.com/fwlink/?linkid=2221605)
- [Find Teams Rooms devices with unsupported licenses](/MicrosoftTeams/rooms/license-check)