---
title: Surface Hub 3 OS update history
description: Discover the latest updates for Surface Hub 3 running Microsoft Teams Rooms, focusing on security, performance, and compliance improvements. 
ms.service: surface-hub
author: coveminer
ms.author: dpandre
ms.topic: how-to
ms.localizationpriority: high
ms.date: 10/18/2024
---

# Surface Hub 3 update history

[!INCLUDE [Hub MTR Scope](includes/hub-mtr-scope.md)]

## Introduction

This article provides a detailed history of firmware and driver updates released for Surface Hub 3 and [migrated Hub 2S](surface-hub-2s-migrate-to-mtr-w.md) devices running Microsoft Teams Rooms on Windows. Updates are designed to enhance security, improve performance, and ensure compliance with regulatory requirements. 

All updates are cumulative, meaning installing the latest update  includes all improvements from previous releases.

Surface Hub devices will receive driver and firmware updates until the date listed in the [Surface Hub devices driver and firmware lifecycle](surface-hub-driver-firmware-accessories-lifecycle.md).

> [!TIP]
> This page is refreshed as new updates are released. Please refer to the [Surface Hub Important Information](https://support.microsoft.com/products/surface-devices/surface-hub) page for related topics on current and past releases that may require your attention.

## Improvements and fixes in the updates

### September 2024 updates

#### September 30 release

This update:

* Addresses a potential security vulnerability related to Intel® Security Advisories INTEL-SA-00999, INTEL-SA-01083 & INTEL-SA-01071.
* Addresses data collection regulatory requirements and updates the consent experience for data transmission.

This release contains the following components. The specific components installed are based on your device's configuration:

| Windows Update Name                               | Device Manage                           |
|---------------------------------------------------|-----------------------------------------|
| Intel - SoftwareComponent - 1.71.99.0             | Intel(R) iCLS Client - Software components |
| Intel - System - 2406.5.5.0                       | Intel(R) Management Engine Interface #1 - System devices  |
| _Hub 3:_ Surface - Firmware - 7.100.143.0<br/> _Hub 2S:_ Surface - Firmware - 699.1205.768.0                | Surface UEFI - Firmware |
| _Hub 3:_ Surface - Firmware - 15.0.2573.1<br/> _Hub 2S:_ Surface - Firmware - 11.8.96.4657                 | Surface ME - Firmware |
| Surface - Firmware - 2.100.139.0            | Surface System Aggregator - Firmware |
| Surface - System - 6.214.10.0          | Surface Integration Service - System devices |
| Surface - System - 10.105.10.0            | Surface System Telemetry Driver - System devices |
| _Hub 3:_ Realtek - Net - 10.59.20.0420<br/> _Hub 2S:_ Realtek - Net - 1153.13.20.0420                 | Surface Ethernet Adapter - Network adapters |
