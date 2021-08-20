---
title: Configure networking and Quality of Service for Microsoft Teams Room on Surface Hub
description: This article explains requirements and recommendations for networking and Quality of Service to optimize Microsoft Teams Rooms on Surface Hub.
keywords: Teams Rooms, Surface Hub, Intune, QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/23/2021
ms.reviewer: 
manager: laurawi
ms.localizationpriority: medium
---

# Configure networking and Quality of Service for Microsoft Teams Rooms on Surface Hub

This article explains how to prepare your environment to optimize Microsoft Teams Rooms on Surface Hub.

## Create and test a device account

A device account is an account that the Microsoft Teams Rooms client uses to access features from Exchange, like calendar, and to enable Skype for Business. [See Create and test a device account](create-and-test-a-device-account-surface-hub.md)

## Check network availability

> [!TIP]
> We strongly recommend using the practices for network configuration listed at
[Microsoft 365 network connectivity principles](https://aka.ms/pnc)

Teams Rooms on Surface Hub must have access to a network that meets these requirements:

- Access to your Active Directory or Azure Active Directory (Azure AD) instance
- Access to a server that can provide an IP address using DHCP. Microsoft Teams Rooms on Surface Hub cannot be configured with a static IP address.
- Access to HTTP ports 80 and 443.
- TCP and UDP ports configured as described in Port and protocol requirements for [Microsoft 365 and Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges) for Microsoft Teams.

> [!IMPORTANT]
> Microsoft Teams Rooms does not support proxy authentication as it may interfere with regular operations of Teams. Ensure that Surface Hub devices or Microsoft 365 service endpoints have been exempted from proxy authentication before going into production with Teams Rooms on Surface Hub.

## Implement Quality of Service (QoS) on Surface Hub

Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.
Configuring QoS for Microsoft Teams on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).

To configure QoS for Surface Hub using Microsoft Intune:

1. In Intune, [create a custom policy](/intune/custom-settings-configure).
2. In **Custom OMA-URI Settings**, select **Add**. For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.
3. To ensure optimal video and audio quality on Surface Hub, add the following QoS settings to the device.

| Name                  | Description           | OMA-URI                                                                        | Type    | Value       |
| --------------------- | --------------------- | ------------------------------------------------------------------------------ | ------- | ----------- |
| **Audio Ports**       | Audio Port range      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/SourcePortMatchCondition      | String  | 50000-50019 |
| **Audio DSCP**        | Audio ports marking   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction                    | Integer | 46          |
| **Video Port**        | Video Port range      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/SourcePortMatchCondition      | String  | 50020-50039 |
| **Video DSCP**        | Video ports marking   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction                    | Integer | 34          |
| **Sharing Port**      | Sharing Port range    | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/SourcePortMatchCondition    | String  | 50040-50059 |
| **Sharing DSCP**      | Sharing ports marking | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction                  | Integer | 18          |

4. When the policy has been created, deploy it to Surface Hub.

## Learn more

- [Implement Quality of Service (QoS) in Microsoft Teams](/microsoftteams/qos-in-teams)
