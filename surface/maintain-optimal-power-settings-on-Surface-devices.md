---
title: Best practice power settings for Surface devices
description: Learn best practices for optimizing power settings on Surface devices, including Copilot+ PCs, to extend battery life and improve energy efficiency.
ms.service: windows-11
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.reviewer: 
manager: frankbu
ms.localizationpriority: medium
ms.date: 10/16/2024
appliesto:
- Windows 10
- Windows 11
---

# Best practice power settings for Surface devices

Surface devices are designed to take full advantage of the latest advancements in energy-efficient computing, offering a seamless experience across workloads. Whether using the device in an office environment, on the go, or in standby mode, Surface dynamically allocates power to individual components, waking system elements only when necessary—such as handling network traffic or notifications—before returning to a low-power state (S0ix).

## Recommendations for IT admins

To maximize efficiency across your organization, follow these key power management best practices:

- **Install the latest drivers and firmware**: Regular updates from Windows Update or Surface Driver and Firmware MSI packages ensure optimal power management settings through a **balanced power plan**. This creates the most efficient configuration by default and leverages Surface's **Modern Standby** capabilities.

- **Use default power settings**: Avoid creating custom power profiles. The **Balanced power plan** built into Surface devices is optimized for battery life and performance. For users or IT admins who must adjust profiles, export power settings from one Surface model to ensure consistency across similar devices.

> [!TIP]
> Only export profiles across identical models. For example, export a power profile from one **Surface Pro 9** to another, but not between **Surface Pro** and **Surface Laptop** models.

- **Monitor battery health and usage patterns**: Use the **Surface app** to review battery usage and health over time. Encourage users to lower screen brightness and reduce background activity where possible. **Screen timeouts** and moderate brightness settings offer simple ways to prolong battery life without compromising functionality.

- **Exclude Surface from group power policies**: Centralized group policies may interfere with the device-optimized power plans. Let **Surface devices** operate on their native power profile to maintain full functionality.

- **Windows performance power slider**: Encourage users to adjust the **Windows power slider** based on their needs. Slide toward **Best Performance** for demanding tasks or toward **Best Battery Life** to conserve power. This setting allows users to quickly adjust power settings on the fly.

- **Battery saver mode**: Enable **Battery Saver** when running on battery. This feature reduces background activities and dims the display when battery levels fall below a user-defined threshold.

  > **To configure Battery Saver:**  
  1. Select **Start** > **Settings** > **System** > **Power & Battery**.  
  2. Under **Battery**, choose **Turn battery saver on automatically if my battery falls below...** and adjust the slider.

## Modern Standby and S0ix

Surface devices utilize **Modern Standby** with two modes to maintain balance between power efficiency and performance:

- **Connected Standby**: Keeps the network active for real-time delivery of emails, notifications, and cloud-synced data.
- **Disconnected Standby**: For extended battery life, this mode disables Wi-Fi and Bluetooth but still offers instant-on functionality when needed.

By default, **S0ix**—the deepest runtime idle platform state—ensures Surface devices operate in a low-power state even when idle, helping conserve battery across all workloads.

### Integrated battery-saving features

The **Surface app** and **Battery Saver mode** make it easy for users to extend battery life:

- **Surface App for Battery Insights**: Users can monitor usage patterns, including which apps drain the most energy, and adjust accordingly.
- **Windows Battery Saver Mode**: Reduces energy consumption by limiting background activities and dimming the display automatically when the battery falls below a set threshold.

For more tips on extending battery life, see:

- [Maximize Your Surface Battery Life](https://support.microsoft.com/en-us/surface/maximize-your-surface-battery-life-45479867-a7fa-33dd-fc4d-6762e9b3b11a)  
- [Battery-Saving Tips for Windows](https://support.microsoft.com/en-us/windows/battery-saving-tips-for-windows-a850d64d-ee8e-c8d2-6c75-8ffe6ea3ea99)

### ARM-based Copilot+ PCs and battery efficiency

With the latest ARM-based **Copilot+ PCs**, including the **Surface Pro (11th Edition)** and **Surface Laptop (7th Edition)**, energy efficiency is taken to the next level. These devices leverage **ARM processors**, which are inherently more power-efficient, enabling extended battery life for mobile workers. The combination of ARM-based architecture and Windows 11 optimization ensures a balance between performance and efficiency, supporting Modern Standby and seamless transitions between work sessions.

### Best practices for extended battery life

| **Best practice** | **Where to adjust** | **Next steps** |
|-------------------|---------------------|----------------|
| Ensure devices are updated | Windows Update | Select **Settings** > **Windows Update** and check for updates. |
| Choose the best power setting | Power slider | Click the **battery icon** on the taskbar and adjust the slider. |
| Use Battery Saver | Battery settings | Go to **Settings** > **System** > **Power & Battery**, and enable **Battery Saver**. |
| Adjust screen brightness | Battery settings | Enable **Lower screen brightness while in Battery Saver**. |
| Investigate power issues | Troubleshooter | Search for **Troubleshoot Power** in the taskbar and follow instructions. |
| Monitor app usage | Surface app | Open the **Surface app** to view app energy consumption. |
| Inspect power cords | Physical inspection | Check for worn or damaged power cables. |

### Summary

By following these best practices and leveraging built-in Surface features like Modern Standby, Battery Saver, and the Surface app, IT admins can ensure optimal performance and battery life for their devices. The latest Copilot+ PCs, powered by ARM processors, offer even more power efficiency, supporting flexible work scenarios and mobile productivity.

For more detailed recommendations, visit:

- [Maximize Your Surface Battery Life](https://support.microsoft.com/en-us/surface/maximize-your-surface-battery-life-45479867-a7fa-33dd-fc4d-6762e9b3b11a)  
- [Battery-Saving Tips for Windows](https://support.microsoft.com/en-us/windows/battery-saving-tips-for-windows-a850d64d-ee8e-c8d2-6c75-8ffe6ea3ea99)  
