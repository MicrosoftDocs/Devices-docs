---
title: Surface Laptop SE overview
description: This article provides an overview of Surface Laptop SE for education. 
ms.prod: w11

ms.localizationpriority: medium

author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 01/11/2022
ms.reviewer: hachidan
manager: frankbu

appliesto:
- Windows 11
---

# Surface Laptop SE overview

Surface Laptop SE provides a managed device experience that simplifies learning for students at an affordable cost. It runs Windows 11 SE, a cloud-first OS, and [comes pre-loaded with widely used apps](#pre-installed-apps) like Microsoft Teams, Word, PowerPoint, Excel, OneNote, Microsoft Edge, Minecraft: Education Edition, Flipgrid, and more. 

:::image type="content" source="images/surface-laptop-se.png" alt-text="Surface Laptop SE showing Windows 11 SE Start menu":::<br>
*Figure 1. Surface Laptop SE showing Windows 11 SE Start menu*

Surface Laptop SE supports most applications that students and educators need, including Progressive Web Apps (PWAs), Universal Windows Platform apps (UWPs), and a [curated set of Win32 & Microsoft Store apps](#install-optional-apps). Unlike other Surface devices, Surface Laptop SE prevents users from installing their own apps. Instead, IT admins or technical leads manage Surface Laptop SE devices using Microsoft Endpoint Manager, which includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune), [Microsoft Intune for Education](https://www.microsoft.com/education/intune), and the new [Surface Management Portal](surface-management-portal.md). 

> [!NOTE]
> This article is intended for IT admins and education personnel who deploy and manage devices for school users. For general information or to order devices, see [Surface Laptop SE Slim Laptop for Students](https://www.microsoft.com/surface/business/surface-laptop-se).

## Simplified deployment, management & security

- Complete low-touch deployment for new devices using Windows Autopilot, quickly applying policies and installing apps. Windows Autopilot provides low-touch deployment and imaging out of the box, with many apps and policies pre-installed and preconfigured. IT can easily adjust device settings—including firmware settings—and install the apps students need so that everything is ready to go  when they first power on their device.
- Once devices are deployed, Microsoft Intune delivers streamlined remote management throughout the school year, allowing IT to manage apps, control security and privacy, and generate compliance reports.
- Lock the operating system with lid-lock when the laptop is closed, and control physical access with the integrated Kensington Nano Security Slot™.
- A newly designed non-exposed hinge, a plastic chassis, and a plastic border surrounding the screen that goes out to the bezel provide extra durability to better meet the needs and demands of student use.
- Intune and DFCI support secure device updates and management to the firmware layer. IT admins can control hardware elements such as mics, USB ports, cameras, and Bluetooth—and remove power to peripherals. The unique scannable Surface packaging allows easy identification of devices, with the device ID number staying the same when it comes time to re-enroll.

### Surface Management Portal

When you enroll Surface Laptop SE for cloud management and users sign in  for the first time, information from these Surface devices automatically flows into the [Surface Management Portal](surface-management-portal.md), giving you a single pane of glass for Surface-specific device admin activities. You can get insights into device compliance, support activity, and warranty coverage. Quickly see the status of each device, which ones are still in warranty or expiring soon, and the status of active support requests.

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="Surface Management Portal showing warranty coverage for Surface Laptop SE":::
*Figure 2. Surface Management Portal showing warranty coverage for Surface Laptop SE*

## Common admin scenarios

| Scenario                                                            | Description                                                                                                                                                                                                                                                                                                                          | Learn more                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Remotely configure Surface Laptop SE devices with Windows Autopilot | Windows Autopilot provides low-touch deployment and imaging out of the box, with many apps and policies pre-installed and preconfigured. IT can easily adjust device settings—including firmware settings—and install the apps students need so that everything is ready to go when they first power on their device.                 |[Set up Intune for Education devices with Windows Autopilot](/intune-education/windows-autopilot-setup)<br><br>[How should I enroll my devices?](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| Deploy updates via Intune for Education                             | IT admins can use Microsoft Intune to push out OS and app updates to Surface Laptop SE devices across the school and throughout the year. If necessary, they can disable hardware elements like the camera or Bluetooth on an individual device or reset a specific device if a student is experiencing technical issues. |[Manage devices running Windows 11 SE](/intune-education/windows-11-se-overview)<br><br>[Microsoft Education documentation and resources](/microsoft-365/education/)<br><br>[Get started with Intune for Education](/microsoft-365/education/deploy/intune-for-education)<br><br>[Use Intune for Education to manage groups, apps, and settings](/microsoft-365/education/deploy/use-intune-for-education) |
| Replace devices as needed                                           | If students crack their screen or otherwise damage the device, IT admins can quickly deploy spare devices, transferring the students' cloud identities to the new devices.                                                                                                  |[Remote device actions in Intune for Education](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| Deploy new apps via Intune                                          | If teachers request a new app, IT admins can remotely install it on all student devices using Intune.                                                                                                                                                                                                                            |[Install apps for all users](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| Reset devices via Intune                                            | When students return their Surface Laptop SE devices at the end of the school year, IT admins can use Intune to reset the devices for the next class.                                                                                                           |[Use Autopilot Reset to reconfigure devices with Intune for Education](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

### Known issues

| Scenario                                                            | Description                                                                                                                                                                                                                                                                                                                          | Learn more                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot reports  error code 0x81039023 on Windows 11 SE during deployment | There's currently a known issue affecting Windows 11 SE devices updated to the [Windows 11 May updates (KB5013943)](https://support.microsoft.com/topic/may-10-2022-kb5013943-os-build-22000-675-14aa767a-aa87-414e-8491-b6e845541755), which prevents applications from being installed during the [Windows Autopilot pre-provisioning](/mem/autopilot/pre-provision) process. As a result, deployment fails when the Enrollment Status Page (ESP) timeout is reached (default is 60 minutes).               |[Recovering from Windows Autopilot error code 0x81039023 on Windows 11 SE](https://techcommunity.microsoft.com/t5/intune-customer-success/support-tip-recovering-from-windows-autopilot-error-code/ba-p/3283743)  |


## Pre-installed apps

Surface Laptop  SE comes with the following pre-installed apps:

- Microsoft Excel
- Flipgrid
- Groove music
- Maps
- Microsoft Edge
- Microsoft News
- Microsoft Teams
- Microsoft To Do
- Microsoft Whiteboard
- Minecraft Education Edition
- Notepad
- Microsoft Office
- OneDrive
- OneNote
- Outlook on the web
- Paint
- Photos
- PowerPoint
- Snipping tool
- Sticky notes
- Surface app
- Surface Diagnostic Toolkit
- Tips
- Voice recorder
- Weather
- Word

## Install optional apps

IT admins can install [more apps](/education/windows/windows-11-se-overview#available-apps) such as Chrome or Zoom via Intune. Note there's no app store for Surface Laptop SE. Refer to the following instructions to complete your app deployment: 

- [App deployment](/intune-education/windows-11-se-overview#app-deployment)


## Repairability

Surface Laptop SE is designed to enable skilled technicians to service devices locally by quickly replacing core components:

- Display Module  
- Keyboard & Bucket
- Speaker & Wi-Fi Module
- Battery
- Feet

Schools can use an Authorized Service Provider or their own skilled technicians to repair devices onsite following the Microsoft-provided "Surface Laptop SE Service Guide," available from [Surface Service Guides](https://www.microsoft.com/download/100440).

To learn more, see:

- [Surface Laptop SE Repair Video](https://youtu.be/fVjjSqfp75g)
- [Top support solutions for Surface devices](support-solutions-surface.md)

## Surface Laptop SE tech specs

| Feature                     | Description                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Dimensions**              | - 11.17" x 7.6" x 0.70" (283.70 mm x 193.05 mm x 17.85 mm)                                                                                                                                                |
| **Storage**<sup>1</sup>     | - On board, Embedded Multimedia Card (eMMC) 64 GB or 128 GB                                                                                                                                                 |
| **Display**                 | - Screen: 11.6" TFT Liquid Crystal Display Module<br>- Display Resolution: 1366 x 768 (135 PPI)<br>- Aspect Ratio: 16:9<br>- Contrast ratio: 800:1 (Typical)<br>- Luminance: 220 nits<br>- No Cover Glass |
| **Battery**                 | - 35 Wh (nominal), 33.9 Wh (min)<br>- 16 hours of battery life <sup>2</sup>                                                                                                                                              |
| **Memory**                  | - 4 GB or 8 GB DDR4 (2400 MHz min)                                                                                                                                                                          |
| **CPU / Graphics**          | - Intel® Celeron® Processor N4020 / Intel® UHD Graphics 600<br>- Intel® Celeron® Processor N4120 / Intel® UHD Graphics 600                                                                                |
| **Connections**             | - 1 x USB-A<br>- 1 x USB-C<br>- 1 x Barrel type DC connector<br>- 1 x 3.5 mm Headphone/Mic Jack                                                                                                           |
| **Security**                | - Firmware TPM across all configurations (Commercial)<br>- Nano Security Lock slot                                                                                                                        |
| **Cameras, video, & audio** | - 1MP front-facing camera with up to 720p 30-fps video<br>- 2 W Stereo Speakers<br>- Single digital microphone                                                                                              |
| **Software**                | - Windows 11 SE<br>- Microsoft 365 for Education<sup>3</sup>                                                                                                                                                         |
| **Wireless**                | - Wi-Fi: 802.11ac (2x2)<br>- Bluetooth Wireless 5.0 LE                                                                                                                                                    |
| **Sensors**                 | - 1 x Hall-effect sensor                                                                                                                                                                                  |
| **Exterior**                | - Casing: All plastic body unpainted<br>- Colors: Glacier<br>- Physical buttons: Power and Volume on keyboard<br>- Hinge: 135-degrees open angle                                                          |
| **Weight**                  | - 2.45 lb. (1,111.3 g)                                                                                                                                                                                    |
| **Keyboard and trackpad**   | - Standard Windows Keyboard for 11.6" without backlight<br>- Standard no floating precision trackpad                                                                                                      |
| **Thermals**                | - Passively cooled                                                                                                                                                                                        |
| **Power supply**            | - In-box, 45 W with DC Barrel charger                                                                                                                                                                      |
| **In the box**              | - Surface device<br>- Power supply<br>- Quick Start Guide<br>- Safety and warranty documents                                                                                                              |
| **Warranty**<sup>4</sup>    | - One-year limited hardware warranty                                                                                                                                                                      |

## References

1. System software and updates use significant storage space. Available storage is subject to change based on system software and updates and apps usage. 1 GB = 1 billion bytes. 1 TB = 1,000 GB. For more information, see [Surface Storage](https://support.microsoft.com/help/4023513/surface-surface-storage?) for more details.
2. Battery life varies significantly based on usage, network and feature configuration, signal strength, settings and other factors. See [Surface battery testing and estimated performance](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) for details.
3. Requires qualifying Microsoft 365 or Office 365 license; sold separately. [Compare Microsoft 365 education plans](https://aka.ms/EDU-Plan-Comparison).
4. Microsoft’s Limited Warranty is in addition to your consumer law rights.


## Learn more

- [Order Surface Laptop SE](https://www.microsoft.com/surface/business/surface-laptop-se)
- [Introducing Surface Laptop SE for Education](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [Windows 11 SE for Education](/education/windows/windows-11-se-overview)
- [Manage devices running Windows 11 SE](/intune-education/windows-11-se-overview)
- [Set up Intune for Education devices with Windows Autopilot](/intune-education/windows-autopilot-setup)
- [Microsoft Education documentation and resources](/microsoft-365/education/)
- [Outlook on the web](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)
- [A purpose-built hardware & software solution for education](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/a-purpose-built-hardware-amp-software-solution-for-education/ba-p/1419013)