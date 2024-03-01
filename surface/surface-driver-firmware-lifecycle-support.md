---
title: Surface devices driver and firmware lifecycle
description: This article provides detailed lifecycle information to help plan and manage hardware and software deployments for Windows-based Surface devices.
ms.service: surface
ms.localizationpriority: high
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 01/25/2024
ms.reviewer: phorton
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---

# Surface devices driver and firmware lifecycle

This page provides essential information on the driver and firmware lifecycle for Windows-based Surface devices, designed to assist IT admins in effectively planning and managing their hardware and software deployment strategies.

This policy outlines the lifecycle of driver and firmware updates for Surface devices. It begins on the initial release of a device and extends until the designated end-of-servicing date when Surface ceases to publish updates. The following sections detail the policy and specify end-of-servicing dates.

## Overview

The Surface driver and firmware lifecycle consists of two parts: 

- The [driver and firmware servicing period](#device-servicing-period) for a device. 
- The [support provided for OS versions](#os-version-support) during that period.

### Device servicing period

The Surface Driver and Firmware Servicing Period defines the period that updates are available for an accessory. The Accessory Servicing Period starts when an accessory is released.

- **For devices released before January 1, 2021:** Surface devices will receive driver and firmware updates for at least four years from when the device was first released. In cases where the servicing duration is longer than four years, an updated end-of-servicing date will be published before the date of the last servicing.

- **For devices released on and after January 1, 2021:** Surface devices will receive driver and firmware updates for at least six years from when the device was first released. In cases where the servicing duration is longer than six years, an updated end-of-servicing date will be published before the date of the last servicing.

### OS version support

OS version support defines the operating system versions Surface supports during the Device servicing period. Surface devices receive driver and firmware updates for Windows OS versions released in the prior 30 months. Surface won't support Windows OS versions earlier than those supported at device release. To see the minimum supported OS version for your Surface device, visit the [Surface supported operating systems support page](https://support.microsoft.com/help/2858199/surface-supported-operating-systems).

Once the device servicing period is concluded, devices continue to receive Windows OS feature and security updates per the Windows Lifecycle Policy as described on the [Microsoft Lifecycle Policy support page](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy).

## Surface driver and firmware lifecycle period

The following table shows the release and end-of-servicing dates for each Surface device with a defined driver and firmware lifecycle policy:

| Surface device                         | Release date        | End-of-servicing date for firmware & drivers |
| -------------------------------------- | ------------------- | -------------------------------------------- |
| Surface Studio 2                       | October 2, 2018     | October 2, 2024                              |
| Surface Laptop 3                       | October 22, 2019    | July 30, 2024                                |
| Surface Pro 7                          | October 22, 2019    | October 30, 2025                            |
| Surface Pro X SQ1                      | November 5, 2019    | August 10, 2025                              |
| Surface Go 2                           | May 6, 2020         | December 30, 2024                            |
| Surface Book 3                         | May 26, 2020        | April 1, 2025                                |
| Surface Pro X SQ2                      | October 13, 2020    | August 10, 2025                              |
| Surface Laptop Go                      | October 13, 2020    | October 13, 2024                             |
| Surface Pro 7+                         | January 15, 2021    | January 15, 2027                             |
| Surface Laptop 4                       | April 15, 2021      | April 15, 2027                               |
| Surface Pro 8                          | October 5, 2021     | October 5, 2027                              |
| Surface Laptop Studio                  | October 5, 2021     | October 5, 2027                              |
| Surface Go 3                           | October 5, 2021     | October 5, 2027                              |
| Surface Pro X Wi-Fi                    | October 5, 2021     | October 5, 2027                              |
| Surface Laptop SE                      | January 11, 2022    | January 11, 2028                             |
| Surface Laptop Go 2                    | June 7, 2022        | June 7, 2028                                 |
| Windows Dev Kit 2023                   | October 24, 2022    | October 24, 2028                             |
| Surface Laptop 5                       | October 25, 2022    | October 25, 2028                             |
| Surface Pro 9                          | October 25, 2022    | October 25, 2028                             |
| Surface Studio 2+                      | October 25, 2022    | October 2, 2028                              |
| Surface Go 4                           | September 21, 2023  | September 21, 2029                           |
| Surface Laptop Go 3                    | October 3, 2023     | October 3, 2029                              |
| Surface Laptop Studio 2                | October 3, 2023     | October 3, 2029                              |

## Legacy products

The following table lists products that have passed their end-of-servicing date based on the driver and firmware lifecycle policy. These devices no longer receive newer driver and firmware updates than those listed on [Surface update history](https://support.microsoft.com/surface/surface-update-history-6036fff5-edec-c8ec-9796-a5633aac9488).

| Surface device                             | Release date       | End-of-servicing date for firmware & drivers |
| ------------------------------------------ | ------------------ | -------------------------------------------- |
| Surface RT                                 | October 26, 2012   | April 11, 2017                               |
| Surface Pro                                | February 9, 2013   | April 11, 2017                               |
| Surface 2                                  | October 22, 2013   | April 10, 2018                               |
| Surface Pro 2                              | October 22, 2013   | April 10, 2018                               |
| Surface Pro 3                              | June 20, 2014      | November 13, 2021                            |
| Surface 3                                  | May 5, 2015        | November 13, 2021                            |
| Surface Book                               | October 26, 2015   | November 13, 2021                            |
| Surface Pro 4                              | October 26, 2015   | November 13, 2021                            |
| Surface Book with Performance Base         | November 10, 2016  | November 13, 2021                            |
| Surface Studio (1st gen)                   | December 15, 2016  | November 13, 2021                            |
| Surface Laptop (1st gen)                   | June 14, 2017      | November 13, 2021                            |
| Surface Book 2                             | November 17, 2017  | June 30, 2023                                |
| Surface Go                                 | August 2, 2018     | August 2, 2022                               |
| Surface Laptop 2                           | October 16, 2018   | December 27, 2022                            |
| Surface Pro 6                              | October 16, 2018   | June 30, 2023                                |
| Surface Go with LTE Advanced               | November 20, 2018  | November 20, 2022                            |
| Surface Pro (5th gen)                      | June 15, 2017      | January 15, 2024                             |
| Surface Pro LTE (5th gen) (Model 1807)     | December 1, 2017   | January 15, 2024                             |

## Learn more

- [Driver and firmware lifecycle for Surface Hub devices and accessories](/surface-hub/surface-hub-driver-firmware-accessories-lifecycle)
- [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md)
- [Surface device compatibility with Windows 10 Long-Term Servicing Channel (LTSC)](surface-device-compatibility-with-windows-10-ltsc.md)
- [Surface Warranty and Support Plans](https://www.microsoft.com/surface/business/warranty-service-offerings-and-support)
- [Surface update history](https://support.microsoft.com/surface/surface-update-history-6036fff5-edec-c8ec-9796-a5633aac9488)
