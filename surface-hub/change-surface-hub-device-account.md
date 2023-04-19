---
title: Change the Microsoft Surface Hub device account
description: You can change the device account in Settings to either add an account if one wasn't already provisioned, or to change any properties of an account that was already provisioned.
ms.assetid: AFC43043-3319-44BC-9310-29B1F375E672
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 01/23/2023
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
---

# Change the Microsoft Surface Hub device account


You can change the device account in Settings to accomplish the following tasks:

- Add an account if one wasn't already provisioned.
- Change any properties of an account that was already provisioned.

## Device account reference


| Value                                     | Description                                                                                                                                                                                                                              |
| ----------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| User Principal Name                       | The user principal name (UPN) of the device account.                                                                                                                                                                                     |
| Password                                  | The corresponding password of the device account.                                                                                                                                                                                        |
| Domain                                    | The domain that the device account belongs to. Not needed for Microsoft 365 accounts.                                                                                                                          |
| User name                                 | The user name of the device account. Not needed for Microsoft 365 accounts.                                                                                                                                 |
| Session Initiation Protocol (SIP) address | The SIP address of the device account.                                                                                                                                                                                                   |
| Microsoft Exchange server                 | The Exchange server of the device account. The device account’s username and password must be able to authenticate to the specified Exchange server.                                                                             |
| Enable Exchange services                  | When checked, all Exchange services will be enabled (for example, calendar on the welcome screen, emailing whiteboards). When not checked, all Exchange services will be disabled, and the Exchange server doesn't need to be provided. |


## What happens?

The UPN and password are used to validate the account in AD or Azure AD. If the validation fails, you may need to provide the domain and user name.

Mail, calendar, Microsoft Teams, and related resources depend on a compatible device account. For Teams or Skype for Business to work, the device account must have a valid SIP address. The device will try to find the SIP automatically. If an SIP address can't be found, the UPN will be used as the SIP address. If this isn't the SIP address for the account, you'll need to provide the SIP address.

The Exchange server address will need to be provided if the device can't find a server associated with the sign-in credentials. Microsoft Surface Hub will use the Exchange server to talk to ActiveSync, which enables several key features on the device.

## Related articles

- [Manage Microsoft Surface Hub](manage-surface-hub.md)
