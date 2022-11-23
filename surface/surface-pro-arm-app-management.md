---
title: Deploy, manage, and service ARM-based Surface devices
description: This article provides an overview of key considerations for deploying, managing, and servicing Surface Pro 9 with 5G and Surface Pro X.
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: hachidan
ms.topic: article
ms.date: 11/23/2022
ms.reviewer: Karand 
manager: laurawi
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
---
# Deploy, manage, and service ARM-based Surface devices

Built to handle high-performance commercial requirements, Surface Pro 9 with 5G incorporates the most powerful processors in its class, the Microsoft SQ3 ARM chipset.

## Deploy

For the best experience, deploy Surface Pro 9 with 5G or Surface Pro X using Windows Autopilot either with the assistance of a Microsoft Cloud Solution Provider or self-provisioned using Autopilot deployment profiles and related features. For more information, refer to the following:

- [Windows Autopilot and Surface devices](/surface/windows-autopilot-and-surface-devices)
- [Overview of Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot)

Autopilot deployment has several advantages: It allows you to use the factory-provisioned operating system, streamlined for zero-touch deployment, to include pre-installation of [Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/enterprise/microsoft-365-apps-for-enterprise).
Organizations already using modern management, security, and productivity solutions are well-positioned to take advantage of the unique performance features in Surface Pro 9 with 5G and Surface Pro X. Customers using modernized [line of business apps](/microsoft-store/working-with-line-of-business-apps), [Microsoft Store (UWP) apps](/windows/uwp/get-started/universal-application-platform-guide), or remote desktop solutions also stand to benefit.

### Image-based deployment considerations

Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager do not support image-based Operating System Deployment (OSD) for Surface Pro 9 with 5G or Surface Pro X. Customers relying on image-based deployment should consider Surface Pro 9 while evaluating the right time to transition to modern deployment solutions.

## Manage

### Manage firmware with UEFI Configurator and SEMM

With Surface Enterprise Management Mode (SEMM), you can manage the following hardware components at the firmware level for Surface Pro 9 with 5G devices:

- **Accessories.** Docking USB Port, Type Cover, Onboard Audio, Onboard Microphone, MAC Address Emulation.
- **Cameras.** Front Camera, Rear Camera, IR Camera.
- **Wireless (aka Radio).** Bluetooth, Wi-Fi, LTE.

#### Advanced settings

- **Kiosk Overrides.** Battery limit.
- **Boot.** Wake on LAN, Wake on Power, IPv6 for PXE boot, Alternate Boot, Boot Order Lock, USB Boot, Network Stack.
- **UEFI Front Page.** Security, Devices, Boot, DateTime

## Microsoft Endpoint Manager

### Manage firmware with Intune and DFCI

With Microsoft Intune and Device Firmware Configuration Interface (DFCI) profiles, you can manage the following hardware components at the firmware level for Surface Pro 9 with 5G devices:

- Front Camera
- Rear Camera
- IR Camera
- WWAN (aka mobile wireless)

### Manage with Azure AD

Microsoft Endpoint Manager and Intune integrate with Azure Active Directory for identity and access control and provide granular management of enrolled devices. Highlights include faster device login times and a more streamlined catalog of policy settings enabling full device management from the cloud. For example, you can [manage LTE using eSIM profiles](/windows/client-management/mdm/esim-enterprise-management) to configure data plans and deploy activation codes to multiple devices.

### Co-management

Once deployed in Autopilot, you can join devices to Azure AD or Active Directory ([Hybrid Azure AD Join](/azure/active-directory/devices/concept-azure-ad-join-hybrid)), where you can [manage the devices with Intune](/mem/intune/remote-actions/device-management) or [co-manage Them with Endpoint Configuration Manager](/mem/configmgr/comanage/overview), which will install the 32-bit x86 ConfigMgr client.

### Third-party MDM solutions

You may be able to use third-party MDM tools to manage Surface Pro 9 with 5G and Surface Pro X. For details, contact your MDM provider.

### Antivirus software

