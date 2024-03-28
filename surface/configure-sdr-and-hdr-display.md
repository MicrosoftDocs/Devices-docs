---
title: Configure SDR & HDR display measurements on Surface devices
description: This article provides a technical reference for SDR and HDR settings on Surface devices
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 3/28/2024
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 11
---

# Configure SDR & HDR display measurements on Surface devices

## Introduction

This guide provides a technical reference for configuring eligible Surface devices for accurate display measurements in both Standard Dynamic Range (SDR) and High Dynamic Range (HDR) modes. With the introduction of new display modes and features in the Windows 11 operating system, understanding and implementing the correct settings is necessary to ensure that the display output matches expectations.

For broader context on how Windows handles HDR and SDR, including processing features, refer to the following blog post: High Dynamic Range in Surface displays.  

It's recommended to start baseline measurements with most processing features disabled. This approach allows for the evaluation of the impact of various features by activating them individually or in combination. Since Windows often depends on applications for content color management, the choice of application for displaying content is also critical.

## SDR and HDR Mode Settings in Windows 11 Version 23H2

To accurately measure SDR and HDR output on the Surface Laptop Studio 2, utilize the following settings. These instructions are applicable if you are running Windows 11 version 22631.3085 or later, which enables correct reporting of Peak Brightness and HDR Certification in the **System** > **Display** > **Advanced Display Settings System** > **Display settings** page.


## Technical reference for Display settings

### Display setting adjustments

#### General settings

| Setting                              | SDR Mode                                                                      | HDR Mode                                                                                                       |
|--------------------------------------|-------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Brightness Slider                    | Set to 100%                                                                   | Adjust using both the "Brightness" slider and the "HDR content brightness slider" within the HDR Menu. Refer to the "HDR content brightness setting" section for more details. |
| **Brightness Slider Dropdown Settings** | | |
| Auto Brightness                      | Disable "Change brightness automatically when lighting changes".             | Same as SDR Mode: Disabled.                                                                                    |
| Content-Based Brightness             | Off                                                                           | Off                                                                                                           |
| Night Light                          | Off                                                                           | Off                                                                                                           |
| Color Profile                        | Set to Vivid                                                                  | Set to HDR                                                                                                    |
| Adaptive Color                       | Off                                                                           | Off                                                                                                           |
| Use HDR                              | Off                                                                           | On                                                                                                            |

#### HDR Settings (System > Display > HDR settings page)

| Setting               | SDR Mode | HDR Mode                                                                                                                                                                     |
|-----------------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| HDR Content Brightness | Not Applicable | Adjust according to the brightness slider value. For Surface Laptop Studio 2: Set "Brightness Slider" to 46 and "HDR Content Brightness Slider" to 1 for accurate measurement. |

### Advanced configuration tips for SDR and HDR accuracy

- **SDR Mode:**
  - For sRGB accuracy, use the settings above but switch the color profile to sRGB.
  - For measuring SDR luminance dynamic range, adjust the brightness slider from 0 to 100.
  - For ACM (Advanced Color Management) mode accuracy, enable "Automatically manage color for apps" under System->Display->Advanced Display settings.

- **HDR Mode:**
  - Brightness slider values are device-specific. Use the [VESA DisplayHDR Test app](https://www.microsoft.com/store/productid/9NN1GPN70NF3?ocid=pdpshare) to observe the "Current Brightness Slider Factor," aiming for a value close to 1.0. This app also provides "Reported Panel Characteristics" for detailed analysis.

## Presenting SDR and HDR content

- **sRGB (SDR) Content (With HDR Disabled or Enabled):** Use Paint for presenting red, green, blue, and white targets as in SDR mode. Windows OS color management will automatically handle SDR content transformations to ensure accurate sRGB output when HDR is enabled.
- **ACM Content Accuracy:** Utilize applications with advanced color management, such as [Microsoft Photos](https://www.microsoft.com/store/productId/9WZDNCRFJBH4?ocid=pdpshare), which uses Advanced Color APIs for correct tone mapping.
- **HDR Content Accuracy:** For presenting 10% and 100% red, green, blue, and white targets, use the VESA DisplayHDR Test app's test cases 6. This application considers the display's reported characteristics to render accurate PQ RGB values. Restart the DisplayHDR app after any display settings changes before taking measurements.

## Surface Laptop Studio 2 measurement examples

The following gamut and luminance accuracy data have been measured after following the guidance explained in this article.

:::image type="content" source="images/gamut-luminance-measurement-examples.png" alt-text="Screenshot of measurements for gamut and luminance accuracy data.":::


## Helpful Links

- [Display Requirements for HDR Video](https://support.microsoft.com/en-us/windows/display-requirements-for-hdr-video-in-windows-192f362e-1245-e14d-3d3f-4b3fc606b80f)

