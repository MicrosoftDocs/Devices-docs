---
title: Long-Term Servicing Channel (LTSC) for Surface devices
description: Learn how Surface devices align with Windows LTSC editions, offering stability for specialized systems, with guidance on transitions to Windows 11
ms.service: surface
author: coveminer
ms.author: chauncel
ms.topic: conceptual
ms.localizationpriority: medium
ms.date: 10/23/2024
manager: frankbu
---

# Long-Term Servicing Channel (LTSC) for Surface devices

Surface devices are designed for productivity and general-purpose use, benefiting from continuous updates delivered via the Semi-Annual Channel (SAC). However, some organizations might require the **Long-Term Servicing Channel (LTSC)** for special-purpose systems, such as manufacturing equipment or healthcare environments.

> [!IMPORTANT]  
> With **Windows 10** support ending on **October 14, 2025**, we recommend transitioning to **Windows 11**, **Windows 365**, or using **Extended Security Updates (ESU)** for legacy systems. See [End of support for Windows 10](https://www.microsoft.com/windows/end-of-support).

## New LTSC for Windows 11

For organizations using Surface devices in scenarios where stability is more important than frequent updates—such as **medical equipment**, **ATMs**, or **point-of-sale systems**—LTSC ensures long-term reliability. These systems benefit from fewer updates, minimizing disruptions while maintaining critical functionality.

- **Windows 11 Enterprise LTSC 2024**: Designed for specialized systems, offering long-term support with limited feature updates.  
- **Windows 11 IoT Enterprise LTSC 2024**: Available through OEMs or Volume Licensing, suitable for embedded systems requiring long-term maintenance.

To learn more, see [Windows 11 Enterprise LTSC 2024](/windows/whats-new/ltsc/whats-new-windows-11-2024) and [Windows 11 IoT Enterprise LTSC 2024](/windows/iot/iot-enterprise/whats-new/windows-11-iot-enterprise-ltsc-2024).

### LTSC availability

- **Windows 11 Enterprise LTSC 2024**: Available via Volume Licensing on a **per-user or per-device** model.  
- **Windows 11 IoT Enterprise LTSC 2024**: Offered through OEMs or Microsoft’s Volume Licensing program.

## Limitations of LTSC for Surface devices

While LTSC provides long-term stability, it might limit certain Surface features. Key experiences that rely on **Windows Feature Updates**—such as **Direct Ink improvements**, **the Surface app for pressure sensitivity settings**, and **Windows Ink Workspace**—are unavailable.

Using LTSC with Surface devices might also limit the functionality of core apps, such as **Microsoft Edge**, **OneNote**, **Camera**, and **Calendar**, which are optimized for the Semi-Annual Channel.

Additionally:

- **Driver and firmware updates** aren't explicitly tested against LTSC editions, potentially leading to compatibility issues.
- **Replacement devices** might include newer hardware components that require more recent drivers, which LTSC might not support.

## General-purpose Surface devices and LTSC

Surface devices that run **productivity apps like Microsoft Office**, **access Microsoft Store apps**, or **browse the internet** should remain on **Windows 11 Pro or Enterprise**, using the Semi-Annual Channel to receive the latest features and security patches.

> [!NOTE]  
> Organizations using a specific LTSC version may need to upgrade to newer LTSC releases or switch to **Windows 11 Pro or Enterprise** to maintain compatibility with new Surface hardware, such as **Surface Pro 10** or **Surface Laptop 6**. For more information, see [Windows LTSC Lifecycle FAQ](/lifecycle/faq/windows#what-are-the-requirements-for-servicing-and-updating-the-windows-10-long-term-servicing-channel--ltsc--).

## Recommendations for organizations using LTSC

For devices that only perform **single-task functions**, such as kiosks or embedded systems, LTSC offers a stable environment with minimal updates. However, for most other cases, organizations should:

- **Use SAC with Windows 11**: This solution ensures access to the latest Surface features, drivers, and firmware updates.
- **Transition from Windows 10 LTSC**: Perform **in-place upgrades** to Windows 11 using **Endpoint Configuration Manager** to avoid compatibility issues with new hardware.