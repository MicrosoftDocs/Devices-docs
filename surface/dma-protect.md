---
title: Surface DMA Protection
description: This article describes DMA protection on compatible Surface devices
ms.prod: surface
ms.localizationpriority: medium
author: coveminer
ms.author: hachidan
ms.topic: overview
ms.date: 10/14/2022                        
ms.reviewer: carlol
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---
# DMA Protection on Surface devices

Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices. Newer Surface devices come with DMA Protection enabled by default. These include Surface Laptop Studio 2, Surface Go 4, Surface Laptop Go 3, Surface Pro 9, Surface Pro 9 with 5G, Surface Pro 8, Surface Laptop Studio, Surface Go 3, Surface Laptop SE, Surface Pro 7+, Surface Pro 7, Surface Laptop 3, Surface Laptop 4, Surface Laptop 5, and Surface Pro X. To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.

![System information showing DMA Protection enabled.](images/systeminfodma.png)

If a Surface removable SSD is tampered with, the device will shutoff power. The resulting reboot causes UEFI to wipe memory, to erase any residual data.
