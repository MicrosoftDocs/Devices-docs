---
title: Surface Brightness Control
description: This article describes how you can use the Surface Brightness Control app to manage display brightness in point-of-sale and kiosk scenarios.
ms.service: surface
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.reviewer: chauncel
manager: frankbu
ms.localizationpriority: medium
appliesto:
- Windows 10
- Windows 11
ms.date: 09/21/2023
---

# Surface Brightness Control

When deploying Surface devices in point of sale or other "always-on"
kiosk scenarios, you can optimize power management using the Surface Brightness Control app. Surface Brightness Control is designed to help reduce thermal load and lower the overall carbon footprint for deployed Surface devices. The tool automatically dims the screen when not in use and includes the following configuration options:

- Period of inactivity before dimming the display.
- Brightness level when dimmed.
- Maximum brightness level when in use.

Download Surface Brightness Control from the [Surface IT Toolkit](surface-it-toolkit-library.md) 

## Supported devices

- Surface Pro 3 and later
- Surface Pro X (all generations)
- Surface 3
- Surface Book (all generations)
- Surface Laptop Studio (all generations)
- Surface Studio (all generations)
- Surface Laptop (all generations)
- Surface Laptop Go (all generations)
- Surface Go (all generations)

## Run Surface Brightness Control

- Install **Surface_Brightness_Control_v1.20.139.0.msi** on the target device, and Surface Brightness Control begins working immediately.

## Configure Surface Brightness Control

You can adjust the default values via the Windows Registry. For more
information about using the Windows Registry, refer to the [Registry
documentation](/windows/desktop/sysinfo/registry).

1. Run **regedit** from a command prompt to open the Windows Registry Editor.
2. Navigate to Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Surface\Surface Brightness Control.
3. Adjust the Registry key values, as described in the following table.

> [!TIP]
> If you're running an older version of Surface Brightness control, navigate to: Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Surface\SurfaceBrightnessControl\

| Registry Setting | Data| Description  
|-----------|------------|---------------
| BrightnessControlEnabled  |  Default: 01  <br> Options 01, 00 <br> Type: REG_BINARY |  This setting allows you to turn Surface Brightness Control on or off. To disable Surface Brightness Control, set the value to 00. If you don't configure this setting, Surface Brightness Control is on. |
| BrightnessControlOnPowerEnabled| Default: 00 <br> Options: 01, 00 <br> Type: REG_BINARY | This setting allows you to turn off Surface Brightness Control when the device is directly connected to AC power. To disable Surface Brightness Control when AC power is plugged in, set the value to 00. If you don't configure this setting when plugged into AC power, Surface Brightness Control is off. |
|AlwaysAllowBrightenEnabled| Default: 01 <br> Options: 01, 00 <br> Type: REG_BINARY | This setting allows Surface Brightness Control to brighten the screen when AC power is connected, even if BrightessControlOnPowerEnabled is set to 00 (disabled).  If you disable this setting and AC power is connected while the screen is dimmed, it will not brighten if BrightControlOnPowerEnabled is also set to 00 (disabled).|
| DimmedBrightness   | Default: 20  <br>Options Range of 0-100 percent of screen brightness <br> Data Type: Positive integer <br> Type: REG_DWORD | This setting allows you to manage brightness range during periods of inactivity. If you don't configure this setting, the brightness level will drop to 20 percent of full brightness after 30 seconds of inactivity. |
FullBrightness   | Default: 100  <br>Options Range of 0-100 percent of screen brightness <br> Data Type: Positive integer <br> Type: REG_DWORD  | This setting allows you to manage the maximum brightness range for the device. If you don't configure this setting, the maximum brightness range is 100 percent.|  
| InactivityTimeout| Default: 30 seconds <br>Options Any numeric value  <br>Data Type: Integer  <br> Type: REG_DWORD | This setting allows you to manage the period of inactivity before dimming the device. If you don't configure this setting, the inactivity timeout is 30 seconds.|
| TelemetryEnabled | Default: 01 <br>Options 01, 00 <br> Type: REG_BINARY  | This setting allows you to manage the sharing of app usage information to improve software and provide a better user experience. To disable, set the value to 00. If you don't configure this setting, telemetry information is shared with Microsoft per the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement). |

### Version history

- v1.20.139.0, released October 4, 2023. Included in [Surface IT Toolkit Library](surface-it-toolkit-library.md), April 25, 2024. 

## Learn more

- [Battery limit setting](battery-limit.md)
- [Surface IT Toolkit Library](surface-it-toolkit-library.md)