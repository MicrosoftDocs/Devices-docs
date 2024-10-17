---
title: Surface DMA Protection
description: Learn about DMA protection on Surface devices, a security feature that safeguards against vulnerabilities associated with removable SSDs and external storage.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 10/17/2024                        
ms.reviewer: carlol
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---
# DMA Protection on Surface devices

Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices. Newer Surface devices come with DMA Protection enabled by default. These include: 

- Surface Laptop (7th Edition), Surface Laptop 6, Surface Laptop 5, Surface Laptop 4, Surface Laptop 3, Surface Laptop SE, Surface Laptop Studio 2, Surface Laptop Studio, and Surface Laptop Go 3.
- Surface Pro (11th Edition), Surface Pro 10, Surface Pro 10 with 5G Surface Pro 9, Surface Pro 9 with 5G, Surface Pro 8, Surface Pro 7+, Surface Pro 7, and Surface Pro X.
- Surface Go 4 and Surface Go 3. 

To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.

![System information showing DMA Protection enabled.](images/systeminfodma.png)

If a Surface removable SSD is tampered with, the device will shut off power. The resulting reboot causes UEFI to wipe memory, to erase any residual data.