Microsoft Defender will help protect Windows 10 and 11 on ARM-based PCs for the supported lifetime of the device. Some third-party antivirus software cannot be installed on devices running on an ARM-based processor. Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs. Contact your antivirus software provider to understand when their apps will be available.

## Service and maintain

ARM-based devices have specific requirements for maintaining the latest drivers and firmware.
Surface Pro 9 with 5G and Surface Pro X were designed to use Windows Update to simplify keeping drivers and firmware up to date for home and small business users. Use the default settings to receive Automatic updates. To verify:

1. Go to **Start** > **Settings > Update & Security > Windows Update** > **Advanced Options.**
2. Under **Choose how updates are installed,** select **Automatic (recommended)**.

### Recommendations for commercial customers

- Use Windows Update or Windows Update for Business to maintain the latest drivers and firmware. For more information, see [Deploy Updates using Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb).
- For more information about deploying and managing updates on Surface devices, see [Manage and deploy Surface driver and firmware updates](/surface/manage-surface-driver-and-firmware-updates).
- Note that Windows Server Update Services (WSUS) does not support the delivery of drivers and firmware to Surface Pro 9 with 5G and Surface Pro X.

## App compatibility

Most apps run on ARM-based Windows 10 PCs with limited exclusions.

### Supported apps

- Most x86 Win32 apps run on Surface Pro 9 with 5G and Surface Pro X.
- Native ARM64 and Microsoft Store UWP apps provide an excellent user experience utilizing the full native speed of the ARM-based processor while optimizing battery life. More Native ARM64 apps are now available including Adobe Photoshop and Adobe Lightroom.
- Apps that use drivers designed for a Windows 10 or Windows 11 PC running on an ARM-based processor.
- x64 emulation for Windows is now generally available in Windows 11.

### FastTrack App Assure

