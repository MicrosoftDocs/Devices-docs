---
title: Deploy, manage, and service Arm processor-based Surface devices
description: Learn how to deploy, manage, and service Arm-based Surface devices, including Surface Pro 11th Edition and Surface Laptop 7th Edition.
ms.service: windows-11
ms.localizationpriority: high
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 9/05/2024
ms.reviewer: karand 
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---
# Deploy, manage, and service Arm-based Surface devices

Arm-based Surface devices, including Surface Pro (11th Edition), Surface Laptop (7th Edition), Surface Pro 9 with 5G, and Surface Pro X, are engineered to meet high-performance commercial requirements.

### Image-based deployment now supported

Image-based Operating System Deployment (OSD) is now [supported via Endpoint Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2403#support-for-arm-64-operating-system-deployment) for Windows 11 on Surface Pro (11th Edition), Surface Laptop (7th Edition), and Surface Pro 9 with 5G. 

### Autopilot deployment 

Deploy Arm-based Surface devices using Windows Autopilot with the help of a Microsoft Cloud Solution Provider. Or you can self-provision devices with Autopilot deployment profiles. Autopilot allows for zero-touch deployment using the factory-provisioned OS, enabling streamlined setup, including preinstallation of [Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/enterprise/microsoft-365-apps-for-enterprise). Organizations using modern management and security solutions can fully use the performance features of Arm-based Surface devices. Customers using modernized [line of business apps](/microsoft-store/working-with-line-of-business-apps), [Microsoft Store apps](/windows/uwp/get-started/universal-application-platform-guide), or remote desktop solutions also stand to benefit.

### Manage firmware with UEFI Configurator and SEMM

With the [Surface IT Toolkit](surface-it-toolkit.md) and [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md), you can [manage hardware components](surface-it-toolkit-uefi-config.md) at the firmware level for commercial SKUs of the supported Surface devices. The default behavior of each component is indicated as either "On" or "Off." For detailed settings functionality, refer to the [SEMM UEFI settings reference](surface-it-toolkit-semm-uefi-settings.md).

> [!NOTE]
> Commercial SKUs of Surface Pro (11th Edition) and Surface Laptop (7th Edition) begin shipping on September 10, 2024, from your [Microsoft Surface Authorized Reseller](https://www.microsoft.com/surface/business/where-to-buy-microsoft-surface).

To learn more about managing firmware with SEMM, see:

- [Get started with Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Manage Surface UEFI settings](manage-surface-uefi-settings.md)

## Microsoft Intune admin center

### Manage firmware with Intune and DFCI

With Microsoft Intune and [Device Firmware Configuration Interface (DFCI) profiles](surface-manage-dfci-guide.md), you can manage hardware components at the firmware level for Arm-based Surface devices, similar to other Surface devices. To learn more, see [Manage DFCI on Surface devices](surface-manage-dfci-guide.md).

### Manage with Microsoft Entra ID

The Microsoft Intune admin center integrates with Microsoft Entra ID to provide granular management of enrolled devices, enabling faster device sign-ins and streamlined policy settings for full cloud-based management. For example, you can [manage LTE using eSIM profiles](/windows/client-management/mdm/esim-enterprise-management) to configure data plans and deploy activation codes across multiple devices.

### Co-management

After deployment via Autopilot, devices can be joined to Microsoft Entra ID or Active Directory ([Microsoft Entra hybrid join](/azure/active-directory/devices/concept-azure-ad-join-hybrid)), where you can [manage the devices with Intune](/mem/intune/remote-actions/device-management) or [co-manage them with Endpoint Configuration Manager](/mem/configmgr/comanage/overview), which installs the 32-bit x86 ConfigMgr client.

### Other MDM solutions

Contact your MDM provider for details about how you can manage Arm-based Surface devices.

### Antivirus software

Microsoft Defender protects Windows 10 and 11 on Arm-based PCs throughout the device's supported lifetime. While more non-Microsoft antivirus programs now support Arm-based PCs, confirm compatibility with your specific solution. Windows Security continues to offer comprehensive protection.

## Service and maintain

Arm-based devices are designed to simplify the update process for drivers and firmware via Windows Update. Ensure the default settings are enabled to receive automatic updates:

1. Go to **Start** > **Settings > Update & Security > Windows Update** > **Advanced Options.**
2. Under **Choose how updates are installed,** select **Automatic (recommended)**.

### Recommendations for commercial customers

- Use Windows Update or Windows Update for Business to maintain the latest drivers and firmware. For more information, see [What is Windows Update for Business?](/windows/deployment/update/waas-manage-updates-wufb).
- For more information about deploying and managing updates on Surface devices, see [Manage and deploy Surface driver and firmware updates](/surface/manage-surface-driver-and-firmware-updates).
- Windows Server Update Services (WSUS) doesn't support the delivery of drivers and firmware to Surface Pro 9 with 5G and Surface Pro X.

## App compatibility

Most apps run smoothly on Arm-based Windows 11 PCs, with a few exceptions.

### Supported apps

- **x86 Win32 apps**: Most run seamlessly on Arm-based Surface devices, benefiting from advanced emulation technology.
- **Native Arm64 and Microsoft Store UWP apps**: These apps deliver an outstanding experience, using the full native speed of the Arm-based processor while optimizing battery life. Native Arm64 app availability continues to grow, including popular applications like Adobe Photoshop and Adobe Lightroom.
- **Driver-supported apps**: Apps that rely on drivers designed for Arm-based Windows 10 or Windows 11 PCs are fully supported.
- **x64 emulation**: Now generally available in Windows 11, x64 emulation allows broader app compatibility, enabling many x64 apps to run effectively on Arm-based devices.
- To learn more, see [Arm-based Surface devices FAQ](surface-arm-faq.md)

### App Assure program

The App Assure program is available to commercial customers for their LOB, ISV, and Microsoft first-party apps targeting Windows 10 or Windows 11 on Arm. If you encounter an app compatibility issue, Microsoft provides developer resources to troubleshoot and assist with app remediations at no extra cost. To learn more, visit [aka.ms/AppAssure](/fasttrack/products-and-capabilities#app-assure).

For more information about running apps on Arm-based devices, see:

- [Windows on Arm documentation](/windows/arm)

## Virtual Desktops (VDI)

Azure Virtual Desktop enables access to Windows desktops, applications, and data on any device, from any location. To learn more, visit the [Azure Virtual Desktop site](https://aka.ms/wvd).

### Browsing

Popular browsers are supported on Arm-based Surface devices:

- Microsoft Edge, Firefox, Chrome, and Internet Explorer run on Surface Pro 9 with 5G and Surface Pro X.
- Firefox and Microsoft Edge (Chromium) run natively with enhanced performance on Arm-based Windows 10 or Windows 11 PCs.

### Installing and using Microsoft Office

- Use Microsoft 365 for the best experience on Arm-based Windows 10 or Windows 11 PCs.
- Microsoft 365 "select-to-run" installs Outlook, Word, Excel, and PowerPoint optimized for Arm-based processors.
- Microsoft Teams runs natively on Surface Pro 9 with 5G and Surface Pro X.
- For "[perpetual versions](/microsoft-365/troubleshoot/installation/office-perpetual-volume-license-products)" of Office, such as Office 2021, install the 32-bit version.

### VPN

To confirm if a specific VPN supports Arm-based Windows 10 or Windows 11 PCs, contact the VPN provider.

## Feature summary for Arm-based Surface devices

The following tables show the availability of key features on Arm-based Surface devices and Windows 11 on Arm.

### Deployment features 


| Feature                                                           | Surface Pro X     | Surface Pro 9 with 5G      | Surface Pro (11th Edition) | Surface Laptop (7th Edition) | Notes                                                                                                                                                                            |
| ----------------------------------------------------------------- | ----------------- | -------------------------- | -------------------------- | ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                                                 | Yes               | Yes                        | Yes                        | Yes                          | Recommended deployment option                                                                                                                                                     |
| Network Boot (PXE)                                    | No                | Yes                        | Yes                        | Yes                           |                                                                                                                                                                                  |
| Windows Configuration Designer                                    | Yes               | Yes                        | Yes                        | Yes                           |                                                                                                              |
| WinPE                                                             | Yes               | Yes                       | Yes                        | Yes                           | Not recommended. Microsoft doesn't provide the necessary .ISO and drivers to support WinPE with Arm-based Surface devices. |
| Operating System Deployment                                        | No                | Yes                        | Yes                        | Yes                          | Supported with Windows 11 on Surface Pro 9 with 5G, Surface Pro (11th Edition), and Surface Laptop (7th Edition).                                                                                                                               |
| MDT                                                               | No                | No                         | No                         | No                           | Not supported on Windows 11, including x86 Windows 11.                                                                                                                         |

### Management tools and options 

| Feature                                       | Surface Pro X     | Surface Pro 9 with 5G         | Surface Pro (11th Edition) | Surface Laptop (7th Edition) | Notes                                                                                                      |
| --------------------------------------------- | ----------------- | ----------------------------- | -------------------------- | ---------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Intune                                        | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Windows Autopilot                             | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Microsoft Entra ID (co-management)            | Yes               | Yes                           | Yes                        | Yes                          | Ability to join Arm-based Surface devices to Microsoft Entra ID or Active Directory (Microsoft Entra hybrid join). |
| Endpoint Configuration Manager                | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Power on When AC Restore                      | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Surface Diagnostic Toolkit (SDT) for Business | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Surface Asset Tag tool                        | Yes               | Yes                           | Yes                        | Yes                          |                                                                                                                |
| Surface Enterprise Management Mode (SEMM)     | Partial           | Yes                           | Yes                        | Yes                          |                                                              |
| Surface UEFI Configurator                     | No                | Yes                           | Yes                        | Yes                          |                                                           |
| Surface UEFI Manager                          | Partial           | Yes                           | Yes                        | Yes                          |                                                            |

### Security capabilities 

| Feature                       | Surface Pro X | Surface Pro 9 with 5G | Surface Pro (11th Edition) | Surface Laptop (7th Edition) | Notes                                                                                                                                                                    |
| ----------------------------- | ------------- | --------------------- | -------------------------- | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| BitLocker                     | Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |
| Microsoft Defender            | Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |
| Support for non-Microsoft antivirus software | See note      | See note               | See note                   | See note                | Some non-Microsoft antivirus software can't be installed on an Arm-based processor. Contact your antivirus software provider about app availability. |
| Secure Boot                   | Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |
| Windows Information Protection| Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |
| Surface Data Eraser     | Yes           | Yes                   | Yes                        | Yes                          |                                                                                                                                                                          |

## FAQ

**Can I deploy Arm-based Surface devices with Endpoint Configuration Manager?**

- Microsoft Endpoint Configuration Manager now [supports Operating System Deployment](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2403#support-for-arm-64-operating-system-deployment) for Windows 11 on Surface Pro 9 with 5G, Surface Pro (11th Edition), and Surface Laptop (7th Edition).

**How can I deploy Arm-based Surface devices?**

- Deploy Surface Pro (11th Edition), Surface Laptop (7th Edition), or Surface Pro 9 with 5G via OSD or Windows Autopilot. 
- Deploy Surface Pro X via Windows Autopilot.

**Is a recovery image available?**

- Yes, when devices begin shipping, go to [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage) for all available BMRs.

**Is Intune required to manage Arm-based Surface devices?**

- Intune is recommended but not required. Once deployed via Autopilot, you can join Arm-based Surface devices to Microsoft Entra ID or Active Directory (Microsoft Entra hybrid join). This enables you to manage your devices with Intune or co-manage them with Endpoint Configuration Manager, which installs the 32-bit x86 ConfigMgr client.

### Learn more

- [Arm-based Surface devices FAQ](surface-arm-faq.md)
- [Windows on Arm documentation](/windows/arm/overview)
- [App Assure](https://www.microsoft.com/fasttrack/microsoft-365/app-assure)
- [Qualcomm: Windows on Snapdragon](https://www.qualcomm.com/developer/windows-on-snapdragon/overview)