---
title: "Deploy Surface Hub with Windows Autopilot & Teams Rooms Auto-login"
description: "This page provides a roadmap for deploying Surface Hub 3 using Windows Autopilot and Teams Rooms Auto-login."
ms.service: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: conceptual
ms.date: 03/26/2024
ms.localizationpriority: Medium
appliesto:
- Surface Hub 3
- Surface Hub 2S
---

# Deploy Surface Hub with Windows Autopilot & Auto-login of Teams Rooms

## Scope

Surface Hub support for seamless end-to-end deployment with Windows Autopilot and Auto-login of Teams Rooms is scoped only to Surface Hub devices running the Microsoft Teams Rooms on Windows platform: [New Surface Hub 3 devices](surface-hub-3-whats-new.md), Surface Hub 2S devices [upgraded with the Surface Hub 3 Pack compute cartridge](install-manage-surface-hub-3-pack.md) and Surface Hub 2S devices [software-migrated to the Teams Rooms on Windows platform](surface-hub-2s-migrate-to-mtr-w.md).

## Background

In the evolving landscape of digital workplaces, the efficiency of setting up and managing devices is paramount. Since it was introduced, Windows Autopilot has enabled a pivotal shift in how IT admins deploy Windows devices, offering a cloud-based solution that simplifies the entire process. This service dramatically reduces the traditional complexities associated with device setup, enabling organizations to get their devices ready for productive use with minimal effort.

While Windows Autopilot has been available for years to enable streamlined deployment of individual users’ Windows PCs, a similarly streamlined deployment option for shared appliance-like devices like Surface Hub and Microsoft Teams Rooms on Windows systems hasn't been available – until now.

Microsoft Teams Rooms on Windows now supports streamlined deployment via a combination of Windows Autopilot and a new Auto-login capability for Teams Rooms. Together, these two components offer customers a seamless end-to-end deployment experience of Teams Rooms on Windows devices using consistent IT management interfaces – Microsoft Intune and the Teams Rooms Pro Management Portal.

## Prerequisites

If you're new to Autopilot, we recommend review of the following articles:

- [Overview of Windows Autopilot](/mem/autopilot/windows-autopilot)
- [Windows Autopilot and Surface devices](/surface/windows-autopilot-and-surface-devices)
- [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot)
- [Surface Registration Support for Windows Autopilot](/surface/surface-autopilot-registration-support)

Even if you're familiar with Autopilot in general, to understand nuances for Teams Rooms devices, and to learn about configuring the new Auto-login of Teams Rooms capability, we recommend reviewing new documentation from Teams Rooms on [Windows Autopilot and Auto-login of Teams Rooms](https://aka.ms/MTRAutopilotDoc).  

## How Autopilot works

Windows Autopilot uses Azure cloud services, including Microsoft Entra-ID (formerly known as Azure AD) and Microsoft Endpoint Manager (formerly known as Intune). This cloud-based approach to device management and deployment allows for the automation and remote management capabilities that Autopilot delivers.

IT admins create deployment profiles in Microsoft Endpoint Manager or other mobile device management (MDM) service. These profiles contain the configuration settings for the devices, such as language, region, network configuration, and the steps required in the Windows Out-of-Box Experience (OOBE). Once profiles are created, they're assigned to the registered devices based on certain criteria, like device model or purchase order. To learn more, see [Configure Autopilot profiles](/autopilot/profiles).

When a new device with a supported platform is Internet-connected and turned on for the first time, it contacts the Windows Autopilot service. The service recognizes the device based on its hardware ID and retrieves the deployment profile assigned to it. The Windows OOBE then customizes itself according to the settings defined in the profile, automating steps that would traditionally require manual input, such as setting up a Wi-Fi connection, accepting license agreements, and more.

## Prepare your environment with configuration for Windows Autopilot and Auto-login of Teams Rooms

