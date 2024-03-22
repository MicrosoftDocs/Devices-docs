---
title: "Deploy Surface Hub 3 with Windows Autopilot & Teams Rooms Auto-login"
description: "This page provides a roadmap for deploying Surface Hub 3 using Windows Autopilot and Teams Rooms Auto-login."
ms.service: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: overview
ms.date: 03/26/2024
ms.localizationpriority: Medium
appliesto:
- Surface Hub 3
---

# Deploy Surface Hub 3 with Windows Autopilot & Auto-login of Teams Rooms 

In the evolving landscape of digital workplaces, the efficiency of setting up and managing devices is paramount. Windows Autopilot represents a pivotal shift in how IT admins deploy Windows devices, offering a cloud-based solution that simplifies the entire process. This service dramatically reduces the traditional complexities associated with device setup, enabling organizations to get their devices ready for productive use with minimal effort.

While Windows Autopilot has been available for years to enable streamlined deployment of individual users’ Windows PCs, a similarly streamlined deployment option for shared appliance-like devices like Surface Hub and Microsoft Teams Rooms on Windows systems has not been available – until now.

Microsoft Teams Rooms on Windows now supports streamlined deployment via Windows Autopilot and a new Auto-login capability for Teams Rooms. Together, these two components offer a customers a seamless end-to-end deployment experience of Teams Rooms on Windows devices using consistent IT management interfaces – Microsoft Intune and the Teams Rooms Pro Management Portal. 

## Prerequisites

If you're new to Autopilot, it's recommended to review the following articles: 

- [Overview of Windows Autopilot](/mem/autopilot/windows-autopilot)
- [Windows Autopilot and Surface devices](/surface/windows-autopilot-and-surface-devices)
- [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot)
- [Surface Registration Support for Windows Autopilot](/surface/surface-autopilot-registration-support)

In addition, review the new guidance from Teams Rooms.  

## How it works

Windows Autopilot leverages Azure cloud services, including Microsoft Entra-ID (formerly known as Azure AD) and Microsoft Endpoint Manager (formerly known as Intune). This cloud-based approach to device management and deployment allows for the automation and remote management capabilities that Autopilot delivers.

IT admins create deployment profiles in Microsoft Endpoint Manager (or another MDM service). These profiles contain the configuration settings for the devices, such as language, region, network configuration, and the steps required in the Out-of-Box Experience (OOBE). Once profiles are created, they are assigned to the registered devices based on certain criteria, like device model or purchase order. To learn more, see [Configure Autopilot profiles](/autopilot/profiles).

When a new device is turned on and connected to the internet for the first time, it contacts the Windows Autopilot service. The service recognizes the device based on its hardware ID and retrieves the deployment profile assigned to it. The OOBE then customizes itself according to the settings defined in the profile, automating steps that would traditionally require manual input, such as setting up a Wi-Fi connection, accepting license agreements, and configuring user accounts.

## Prepare for Autopilot deployment

For Surface Hub 3, Hub 2S devices [software-migrated to the Teams Rooms on Windows platform](surface-hub-2s-migrate-to-mtr-w.md), and Hub 2S devices [upgraded with the Surface Hub 3 Pack compute cartridge](install-manage-surface-hub-3-pack.md), support for Windows Autopilot and Auto-login of Teams Rooms brings a set of unique advantages. These latest Hub devices deliver the most value via a seamless integration into corporate environments. 

As shown in the following table, the process of enabling Autopilot and Teams Rooms Auto-Login varies across the latest Hub devices. But once devices are registered with the Autopilot service, regardless of the method used, they each benefit equally from the same automated configuration and deployment capabilities in Autopilot and Teams Rooms Auto-login. This includes automatic enrollment in management tools, application of settings and policies, and provisioning of user accounts and applications, which can all occur without direct IT intervention after the device is in the user's hands.


| Device                 | Description                                                                                                           | Supported Autopilot enrollment methods           | Required steps |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------      | -------------- |
| Surface Hub 3          | Surface Hub 3 devices shipped from the factory                                                                      | Partner-driven on by behalf of customer (recommended)| [Enroll into Autopilot](#enroll-surface-hub-3)   |
| Surface Hub 3          | Hub 2S devices [upgraded with the Surface Hub 3 Pack compute cartridge](install-manage-surface-hub-3-pack.md)         | Customer-driven directly in Intune       | [Manually register devices & enroll](#manually-register--enroll-surface-hub-3-devices-upgraded-via-surface-hub-3-pack)    |
| Surface Hub 2S         | Surface Hub 2S devices [software-migrated to the Teams Rooms on Windows platform](surface-hub-2s-migrate-to-mtr-w.md) | Customer-driven directly in Intune      | [Manually register devices & enroll](#manually-register--enroll-surface-hub-2s-devices-migrated-to-teams-rooms-on-windows)   |


### Enroll Surface Hub 3  

New Surface Hub 3 devices that ship from the factory are fully ready for Autopilot use. It's recommended to use take advantage of the expertise of certified partners who can create the requisite Autopilot profiles and enroll Surface Hub 3 in Autopilot.   

### Manually register & enroll Surface Hub 3 devices upgraded via Surface Hub 3 Pack

When you updgrade Surface Hub 2S to Surface Hub 3, a new hardware hash is created. To proceed, you first need to manually extract the hardware hash. 

### Manually register & enroll Surface Hub 2S devices migrated to Teams Rooms on Windows

Manual extraction of hardware hash required


## Learn more

- [Surface Hub support coming for Windows Autopilot](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-support-coming-for-windows-autopilot/ba-p/3977848)
- [Microsoft Teams Rooms and Devices: Microsoft Ignite 2023](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-rooms-and-devices-microsoft-ignite-2023/ba-p/3975581)