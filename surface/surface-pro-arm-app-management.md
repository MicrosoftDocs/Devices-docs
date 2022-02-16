---
title: Deploying, managing, and servicing Surface Pro X
description: This article provides an overview of key considerations for deploying, managing, and servicing Surface Pro X.
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/01/2021
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
---
# Deploying, managing, & servicing Surface Pro X

## Introduction

Built to handle high performance commercial requirements, Surface Pro X breaks new ground by incorporating the most powerful processors in its class, the Microsoft SQ1 and Microsoft SQ1 ARM chipsets.

Powered by a 3GHz CPU and a 2.1 teraflop GPU, Surface Pro X provides a full Windows experience. Its 15-hour battery life built-in Gigabit LTE and the versatility of touch, pen, tablet, and laptop make it ideally suited for mobile first-line workers and professionals across the financial, legal, and medical fields or any role demanding extended battery life and continuous connectivity capabilities.

Surface Pro X is designed almost exclusively for a modern, cloud-based environment and works best when paired with Microsoft 365, Intune and Windows Autopilot. This article highlights what that looks like and outlines key considerations for deploying, managing, and servicing Surface Pro X.

## Deploying Surface Pro X

For the best experience, deploy Surface Pro X using Windows Autopilot either with the assistance of a Microsoft Cloud Solution Provider or self-provisioned using Autopilot deployment profiles and related features. For more information, refer to:

- [Windows Autopilot and Surface devices](windows-autopilot-and-surface-devices.md)
- [Overview of Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot)

Autopilot deployment has several advantages: It allows you to use the factory provisioned operating system, streamlined for zero-touch deployment, to include pre-installation of Microsoft 365 Apps for enterprise (also known as Office Pro Plus).

Organizations already using modern management, security, and productivity solutions are well positioned to take advantage of the unique performance features in Surface Pro X. Customers using modernized line of business apps, Microsoft store (UWP) apps, or remote desktop solutions also stand to benefit.

## Image-based deployment considerations

Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager (formerly System Center Configuration Manager) currently do not support Surface Pro X for operating system deployment. Customers relying on image-based deployment should consider Surface Pro 8 while they continue to evaluate the right time to transition to modern deployment solutions. 

## Managing Surface Pro X devices

### Intune

A component of Microsoft Enterprise Mobility + Security, Intune integrates with Azure Active Directory for identity and access control and provides granular management of enrolled Surface Pro X devices. Intune mobile device management (MDM) policies have a number of advantages over older on-premises tools such as Windows Group Policy. This includes faster device login times and a more streamlined catalog of policies enabling full device management from the cloud. For example, you can manage LTE using eSIM profiles to configure data plans and deploy activation codes to multiple devices.<br> 

For more information about using Intune, refer to the [Intune documentation](/intune).

### Co-management

Once deployed in Autopilot, you can join Surface Pro X devices to Azure AD or Active Directory (Hybrid Azure AD Join) where you will be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which will install the 32-bit x86 ConfigMgr client.

### Third party MDM solutions

You may be able to use third-party MDM tools to manage Surface Pro X devices. For details, contact your MDM provider.

### Antivirus software

Microsoft Defender will help protect Windows 10 and Windows 11 on ARM-based PCs for the supported lifetime of the device. 

Some third-party antivirus software cannot be installed on devices running on an ARM-based processor. Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs. Contact your antivirus software provider to understand when their apps will be available.

## Servicing Surface Pro X

Surface Pro X ships with Windows 10 version 2004 and supports Windows 10, version 1903 and later. As an ARM-based device, it has specific requirements for maintaining the latest drivers and firmware. 

Surface Pro X was designed to use Windows Update to simplify the process of keeping drivers and firmware up to date for both home users and small business users. Use the default settings to receive Automatic updates.  To verify:

1. Go to **Start** > **Settings > Update & Security > Windows Update** > **Advanced Options.**
2. Under **Choose how updates are installed,** select **Automatic (recommended)**.

### Recommendations for commercial customers

- Use Windows Update or Windows Update for Business for maintaining the latest drivers and firmware. For more information, see [Deploy Updates using Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb).
- For more information about deploying and managing updates on Surface devices, see [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).
- Note that Windows Server Update Services (WSUS) does not support the ability to deliver drivers and firmware to Surface Pro X.

## Running apps on Surface Pro X

Most apps run on ARM-based Windows 10 PCs with limited exclusions.

### Supported apps

- Most x86 Win32 apps run on Surface Pro X.
- Native ARM64 and Microsoft Store UWP apps provide an excellent user experience utilizing the full native speed of the ARM-based processor while optimizing battery life.
- Apps that use drivers designed for a Windows 10 or Windows 11 PC running on an ARM-based processor.

> [!NOTE]
> With 64-bit emulation coming soon in Preview via the Windows Insider program, you'll be able to run 64-bit (x64) apps on Surface Pro X.