The App Assure program is available to commercial customers for their LOB, ISV and Microsoft first-party apps targeting Windows 10 on ARM. If commercial customers encounter an app compatibility issue using Windows 10 on ARM, Microsoft will provide developer resources to troubleshoot and assist with app remediations at no additional cost. To learn more, visit [aka.ms/AppAssure](/fasttrack/products-and-capabilities#app-assure).

For more information about running apps on Surface Pro 9 with 5G or Surface Pro X, refer to:

- [Windows on ARM documentation](/windows/arm)

## Virtual Desktops (VDI)

Azure Virtual Desktop enables access to Windows desktops, applications, and data on any computing device or platform, from any location. To learn more, refer to the [Azure Virtual Desktop site](https://aka.ms/wvd).

### Browsing

Popular browsers run on Surface Pro 9 with 5G and Surface Pro X:

- Inbox Edge, Firefox, Chrome, and Internet Explorer run on Surface Pro 9 with 5G and Surface Pro X.
- Firefox and Microsoft Edge based on Chromium run natively with enhanced performance on ARM-based Windows 10 or Windows 11 PCs.

### Installing and using Microsoft Office

- Use Office 365 for the best experience on a Windows 10 or Windows 11 PC on an ARM-based processor.
- Office 365 "click-to-run" installs Outlook, Word, Excel, and PowerPoint optimized to run on a Windows 10 or Windows 11 PC on an ARM-based processor.
- Microsoft Teams runs natively on Surface Pro 9 with 5G and Surface Pro X.
- For "[perpetual versions](/microsoft-365/troubleshoot/installation/office-perpetual-volume-license-products)" of Office, such as Office 2021, install the 32-bit version.

### VPN

To confirm if a specific third-party VPN supports a Windows 10 or Windows 11 PC on an ARM-based processor, contact the VPN provider.

## Feature summary

The following tables show the availability of selected key features on Surface Pro 9 with 5G and Surface Pro X with Windows 10 or Windows 11 on ARM.

### Deployment

| Feature                                                           | Surface Pro X     | Surface Pro 9 with 5G      | Notes                                                                                                                                                                            |
| ----------------------------------------------------------------- | ----------------- | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Windows Autopilot                                                 | Yes               | Yes                        | Recommended deployment option                                                                                                                                                        |
| Support for Network Boot (PXE)                                    | No                | No                         |                                                                                                                                                                                      |
| Windows Configuration Designer                                    | No                | No                         | Not recommended for Surface Pro 9 with 5G or Surface Pro X.                                                                                                                          |
| WinPE                                                             | No                | No                         | Not recommended for Surface Pro 9 with 5G or Surface Pro X. Microsoft does not provide the necessary .ISO and drivers to support WinPE with Surface Pro 9 with 5G and Surface Pro X. |
| Operating System Deployment (OSD)                                 | No                | No                         | Not supported on Surface Pro 9 with 5G or Surface Pro X.                                                                                                                             |
| MDT                                                               | No                | No                         | Not supported on Surface Pro 9 with 5G or Surface Pro X.                                                                                                                             |

### Management

| Feature                                       | Surface Pro X     | Surface Pro 9 with 5G         | Notes                                                                                                      |
| --------------------------------------------- | ----------------- | ----------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Intune                                        | Yes               | Yes                           |                                                                                                                |
| Windows Autopilot                             | Yes               | Yes                           |                                                                                                                |
| Azure AD (co-management)                      | Yes               | Yes                           | Ability to join Surface Pro 9 with 5G or Surface Pro X to Azure AD or Active Directory (Hybrid Azure AD Join). |
| Endpoint Configuration Manager                | Yes               | Yes                           |                                                                                                                |
| Power on When AC Restore                      | Yes               | Yes                           |                                                                                                                |
| Surface Diagnostic Toolkit (SDT) for Business | Yes               | Yes                           |                                                                                                                |
| Surface Asset Tag tool                        | Yes               | Yes                           |                                                                                                                |
| Surface Enterprise Management Mode (SEMM)     | Partial           | Yes                           | Surface Pro 9 with 5G adds UEFI management options                                                             |
| Surface UEFI Configurator                     | No                | Yes                           | Surface Pro 9 with 5G adds UEFI management options                                                             |
| Surface UEFI Manager                          | Partial           | Yes                           | Surface Pro 9 with 5G adds UEFI management options                                                             |

### Security

| Feature                       | Surface Pro X | Surface Pro 9 with 5G | Notes                                                                                                                                                                    |
| --------------------------------- | ----------------- | -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| BitLocker                         | Yes               | Yes                              |                                                                                                                                                                              |
| Microsoft Defender                | Yes               | Yes                              |                                                                                                                                                                              |
| Support for third-party antivirus | See note          | See note                         | Some third-party antivirus software cannot be installed on an ARM-based processor. Contact your antivirus software provider to understand when their apps will be available. |
| Secure Boot                       | Yes               | Yes                              |                                                                                                                                                                              |
| Windows Information Protection    | Yes               | Yes                              |                                                                                                                                                                              |
| Surface Data Eraser (SDE)         | Yes               | Yes                              |                                                                                                                                                                              |

## FAQ

**Can I deploy Surface Pro 9 with 5G and Surface Pro X with MDT or Endpoint Configuration Manager?**

- The Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager currently do not support Surface Pro 9 with 5G and Surface Pro X or Surface Pro 9 with 5G for operating system deployment. Customers relying on image-based deployment should consider Surface Pro 8 while evaluating the right time to transition to the cloud.

**How can I deploy Surface Pro 9 with 5G or Surface Pro X?**

- Deploy Surface Pro 9 with 5G and Surface Pro X or Surface Pro 9 with 5G using Windows Autopilot.

**Is a BMR available?**

- A BMR is available for Surface Pro X. Refer to [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage). A BMR will be available for Surface Pro 9 5G.

**Is Intune required to manage Surface Pro 9 with 5G or Surface Pro X**

- Intune is recommended but not required. Once deployed in Autopilot, you can join Surface Pro 9 with 5G and Surface Pro X devices to Azure AD or Active Directory (Hybrid Azure AD Join), where you will be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which will install the 32-bit x86 ConfigMgr client.

To learn more, see [ARM-based Surface devices FAQ](surface-arm-faq.md)