The new guidance from Teams Rooms, including full documentation on the new [Auto-login of Teams Rooms capability](https://aka.ms/MTRAutopilotDoc), covers the specific steps you need to prepare your environment with the necessary configuration before Autopilot-enrolling your supported Surface Hub devices and configuring Auto-login of Teams rooms. For example, the documentation covers Microsoft Teams Rooms (and therefore Surface Hub) specific guidance for Profile creation and Enrollment Status Page configuration, relative to the unique characteristics of these devices. Ensure you have reviewed the documentation and prepared your environment, before proceeding with the following enrollment steps.

## Enroll your Surface Hub for Windows Autopilot deployment

For Surface Hub 3, and Surface Hub 2S devices [upgraded with the Surface Hub 3 Pack compute cartridge](install-manage-surface-hub-3-pack.md) and Surface Hub 2S devices [software-migrated to the Teams Rooms on Windows platform](surface-hub-2s-migrate-to-mtr-w.md), support for Windows Autopilot and Auto-login of Teams Rooms brings huge value in enabling even more seamless integration into corporate environments.

As shown in the following table, the process of enrolling a supported version of Surface Hub in Windows Autopilot varies by device type. But once devices are enrolled and registered with the Autopilot service, regardless of the method used, they each benefit equally from the same automated configuration and deployment capabilities of Autopilot. This includes automatic enrollment in management tools, application of settings and policies, and more, which can all occur without direct IT intervention after the device is in the user's hands.

| Device                 | Description                                                                                                           | Supported Autopilot enrollment methods           | Required steps | Learn more   |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------      | -------------- |--------------
| Surface Hub 3          | Surface Hub 3 devices shipped from the factory                                                                        | - Partner-driven on behalf of customer (recommended)<br><br>- Submit request to [Microsoft support](/surface/surface-autopilot-registration-support) | [Enroll in Autopilot](#enroll-a-new-surface-hub-3-shipped-from-factory)   |  [Reseller, distributor, or partner registration](/autopilot/partner-registration) <br> <br> [Surface partners enabled for Autopilot](/surface/windows-autopilot-and-surface-devices#surface-partners-enabled-for-windows-autopilot)          |
| Surface Hub 3          | Hub 2S devices [upgraded with the Surface Hub 3 Pack compute cartridge](install-manage-surface-hub-3-pack.md)         | - Customer-driven directly in Intune     | [Manually register devices & enroll](#manually-register--enroll-surface-hub-2s-devices-upgraded-with-a-surface-hub-3-pack-compute-cartridge) | [Manually register devices with Windows Autopilot](/autopilot/add-devices)           |
| Surface Hub 2S         | Surface Hub 2S devices being [software-migrated to the Teams Rooms on Windows platform](surface-hub-2s-migrate-to-mtr-w.md) | - Customer-driven directly in Intune      | [Manually register devices & enroll](#manually-register--enroll-surface-hub-2s-devices-being-migrated-to-teams-rooms-on-windows-platform)  | [Manually register devices with Windows Autopilot](/autopilot/add-devices)         |

### Enroll a new Surface Hub 3 shipped from factory  

New Surface Hub 3 devices that ship from the factory are fully ready for Autopilot use. We recommend consulting with certified partners who can Autopilot enroll Surface Hub 3 (or other Autopilot-supporting) devices on behalf of customers, including creating the requisite Autopilot profiles. Learn more, including about how to set up the trust relationship with your partner, in this [documentation](/autopilot/partner-registration). Or see the list of [Surface partners enabled for Autopilot](/surface/windows-autopilot-and-surface-devices#surface-partners-enabled-for-windows-autopilot)

### Manually register & enroll Surface Hub 2S devices upgraded with a Surface Hub 3 Pack compute cartridge

When you upgrade a Surface Hub 2S with a Surface Hub 3 Pack compute cartridge (turning it into a Surface Hub 3), a new hardware hash is generated for that exact unique hardware combination of Surface Hub display chassis and Surface Hub 3 Pack compute cartridge inside. Therefore, in order to proceed with Autopilot enrollment for this new system hardware combination, you first need to manually extract the new hardware hash. Methods to extract the hardware hash vary depending on whether the device has been previously deployed:

1. **If you have never deployed the device before**, you can capture the hardware hash from the first screen of the first time setup (Windows OOBE) process:

   - **In first time setup (OOBE):** At the first Windows OOBE screen, press **Ctrl-Shift-D** to bring up the Diagnostics Page. From this page, you can export logs to a thumb drive. The logs include a CSV file with the hardware hash.

2. **If you have already deployed the device** and it's up and running with the Microsoft Teams Rooms on Windows platform, you can capture the hash from the From Windows Administrator account:

   - **From Windows Administrator account:** Press the **Windows** key five times. In the sign-in screen, sign in with your admin credentials, and go to **Settings** **Accounts** **Access work or school** **Export your management log files** > **Export**. By default, the file is saved in the following location: **Users\Public\Documents\MDMDiagnostics**. Open MDMDiagReport.cab, select the DeviceHash CSV file, and extract the file to your desired location or USB drive.

3. Open the CSV file with a plain text editor such as Notepad. Ensure your CSV file meets the following requirements so it can be successfully imported into Intune:

   - Device information in the CSV file should include Serial number, Windows product ID, and Hardware hash. You should also include an optional group tag, as specified per guidance in the detailed documentation on [Windows Autopilot and Auto-login of Teams Rooms](https://aka.ms/MTRAutopilotDoc).

   > [!TIP]
   > Do not add an Assigned user column in CSV file as it is unnecessary for deploying a Teams Rooms on Windows device like Surface Hub and adding it with a blank entry will cause failure during import to Intune.

### Manually register & enroll Surface Hub 2S devices being migrated to Teams Rooms on Windows platform

When planning the migration process for a Surface Hub 2S to transition from Windows 10 Team edition to the Microsoft Teams Rooms on Windows platform, it's advantageous to also set the stage for the device to autonomously complete its deployment post-migration, utilizing Windows Autopilot with Teams Rooms Auto-Login. This approach is beneficial for customers triggering migration remotely, as it facilitates a fully remote, end-to-end process spanning migration to the Teams Rooms on Windows experience to the subsequent deployment within your organization.

> [!TIP]
> For an optimal experience, it's recommended to configure Autopilot before starting the migration process. This preparation ensures Autopilot is primed and ready to facilitate deployment when migration is complete.

1. While the Surface Hub 2S device is still running Windows 10 Team edition (that is, before you migrate to the Teams Rooms on Windows experience), extract the system’s hardware hash and manually enroll the device in Autopilot. To extract the hardware hash:

   - **Manually on Surface Hub 2S:** Select **Start** > **All apps** > **Settings** > **View as Admin** > enter admin credentials > **Update & Security** > **Logs** > **Collect logs**.

   - **Remotely via Teams Rooms Admin Center:** Select Teams devices > Surface Hubs (legacy) > select the device > Download device logs.
  
   - From the zip file, extract the autopilot.cab file from the **Environment** subdirectory. Open autopilot.cab, select the DeviceHash CSV file, and extract the file to your desired location or USB drive.

2. Open the CSV file with a plain text editor such as Notepad. Ensure your CSV file meets the following requirements so it can be successfully imported into Intune:

   - Device information in the CSV file should include Serial number, Windows product ID, and Hardware hash. You should also include an optional group tag, as specified per guidance in the detailed documentation on [Windows Autopilot and Auto-login of Teams Rooms](https://aka.ms/MTRAutopilotDoc).

   > [!TIP]
   > Do not add an Assigned user column in CSV file as it is unnecessary for deploying a Teams Rooms on Windows device like Surface Hub and adding it with a blank entry will cause failure during import to Intune.

## Configure Auto-login of Teams Rooms for Autopilot-enrolled Surface Hub devices

As outlined in the documentation on [Auto-login of Teams Rooms capability](https://aka.ms/MTRAutopilotDoc), once a Surface Hub device is enrolled in Windows Autopilot, it syncs to the **Planning** > **Autopilot Devices** tab in the [Teams Rooms Pro Management Portal](/microsoftteams/rooms/managed-meeting-rooms-portal). At that point, you can assign the Resource Account credentials that you intend to be used to automatically log into the Teams Rooms experience on the Hub when it completes the automated end-to-end deployment process.

After that final phase of configuration is complete, you're ready to power on the Surface Hub device for the first time
or initiate the migration process for a Surface Hub 2S being software-migrated to the Teams Rooms on Windows platform.

If everything is set up and configured correctly, and the device is Internet-connected, it should begin seamlessly deploying itself starting from the beginning of Windows OOBE. It ends its automated deployment with the Welcome screen of the Teams Rooms application loaded and ready to join meetings.

## Learn more

- [Windows Autopilot and Auto-login of Teams Rooms](https://aka.ms/MTRAutopilotDoc)
- [Surface partners enabled for Autopilot](/surface/windows-autopilot-and-surface-devices#surface-partners-enabled-for-windows-autopilot)
- [Migrate Surface Hub 2S to Microsoft Teams Rooms on Windows](surface-hub-2s-migrate-to-mtr-w.md)
- [Surface Hub support coming for Windows Autopilot](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-support-coming-for-windows-autopilot/ba-p/3977848)
- [Microsoft Teams Rooms and Devices: Microsoft Ignite 2023](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-rooms-and-devices-microsoft-ignite-2023/ba-p/3975581)