### FastTrack App Assure 

The App Assure program is available to commercial customers for their LOB, ISV and Microsoft first-party apps targeting Windows 10 on ARM. If commercial customers encounter an app compatibility issue using Windows 10 on ARM, Microsoft will provide developer resources to troubleshoot and assist with app remediations, at no additional cost. To learn more,visit [aka.ms/AppAssure](/fasttrack/products-and-capabilities#app-assure).

For more information about running apps on Surface Pro X, refer to:

- [Windows 10 ARM-based PCs Support FAQ](https://support.microsoft.com/help/4521606)
- [Windows 10 on ARM documentation](/windows/arm)

## Virtual Desktops (VDI)

Windows Virtual Desktop enables access to Windows desktops,applications, and data on any computing device or platform, from any location. To learn more, refer to the [Windows Virtual Desktop site](https://aka.ms/wvd). 

## Browsing with Surface Pro X

Popular browsers run on Surface Pro X:

- In-box Edge, Firefox, Chrome, and Internet Explorer all run on Surface Pro X.
- Firefox and Microsoft Edge based on Chromium run natively and therefore have enhanced performance on a Windows 10 PC on an ARM-based processor.

## Installing and using Microsoft Office

- Use Office 365 for the best experience on a Windows 10 or Windows 11 PC on an ARM-based processor.
- Office 365 "click-to-run" installs Outlook, Word, Excel, and PowerPoint, optimized to run on a Windows 10 or Windows 11 PC on an ARM-based processor.
- Microsoft Teams runs great on Surface Pro X.
- For "perpetual versions" of Office such as Office 2019, install the 32-bit version.

## VPN

To confirm if a specific third-party VPN supports a Windows 10 PC on an ARM-based processor, contact the VPN provider.

## Feature summary

The following tables show the availability of selected key features on Surface Pro X with Windows 10 or Windows 11 on ARM.


**Deployment**

| Feature                                                           | Y/N | Notes                                                                                                                             |
| ----------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                                                 | Yes |                                                                                                                                   |
| Support for Network Boot (PXE)                                    | No  |                                                                                                                                   |
| Windows Configuration Designer                                    | No  | Not recommended for Surface Pro X.                                                                                                |
| WinPE                                                             | Yes | Not recommended for Surface Pro X. Microsoft does not provide the necessary .ISO and drivers to support WinPE with Surface Pro X. |
| Endpoint Configuration Manager: Operating System Deployment (OSD) | No  | Not supported on Surface Pro X.                                                                                                   |
| MDT                                                               | No  | Not supported on Surface Pro X.                                                                                                   |

 
 
 **Management**
 

| Feature                                       | Y/N     | Notes                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| Intune                                        | Yes     | Manage LTE with eSIM profiles.                                                        |
| Windows Autopilot                             | Yes     |                                                                                       |
| Azure AD (co-management)                      | Yes     | Ability to join Surface Pro X to Azure AD or Active Directory (Hybrid Azure AD Join). |
| Endpoint Configuration Manager                | Yes     |                                                                                       |
| Power on When AC Restore                      | Yes     |                                                                                       |
| Surface Diagnostic Toolkit (SDT) for Business | Yes     |                                                                                       |
| Surface Asset Tag tool                        | Yes     |                                                                                       |
| Surface Enterprise management Mode (SEMM)     | Partial | No option to disable hardware on Surface Pro X at the firmware level.                 |
| Surface UEFI Configurator                     | No      | No option to disable hardware. on Surface Pro X at the firmware level.                |
| Surface UEFI Manager                          | Partial | No option to disable hardware on Surface Pro X at the firmware level.                 |

 

**Security**
 

 Feature                                       | Y/N     | Notes                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| BitLocker                                     | Yes     |                                                       |
| Windows Defender                              | Yes     |                                                                                       |
| Support for third-party antivirus             | See note| Some third-party antivirus software cannot be installed on running on an ARM-based processor. Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs. Contact your antivirus software provider to understand when their apps will be available. |
| Secure Boot               | Yes     |                                                                                       |
| Windows Information Protection                      | Yes     |                                                                                       |
| Surface Data Eraser (SDE)     | Yes     |                                                                                       |




## FAQ

### Can I deploy Surface Pro X with MDT or Endpoint Configuration Manager?

The Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager  currently do not support Surface Pro X for operating system deployment. Customers relying on image-based deployment should consider Surface Pro 8 while they continue to evaluate the right time to transition to the cloud.

### How can I deploy Surface Pro X?

Deploy Surface Pro X using Windows Autopilot.

### Is a BMR available?

Yes, refer to [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).

### Is Intune required to manage Surface Pro X?

Intune is recommended but not required. Once deployed in Autopilot, you can join Surface Pro X devices to Azure AD or Active Directory (Hybrid Azure AD Join) where you will be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which will install the 32-bit x86 ConfigMgr client.
