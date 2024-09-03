---
title: Deploy, manage, and service ARM processor-based Surface devices
description: This article provides an overview of key considerations for deploying, managing, and servicing Surface Pro (11th Edition), Surface Laptop (7th edition), Surface Pro 9 with 5G, and Surface Pro X.
ms.service: windows-11
ms.localizationpriority: high
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 6/21/2024
ms.reviewer: Karand 
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---
# Deploy, manage, and service ARM-based Surface devices

ARM-based Surface devices including Surface Pro (11th Edition), Surface Laptop (7th edition), Surface Pro 9 with 5G, and Surface Pro X are built to handle high-performance commercial requirements.

### Image-based deployment now supported

Image-based Operating System Deployment (OSD) is now [supported via Endpoint Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2403#support-for-arm-64-operating-system-deployment) for Windows 11 on Surface Pro (11th Edition), Surface Laptop (7th Edition), Surface Pro 9 with 5G, and Surface Pro X. 

### Autopilot deployment 

You can deploy ARM-based Surface devices using Windows Autopilot either with the assistance of a Microsoft Cloud Solution Provider or self-provisioned using Autopilot deployment profiles and related features. For more information, see the following resources:

- [Windows Autopilot and Surface devices](/surface/windows-autopilot-and-surface-devices)
- [Overview of Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot)

Autopilot deployment has several advantages: It allows you to use the factory-provisioned operating system, streamlined for zero-touch deployment, to include preinstallation of [Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/enterprise/microsoft-365-apps-for-enterprise). Organizations already using modern management, security, and productivity solutions are well-positioned to take advantage of the unique performance features in ARM-based Surface devices. Customers using modernized [line of business apps](/microsoft-store/working-with-line-of-business-apps), [Microsoft Store (UWP) apps](/windows/uwp/get-started/universal-application-platform-guide), or remote desktop solutions also stand to benefit.

### Manage firmware with UEFI Configurator and SEMM

With the [Surface IT Toolkit](surface-it-toolkit.md) and [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md), you can [manage hardware components](surface-it-toolkit-uefi-config.md) at the firmware level for commercial SKUs of Surface Pro (11th Edition), Surface Laptop (7th edition), Surface Pro 9 with 5G, and Surface Pro X devices (including Surface Pro X SQ1, Surface Pro X SQ1 LTE, Surface Pro X SQ2, and Surface Pro X SQ2 LTE). The default behavior of each component is indicated as either "On" or "Off." For descriptions of settings functionality, see [SEMM UEFI settings reference](surface-it-toolkit-semm-uefi-settings.md).

> [!NOTE]
> Commercial SKUs of Surface Pro (11th edition) and Surface Laptop (7th edition) begin shipping September 10, 2024 from your [Microsoft Surface Authorized Reseller](https://www.microsoft.com/surface/business/where-to-buy-microsoft-surface).


| Component              | Surface Pro (11th Edition)     | Surface Laptop (7th edition) | Surface Pro 9 with 5G     | Surface Pro X     |
|------------------------|--------------------------------|-----------------------------|---------------------------|-------------------|
| **Accessories**        |                                |                             |                           |                   |
| Docking USB Port       | On                             | On                          | On                        |                   |
| On-board Audio         | On                             | On                          | On                        |                   |
| On-board Microphone    | On                             | On                          | On                        |                   |
| MAC Address Emulation  | Off                            | Off                         | Off                       |                   |
| Type Cover             | On                             | On                          | On                        |                   |
| **Cameras**            |                                |                             |                           |                   |
| Front Camera           | On                             | On                          | On                        |                   |
| Rear Camera            | On                             | On                          | On                        |                   |
| IR Camera              |                                |                             | On                        |                   |
| **Radio**              |                                |                             |                           |                   |
| Bluetooth              | On                             | On                          | On                        |                   |
| Wi-Fi                  | On                             | On                          | On                        |                   |
| Wi-Fi and Bluetooth    | On                             | On                          | On                        |                   |
| LTE                    | On                             |                             | On                        |                   |
| NFC                    | On                             |                             |                           |                   |
| **Boot**               |                                |                             |                           |                   |
| Wake on LAN            | Off                            | Off                         | Off                       | Off               |
| Wake on Power          | Off                            | Off                         | Off                       | Off               |
| IPv6 for PXE Boot      | Off                            | Off                         | Off                       | Off               |
| Alternate Boot         | On                             | On                          | On                        | On                |
| Boot Order Lock        | Off                            | Off                         | Off                       | Off               |
| USB Boot               | On                             | On                          | On                        | On                |
| Network Stack          | Off                            | Off                         | Off                       | Off               |
| Auto Power On<sup>1</sup>         |                                |                             |                           | Off               |
| **USB-C Mode**         |                                |                             |                           |                   |
| USB-C Port 1           | Mode 0, Mode 1, Mode 2         | Mode 0, Mode 1, Mode 2      | Mode 0, Mode 1, Mode 2    |                   |
| **UEFI Front Page**    |                                |                             |                           |                   |
| Security               | On                             | On                          | On                        | On                |
| Devices                | On                             | On                          | On                        |                   |
| Boot                   | On                             | On                          | On                        | On                |
| DateTime               | On                             | On                          | On                        |                   |
| **Kiosk Overrides**    |                                |                             |                           |                   |
| Battery Limit          | Off                            | Off                         | Off                       | Off               |

**1.** *Auto Power On is available only for Surface Pro X SQ1 LTE and Surface Pro X SQ2 LTE.*

To learn more about managing firmware with SEMM, see:

- [Get started with Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Manage Surface UEFI settings](manage-surface-uefi-settings.md)

## Microsoft Intune admin center

### Manage firmware with Intune and DFCI

With Microsoft Intune and [Device Firmware Configuration Interface (DFCI) profiles](surface-manage-dfci-guide.md), you can manage hardware components at the firmware level just like any other Surface device. To learn more, see [Manage DFCI on Surface devices](surface-manage-dfci-guide.md).

<a name='manage-with-azure-ad'></a>

### Manage with Microsoft Entra ID

Microsoft Intune admin center and Intune integrate with Microsoft Entra ID for identity and access control and provide granular management of enrolled devices. Highlights include faster device sign in times and a more streamlined catalog of policy settings enabling full device management from the cloud. For example, you can [manage LTE using eSIM profiles](/windows/client-management/mdm/esim-enterprise-management) to configure data plans and deploy activation codes to multiple devices.

### Co-management

Once deployed in Autopilot, you can join devices to Microsoft Entra ID or Active Directory ([Microsoft Entra hybrid join](/azure/active-directory/devices/concept-azure-ad-join-hybrid)), where you can [manage the devices with Intune](/mem/intune/remote-actions/device-management) or [co-manage them with Endpoint Configuration Manager](/mem/configmgr/comanage/overview), which installs the 32-bit x86 ConfigMgr client.

### Other MDM solutions

You may be able to use non-Microsoft MDM tools to manage ARM-based Surface devices. For details, contact your MDM provider.

### Antivirus software

Microsoft Defender helps protect Windows 10 and 11 on ARM-based PCs for the supported lifetime of the device. Some third-party antivirus software can't be installed on devices running on an ARM-based processor. Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs.

## Service and maintain

ARM-based devices have specific requirements for maintaining the latest drivers and firmware. They're designed to use Windows Update to simplify keeping drivers and firmware up to date for home and small business users. Use the default settings to receive Automatic updates. To verify:

1. Go to **Start** > **Settings > Update & Security > Windows Update** > **Advanced Options.**
2. Under **Choose how updates are installed,** select **Automatic (recommended)**.

### Recommendations for commercial customers

- Use Windows Update or Windows Update for Business to maintain the latest drivers and firmware. For more information, see [Deploy Updates using Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb).
- For more information about deploying and managing updates on Surface devices, see [Manage and deploy Surface driver and firmware updates](/surface/manage-surface-driver-and-firmware-updates).
- Windows Server Update Services (WSUS) doesn't support the delivery of drivers and firmware to Surface Pro 9 with 5G and Surface Pro X.

## App compatibility

Most apps run smoothly on ARM-based Windows 11 PCs, with only a few exceptions.

### Supported apps

- **x86 Win32 apps**: Most run seamlessly on ARM-based Surface devices, benefiting from advanced emulation technology.
- **Native Arm64 and Microsoft Store UWP apps**: These apps deliver an outstanding user experience, taking full advantage of the ARM-based processor's native speed while optimizing battery life. The availability of Native Arm64 apps continues to grow, including popular applications like Adobe Photoshop and Adobe Lightroom.
- **Driver-supported apps**: Apps that rely on drivers specifically designed for ARM-based Windows 10 or Windows 11 PCs are fully supported.
- **x64 emulation**: Now generally available in Windows 11, x64 emulation allows for broader app compatibility, enabling many x64 apps to run effectively on ARM-based devices.

### FastTrack App Assure

The App Assure program is available to commercial customers for their LOB, ISV, and Microsoft first-party apps targeting Windows 10 or Windows 11 on ARM. If commercial customers encounter an app compatibility issue using Windows 10 or Windows 11 on ARM, Microsoft provides developer resources to troubleshoot and assist with app remediations at no extra cost. To learn more, visit [aka.ms/AppAssure](/fasttrack/products-and-capabilities#app-assure).

For more information about running apps on, see:

- [Windows on ARM documentation](/windows/arm)

## Virtual Desktops (VDI)

Azure Virtual Desktop enables access to Windows desktops, applications, and data on any computing device or platform, from any location. To learn more, refer to the [Azure Virtual Desktop site](https://aka.ms/wvd).

### Browsing

Popular browsers run on Surface Pro 9 with 5G and Surface Pro X:

- Inbox Microsoft Edge, Firefox, Chrome, and Internet Explorer run on Surface Pro 9 with 5G and Surface Pro X.
- Firefox and Microsoft Edge based on Chromium run natively with enhanced performance on ARM-based Windows 10 or Windows 11 PCs.

### Installing and using Microsoft Office

- Use Microsoft 365 for the best experience on a Windows 10 or Windows 11 PC on an ARM-based processor.
- Microsoft 365 "click-to-run" installs Outlook, Word, Excel, and PowerPoint optimized to run on a Windows 10 or Windows 11 PC on an ARM-based processor.
- Microsoft Teams runs natively on Surface Pro 9 with 5G and Surface Pro X.
- For "[perpetual versions](/microsoft-365/troubleshoot/installation/office-perpetual-volume-license-products)" of Office, such as Office 2021, install the 32-bit version.

### VPN

To confirm if a specific third-party VPN supports a Windows 10 or Windows 11 PC on an ARM-based processor, contact the VPN provider.

## Feature summary

The following tables show the availability of selected key features on Surface Pro 9 with 5G and Surface Pro X with Windows 10 or Windows 11 on ARM.

### Deployment


| Feature                                                           | Surface Pro X     | Surface Pro 9 with 5G      | Surface Pro (11th Edition) | Surface Laptop (7th edition) | Notes                                                                                                                                                                            |
| ----------------------------------------------------------------- | ----------------- | -------------------------- | -------------------------- | ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                                                 | Yes               | Yes                        | Yes                        | Yes                          | Recommended deployment option                                                                                                                                                     |
| Support for Network Boot (PXE)                                    | No                | No                         | No                         | No                           |                                                                                                                                                                                  |
| Windows Configuration Designer                                    | No                | No                         | No                         | No                           |                                                                                                              |
| WinPE                                                             | No                | No                         | No                         | No                           | Not recommended. Microsoft doesn't provide the necessary .ISO and drivers to support WinPE with ARM-based Surface devices. |
| Operating System Deployment (OSD)                                 | No                | Yes                        | Yes                        | Yes                          | Supported with Windows 11 on Surface Pro 9 with 5G, Surface Pro (11th Edition), and Surface Laptop (7th edition).                                                                                                                               |
| MDT                                                               | No                | No                         | No                         | No                           | Not supported on Windows 11" including x86 Windows 11.                                                                                                                         |

### Management

| Feature                                       | Surface Pro X     | Surface Pro 9 with 5G         | Surface Pro (11th Edition) | Surface Laptop (7th edition) | Notes                                                                                                      |
| --------------------------------------------- | ----------------- | ----------------------------- | -------------------------- | ---------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Intune                                        | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Windows Autopilot                             | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Microsoft Entra ID (co-management)                      | Yes               | Yes                           | Yes                        | Yes                          | Ability to join ARM-based Surface devices to Microsoft Entra ID or Active Directory (Microsoft Entra hybrid join). |
| Endpoint Configuration Manager                | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Power on When AC Restore                      | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Surface Diagnostic Toolkit (SDT) for Business | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Surface Asset Tag tool                        | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Surface Enterprise Management Mode (SEMM)     | Partial           | Yes                           | Yes                        | Yes                          |                                                              |
| Surface UEFI Configurator                     | No                | Yes                           | Yes                        | Yes                          |                                                           |
| Surface UEFI Manager                          | Partial           | Yes                           | Yes                        | Yes                          |                                                            |

### Security

| Feature                       | Surface Pro X | Surface Pro 9 with 5G | Surface Pro (11th Edition) | Surface Laptop (7th edition) | Notes                                                                                                                                                                    |
| ----------------------------- | ------------- | --------------------- | -------------------------- | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BitLocker                     | Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |
| Microsoft Defender            | Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |
| Support for third-party antivirus | See note      | See note               | See note                   | See note                     | Some third-party antivirus software can't be installed on an ARM-based processor. Contact your antivirus software provider about app availability. |
| Secure Boot                   | Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |
| Windows Information Protection| Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |
| Surface Data Eraser (SDE)     | Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |
## FAQ

**Can I deploy ARM-based Surface devices with Endpoint Configuration Manager?**

- Microsoft Endpoint Configuration Manager now [supports Operating System Deployment](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2403#support-for-arm-64-operating-system-deployment) for Windows 11 on Surface Pro 9 with 5G with 5G.

**How can I deploy ARM-based Surface devices?**

- Deploy Surface Pro 9 with 5G, Surface Pro (11th Edition), or Surface Laptop (7th edition) via OSD or Windows Autopilot. 
- Deploy Surface Pro X via Windows Autopilot.

**Is a BMR available?**

- Yes a BMR is available for Surface Pro X and Surface Pro 9  with 5G. Refer to [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).
- BMRs for Surface Pro (11th Edition) and Surface Laptop (7th edition) will be available upon commercial availability in September. 

**Is Intune required to manage ARM-based Surface devices?**

- Intune is recommended but not required. Once deployed in Autopilot, you can join ARM-based Surface devices to Microsoft Entra ID or Active Directory (Microsoft Entra hybrid join), where you'll be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which installs the 32-bit x86 ConfigMgr client.
