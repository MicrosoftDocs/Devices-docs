---
title: "Deploy Surface Hub with Windows Autopilot & Teams Rooms Auto-login"
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

# Deploy Surface Hub with Windows Autopilot & Auto-login of Teams Rooms 

## Scope

Surface Hub support for seamless end-to-end deployment with Windows Autopilot and Auto-login of Teams Rooms is scoped only to Surface Hub devices running the Microsoft Teams Rooms on Windows platform—specifically new Surface Hub 3 devices, Surface Hub 2S devices upgraded with the Surface Hub 3 Pack compute cartridge, and Surface Hub 2S devices software-migrated to the Teams Rooms on Windows platform. 


## Background

In the evolving landscape of digital workplaces, the efficiency of setting up and managing devices is paramount. Since it was introduced, Windows Autopilot has enabled a pivotal shift in how IT admins deploy Windows devices, offering a cloud-based solution that simplifies the entire process. This service dramatically reduces the traditional complexities associated with device setup, enabling organizations to get their devices ready for productive use with minimal effort.

While Windows Autopilot has been available for years to enable streamlined deployment of individual users’ Windows PCs, a similarly streamlined deployment option for shared appliance-like devices like Surface Hub and Microsoft Teams Rooms on Windows systems has not been available – until now.

Microsoft Teams Rooms on Windows now supports streamlined deployment via a combination of Windows Autopilot and a new Auto-login capability for Teams Rooms. Together, these two components offer a customers a seamless end-to-end deployment experience of Teams Rooms on Windows devices using consistent IT management interfaces – Microsoft Intune and the Teams Rooms Pro Management Portal. 

## Prerequisites

If you're new to Autopilot, it's recommended to review the following articles: 

- [Overview of Windows Autopilot](/mem/autopilot/windows-autopilot)
- [Windows Autopilot and Surface devices](/surface/windows-autopilot-and-surface-devices)
- [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot)
- [Surface Registration Support for Windows Autopilot](/surface/surface-autopilot-registration-support)

Even if you are familiar with Autopilot in general, to understand nuances for Teams Rooms devices, and to learn about configuring the new Auto-login of Teams Rooms capability, we recommend reviewing new documentation from Teams Rooms on Windows Autopilot and Auto-login of Teams Rooms.  

## How Autopilot works

Windows Autopilot leverages Azure cloud services, including Microsoft Entra-ID (formerly known as Azure AD) and Microsoft Endpoint Manager (formerly known as Intune). This cloud-based approach to device management and deployment allows for the automation and remote management capabilities that Autopilot delivers.

IT admins create deployment profiles in Microsoft Endpoint Manager (or another MDM service). These profiles contain the configuration settings for the devices, such as language, region, network configuration, and the steps required in the Windows Out-of-Box Experience (OOBE). Once profiles are created, they are assigned to the registered devices based on certain criteria, like device model or purchase order. To learn more, see [Configure Autopilot profiles](/autopilot/profiles).

When a new device with a supported platform is internet-connected and turned on for the first time, it contacts the Windows Autopilot service. The service recognizes the device based on its hardware ID and retrieves the deployment profile assigned to it. The Windows OOBE then customizes itself according to the settings defined in the profile, automating steps that would traditionally require manual input, such as setting up a Wi-Fi connection, accepting license agreements, and more.

## Prepare your environment with configuration for Windows Autopilot and Auto-login of Teams Rooms

The new guidance from Teams Rooms, including full documentation on the new Auto-login of Teams Rooms capability, covers the specific steps you need to prepare your environment with the necessary configuration prior to Autopilot-enrolling your supported Surface Hub devices and configuring Auto-login of Teams rooms. For example, the documentation covers Microsoft Teams Rooms (and therefore Surface Hub) specific guidance for Profile creation and Enrollment Status Page configuration, relative to the unique characteristics of these devices. Please ensure you have reviewed the documentation and prepared your environment, prior to proceeding with the following enrollment steps.

## Enroll your Surface Hub for Windows Autopilot deployment

For Surface Hub 3, and Surfaace Hub 2S devices [upgraded with the Surface Hub 3 Pack compute cartridge](install-manage-surface-hub-3-pack.md) and Surface Hub 2S devices [software-migrated to the Teams Rooms on Windows platform](surface-hub-2s-migrate-to-mtr-w.md), support for Windows Autopilot and Auto-login of Teams Rooms brings huge value in enabling even more seamless integration into corporate environments. 

