---
title: Surface Hub may install updates and restart outside maintenance hours
description: troubleshooting information for Surface Hub regarding automatic updates
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
ms.prod: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: troubleshooting
ms.localizationpriority: medium
ms.date: 04/15/2021
---

# Surface Hub may install updates and restart outside maintenance hours

Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window. The device then restarts if it's necessary. You can't use the device until the process is completed.

> [!NOTE]  
> This isn't expected behavior for missing a maintenance window. It occurs only if the device is out-of-date for a long time.

## Cause

To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below). During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Update for Business (WUfB). Once updates are complete, the Hub may restart.

Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved. For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window. If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates. This can occur during or outside the maintenance window. Once the download and installation has begun, the device may restart.

## To avoid this issue

It's important that you set aside maintenance time for Surface Hub to perform administrative functions. Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates. We recommend that you not use or reserve the Hub during scheduled maintenance period. A two-hour window should be reserved for updating.

One option that you can use to control the availability of updates is Windows Update for Business.

## Learn more
  
- [Maintenance window](manage-windows-updates-for-surface-hub.md#maintenance-window) 
