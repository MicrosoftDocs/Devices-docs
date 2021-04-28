---
title: Setup worksheet (Surface Hub)
description: When you've finished pre-setup and are ready to start first-time setup for your Microsoft Surface Hub, make sure you have all the information listed in this section.
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: 
manager: laurawi
keywords: Setup worksheet, pre-setup, first-time setup
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/21/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
---

# Setup worksheet (Surface Hub)


When you've finished pre-setup and are ready to start first-time setup for your Microsoft Surface Hub, make sure you have all the information listed in this section.

You should fill out one list for each Surface Hub you need to configure, although some information can be used on all Surface Hubs, like the proxy information or domain credentials. Some of this information may not be needed, depending on how you've decided to configure your device, or depending on how the environment is configured for your organization's infrastructure.

When setup is finished, see checklist below for post-deployment tasks.


| Property                                                          | What this is used for                                                                                                                                                                                                                                                                                                                                                           | Example                                                                                                            |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Proxy information                                                 | If your network uses a proxy for network and/or Internet access, you must provide a script or server/port information.                                                                                                                                                                                                                                                          | Proxy script: http://contoso/proxy.pa <br><br>- OR - <br><br>Server and port info: 10.10.10.100, port 80           |
| Wireless network credentials (username and password)              | If you decide to connect your device to Wi-Fi, and your wireless network requires user credentials.                                                                                                                                                                                                                                                                             | admin1@contoso.com, #MyPassw0rd                                                                                    |
| Device account UPN or Domain\username and device account password | This is the User Principal Name (UPN) or the domain\username, and the password of the device account. Mail, calendar, and Skype for Business depend on a compatible device account.                                                                                                                                                                                             | UPN: ConfRoom15@contoso.com, #Passw0rd1 <br><br>- OR - <br><br>Domain and username: CONTOSO\ConfRoom15, #Passw0rd1 |
| Device account Microsoft Exchange server                          | This is the device account's Exchange server. Mail, calendar, and Skype for Business depend on a compatible device account. For mail and calendar to work, the device account must have a valid Exchange server. The device will try to find this automatically.                                                                                                                | outlook.office365.com                                                                                              |
| Device account Session Initiation Protocol (SIP) address          | This is the device account's Skype for Business SIP address. Mail, calendar, and Skype for Business depend on a compatible device account. For Skype for Business to work, the device account must have a valid SIP address. The device will try to find this automatically.                                                                                                    | sip: ConfRoom15@contoso.com                                                                                        |
| Friendly name                                                     | The friendly name of the device is the broadcast name that people will see when they try to wirelessly connect to the Surface Hub. This name will be displayed prominently on the Surface Hub's screen. We suggest that the friendly name you choose is recognizable and unique so that people can distinguish one Surface Hub from another when trying to connect.             | Conference Room 15                                                                                                 |
| Device name                                                       | The device name is the name that will be used for domain join, and is the identity you will see in your MDM provider if the device is enrolled into MDM. The device name you choose must not be the same name as any other device on the user’s Active Directory domain (if you decide to domain join the device). The device cannot join the domain if its name is not unique. | confroom15                                                                                                         |

#### If you’re joining Azure AD

| Property                                                 | What this is used for                                                                                                                                                                                       | Example                         |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| Azure AD tenant user credentials (username and password) | If you decide to have people in your Azure Active Directory (Azure AD) organization become admins on the device, then you'll need to join Azure AD. To join Azure AD, you will need valid user credentials. | admin1@contoso.com, #MyPassw0rd |

 

#### If you’re joining a domain

| Property                                           | What this is used for                                                                                                                                                                                                                        | Example                                         |
| -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| Domain to join                                     | This is the domain you will need to join so that a security group of your choice can be admins for the device. You may need the fully qualified domain name (FQDN).                                                                          | contoso (short name) OR contoso.corp.com (FQDN) |
| Domain account credentials (username and password) | A domain can't be joined unless you provide sufficient account credentials to join the domain. Once you provide a domain to join and credentials to join the domain, then a security group of your choice can change settings on the device. | admin1, #MyPassw0rd                             |
| Admin security group alias                         | This is a security group in your Active Directory (AD); any members of this security group can change settings on the device.                                                                                                                | SurfaceHubAdmins                                |

 
 

#### If you're using a local admin

| Property                                                | What this is used for                                                                                   | Example             |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------- |
| Local admin account credentials (username and password) | If you decide not to join an AD domain or Azure AD, you can create a local admin account on the device. | admin1, #MyPassw0rd |

 

#### If you need to install certificates or apps

| Property  | What this is used for                                                                                                                                                                                                                                                                                 |
| --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| USB drive | If you know before first run that you want to install certificates or universal apps, follow the steps in [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md). Your provisioning packages will be created on a USB drive. |

 

## Post deployment checklist


|Check|Response|
|--- |---- |
|**Device account syncing**| ☐ Yes <br> ☐ No |
|**Bitlocker key**| ☐ Saved to file (no affiliation) <br> ☐ Saved in Active Directory (AD affiliation) <br>☐ Saved in Azure AD (Azure AD affiliation) |
|**Device OS updates**| ☐ Completed |
|**Windows Store updates**| ☐ Automatic <br> ☐ Manual |
|**Microsoft Teams scheduled meeting**| ☐ Confirmation email received <br> ☐ Meeting appears on start screen <br>  ☐ One-touch join functions <br> ☐ Able to join audio <br> ☐ Able to join video <br> ☐ Able to share screen ||
|**Skype for Business scheduled meeting**| ☐ Confirmation email received <br> ☐ Meeting appears on start screen <br> ☐ One-touch join functions correctly <br> ☐ Able to join audio <br> ☐ Able to join video <br> ☐ Able to share screen <br> ☐ Able to send/receive IM |
|**Scheduled meeting when already invited**| ☐ Meeting declined |
|**Microsoft Teams ad-hoc meeting**| ☐ Invite other users work <br> ☐ Able to join audio <br> ☐ Able to join video <br> ☐ Able to share screen |
|**Skype for Business scheduled meeting**| ☐ Invite other users work <br> ☐ Able to join audio <br> ☐ Able to join video <br> ☐ Able to share screen <br> ☐ Able to send/receive IM |
|**Microsoft Whiteboard**| ☐ Launch from Welcome / Start screen <br> ☐ Launch from Microsoft Teams | 
|**Incoming Skype/Teams call**| ☐ Able to join audio<br>☐ Able to join video <br> ☐ Able to share screen <br> ☐ Able to send/receive IM (Skype for Business only) |
|**Incoming live video streams**| ☐ Maximum 2 (Skype for Business) <br> ☐ Maximum 4 (Microsoft Teams) |
|**Microsoft Teams Mode 0 behavior**| ☐ Skype for Business tile on Welcome/Start screen <br> ☐ Can join scheduled Skype for Business meetings (Skype UI) <br> ☐ Can join scheduled Teams meetings (Teams UI) |
|**Microsoft Teams Mode 1 behavior**| ☐ Teams tile on Welcome/Start screen <br> ☐ Can join scheduled Skype for Business meetings (Skype UI) <br> ☐ Can join scheduled Teams meetings (Teams UI) |
|**Microsoft Teams Mode 2 behavior**| ☐ Teams tile on Welcome / Start screen <br> ☐ Can join scheduled Teams meetings <br> ☐ Fail to join Skype for Business meetings |


