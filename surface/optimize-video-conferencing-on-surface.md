---
title: Optimize video conferencing on Surface devices
description: This page provides best practices for using Microsoft Teams and other video conferencing solutions on Surface devices
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/10/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
---

# Optimize video conferencing on Surface devices

Surface devices take advantage of the latest advances in mobile device energy consumption to deliver a streamlined experience optimized across workloads. For most workloads, this provides a great experience. For some workloads using Microsoft Teams or other video conferencing applications, you should follow these recommendations to ensure the best experience.

## Surface drivers and firmware

Microsoft regularly releases updates for Surface devices and has released several Surface updates that target video conferencing workloads, including:

- System performance improvements
- Power consumption improvements in camera drivers
- Graphics driver updates
- Power settings optimizations

### Get updates to all devices

Ensure your organization has a process for your devices to receive these updates. If you are using Windows Update or [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb), you are already receiving the latest Surface updates when they are released. Check for updates using Windows Update and verify the newest Surface updates have been installed. To learn more, see:

- [Surface update history](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)
- [Install Surface and Windows updates](https://www.microsoft.com/surface/support/performance-and-maintenance/install-software-updates-for-surface?)

If you are using other options to install Surface drivers and firmware updates, you will need to install the latest Surface updates manually using the published MSI files or install the updates using Configuration Manager. To learn more, see:

- [Download drivers and firmware for Surface](https://support.microsoft.com/help/4023482)
- [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md)
- [How to manage Surface driver updates in Configuration Manager](https://support.microsoft.com/help/4098906)

### Graphics driver updates for Microsoft Teams

Newer Surface device models with 10th and 11th generation Intel processors have received graphics driver updates that help with video conferencing workloads. To enable these improvements, make sure you install the following:

- Microsoft Teams version **1.4.00.22472** or later.
- Intel graphics driver **27.20.100.9621** or later.

### Power settings optimizations

Surface devices can adjust performance-related power settings by changing the Windows performance power slider position in Windows 10, also known as power mode in Windows 11.

Some Surface devices have received updates that include power setting optimizations for video conferencing workloads based on the power slider position or power mode. However, because Windows 10 and Windows 11 use the **Recommended** power slider position and power mode position for video conferencing workloads, you will need to adjust the power slider to enable these optimizations:

1. Connect to AC power (optimizations won’t run when using battery power).  
2. Adjust the power slider or power mode position to use **Better Performance** or **Best Performance.**

## Learn more

- [Best practice power settings for Surface devices](maintain-optimal-power-settings-on-surface-devices.md)
- [Maximize your Surface battery life](https://support.microsoft.com/surface/maximize-your-surface-battery-life-45479867-a7fa-33dd-fc4d-6762e9b3b11a)
