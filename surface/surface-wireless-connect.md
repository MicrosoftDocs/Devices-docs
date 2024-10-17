---
title: Optimize Wi-Fi connectivity for Surface devices
description: This topic describes recommended Wi-Fi settings to ensure Surface devices stay connected in congested network environments and mobile scenarios.
ms.service: surface
author: coveminer
ms.localizationpriority: medium
ms.author: chauncel
ms.topic: how-to
ms.reviewer: chauncel
manager: frankbu
ms.date: 10/16/2024
appliesto:
- Windows 10
- Windows 11
---

# Optimize Wi-Fi connectivity on Surface devices

Surface devices are designed to maintain seamless connectivity and optimize power consumption to support all-day productivity. This article provides guidance on optimizing Wi-Fi performance and outlines the key settings to ensure uninterrupted wireless connectivity across different environments.

## Recommendations for IT admins

To ensure your organization’s Surface devices benefit from the latest wireless optimization, follow these key recommendations:

- **Install the latest drivers and firmware**: Use **Windows Update** or the [Surface Driver and Firmware MSI](manage-surface-driver-and-firmware-updates.md) to ensure Surface devices are up to date. Installing the latest updates improves performance, stability, and connectivity.
- **Configure access points for fast roaming**: Enable protocols like **802.11k, 802.11v, and 802.11r** to enhance roaming capabilities. These protocols allow Surface devices to transition smoothly between access points, reducing disruptions as users move between coverage areas.
- **Avoid custom configurations**: Maintain **default Wi-Fi settings** where possible to leverage the optimized factory configurations on Surface devices. These settings balance performance and power efficiency, ensuring reliability in typical usage scenarios.

## Configuring access points for optimal roaming capabilities

If you're managing wireless networks accessed by Surface devices, it's recommended to enable **802.11k, 802.11v, and 802.11r** protocols for seamless roaming. These protocols improve how Surface devices connect to the best available access points:

- **802.11r (Fast BSS Transition)**: Reduces handoff times between access points by minimizing authentication steps.
- **802.11k (Neighbor Reports)**: Provides the device with detailed information about nearby access points to optimize handoff decisions.
- **802.11v (BSS Transition Management Frames)**: Helps devices choose access points based on real-time conditions beyond signal strength, such as network congestion.

**Supported devices**: Most recent Surface devices, including Surface Pro 7 and later, Surface Laptop Studio, Surface Pro X, and Surface Go models, fully support these protocols.

## Managing wireless settings on Surface devices

In most cases, **default wireless settings** provide optimal performance. However, in complex network environments or in cases where users experience disruptions, IT admins can adjust key settings to improve Wi-Fi performance.

### Recommended adjustments

1. **Roaming aggressiveness**: You can configure the threshold at which Surface devices search for a new access point when the signal weakens.
   - **Default**: Medium (72% signal strength).
   - **Recommendation**: Increase roaming aggressiveness only if needed for environments with dense Wi-Fi networks.

> [!NOTE]
> Increasing roaming aggressiveness improves connectivity but can lead to faster battery depletion.

2. **Dual-band Wi-Fi capability**: By default, Surface devices dynamically switch between **2.4 GHz and 5 GHz** bands based on network availability and signal quality.

> [!TIP]
> Avoid forcing the device to connect only to the 5 GHz band, as many public Wi-Fi hotspots still use 2.4 GHz networks.

To configure Wi-Fi settings:

1. Open **Start** > **Device Manager**.
2. Under **Network adapters**, right-click your Wi-Fi adapter and select **Properties**.
3. Select the **Advanced** tab to adjust settings like **Roaming Aggressiveness** and **Preferred Band**.

## Troubleshooting Wi-Fi performance

### Check for firmware and driver updates

Surface devices rely on the latest **Wi-Fi driver and firmware updates** for optimal performance. Ensure your devices stay updated by following the steps in [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).

### Minimize signal interference

Wireless performance can be impacted by environmental factors such as **thick walls** or **metal obstructions**. Encourage users to:

- Avoid blocking the top of the Surface Pro or Surface Go, where the Wi-Fi radio receiver is located.
- Use the device in areas with strong signal coverage and minimal interference.

> [!TIP]
> When working in areas with many overlapping Wi-Fi networks (like apartment buildings), setting Surface devices to use the **5 GHz** band temporarily can reduce interference.

### Optimize performance with Surface tools

For IT admins, the **Surface Diagnostic Toolkit** can be used to identify and resolve common connectivity issues on Surface devices.

## Summary

Surface devices are designed to offer optimized wireless connectivity out of the box, with **default Wi-Fi settings** balancing performance and power consumption. By keeping devices updated with the latest firmware and drivers, enabling fast-roaming protocols, and using recommended configurations, organizations can ensure reliable connectivity and seamless productivity for their users.

For more information, see:

- [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md)
- [Deploy, manage, and service Arm-based Surface devices](surface-pro-arm-app-management.md)