As shown in the following table, the process of enrolling a supported version of Surface Hub in Windows Autopilot varies by device type. But once devices are enrolled and registered with the Autopilot service, regardless of the method used, they each benefit equally from the same automated configuration and deployment capabilities of Autopilot. This includes automatic enrollment in management tools, application of settings and policies, and more which can all occur without direct IT intervention after the device is in the user's hands.


| Device                 | Description                                                                                                           | Supported Autopilot enrollment methods           | Required steps | Learn more   |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------      | -------------- |--------------
| Surface Hub 3          | Surface Hub 3 devices shipped from the factory                                                                      | Partner-driven on behalf of customer (recommended)| [Enroll in Autopilot](#enroll-surface-hub-3)   |  [Reseller, distributor, or partner registration](/autopilot/partner-registration)           |
| Surface Hub 3          | Hub 2S devices [upgraded with the Surface Hub 3 Pack compute cartridge](install-manage-surface-hub-3-pack.md)         | Customer-driven directly in Intune       | [Manually register devices & enroll](#manually-register--enroll-surface-hub-3-devices-upgraded-via-surface-hub-3-pack) | [Manually register devices with Windows Autopilot](/autopilot/add-devices)           |
| Surface Hub 2S         | Surface Hub 2S devices being [software-migrated to the Teams Rooms on Windows platform](surface-hub-2s-migrate-to-mtr-w.md) | Customer-driven directly in Intune      | [Manually register devices & enroll](#manually-register--enroll-surface-hub-2s-devices-migrated-to-teams-rooms-on-windows)  | [Manually register devices with Windows Autopilot](/autopilot/add-devices)         |

### Enroll Surface Hub 3  

New Surface Hub 3 devices that ship from the factory are fully ready for Autopilot use. It's recommended to use take advantage of the expertise of certified partners who can create the requisite Autopilot profiles and enroll Surface Hub 3 in Autopilot.

### Manually register & enroll Surface Hub 3 devices upgraded via Surface Hub 3 Pack

When you upgrade Surface Hub 2S to Surface Hub 3, a new hardware hash is created. To proceed, you first need to manually extract the hardware hash. To extract hardware the hardware hash: 

- **In first time setup (OOBE):** At the first Windows OOBE screen, press **Ctrl-Shift-D** to bring up the Diagnostics Page. From this page, you can export logs to a thumb drive. The logs include a CSV file with the hardware hash.
- **From Windows Administrator account:** If you need to extract the hardware hash after already completing first-time setup, press the **Windows** key five times. In the login screen, sign in with your admin credentials, and go to **Settings** **Accounts** **Access work or school** **Export your management log files** > **Export**. By default, the file is saved in the following location: **Users\Public\Documents\MDMDiagnostics**. Open MDMDiagReport, select DeviceHash CSV file, and extract the file to your desired location or USB drive. 

2. Open the CSV file with a plain text editor such as Notepad. Ensure your CSV file meets requirements:

- Device information in the CSV file where you capture hardware hashes should include: Serial number, Windows product ID, and Hardware hash. You can also include an optional group. 

> [!IMPORTANT]
> Do not add Assigned user column in CSV file. 

### Manually register & enroll Surface Hub 2S devices migrated to Teams Rooms on Windows

1. It's recommended to extract the hardware hash and enroll the device in Autopilot **before you migrate** to the Teams Rooms on Windows experience. To extract the hardware hash: 

- **Manually on Surface Hub 2S:** Select **Start** > **All apps** > **Settings** > **View as Admin** > enter admin credentials > **Update & Security** > **Logs** > **Collect logs**. 

- **Remotely via Teams Rooms Admin Center:** Select Teams devices > Surface Hubs (legacy) > select the device > Download device logs. 

2. Open the CSV file with a plain text editor such as Notepad. Ensure your CSV file meets requirements:

- Device information in the CSV file where you capture hardware hashes should include: Serial number, Windows product ID, and Hardware hash. You can also include an optional group. 

> [!IMPORTANT]
> Do not add Assigned user column in CSV file. 

## Learn more

- [Migrate Surface Hub 2S to Microsoft Teams Rooms on Windows](surface-hub-2s-migrate-to-mtr-w.md)
- [Surface Hub support coming for Windows Autopilot](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-support-coming-for-windows-autopilot/ba-p/3977848)
- [Microsoft Teams Rooms and Devices: Microsoft Ignite 2023](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-rooms-and-devices-microsoft-ignite-2023/ba-p/3975581)