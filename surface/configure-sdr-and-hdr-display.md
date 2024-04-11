---
title: Configure SDR & HDR display measurements on Surface devices
description: This article provides a technical reference for SDR and HDR settings on Surface devices.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 4/11/2024
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 11
---

# Set up Surface devices for SDR & HDR display measurements

This guide provides a technical reference for configuring eligible Surface devices for accurate display measurements in both Standard Dynamic Range (SDR) and High Dynamic Range (HDR) modes. With the introduction of new display modes and features in the Windows 11 operating system, understanding and implementing the correct settings is necessary to ensure that the display output matches expectations.

For broader context on how Windows handles HDR and SDR, including processing features, see the following blog post: [High Dynamic Range in Surface displays](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/high-dynamic-range-in-surface-displays/ba-p/4100353).  

We recommend beginning with baseline measurements while keeping most processing features turned off. This method makes it easier to assess the impact of different features by turning them on one at a time or in various combinations. It's also important to note that Windows frequently relies on applications for managing content color, so choosing the right application to display content is crucial.

## SDR and HDR mode settings in Windows 11 23H2

To accurately measure SDR and HDR output on the Surface Laptop Studio 2, use the following settings. These instructions are applicable if you're running Windows 11 version 22631.3085 or later, which enables correct reporting of Peak Brightness and HDR Certification in the **System** > **Display** > **Advanced Display** > **Display information** page.

## Technical reference for display settings

### Display setting adjustments

#### General settings

| Setting                              | SDR Mode                                                                      | HDR Mode                                                                                                       |
|--------------------------------------|-------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Brightness Slider                    | Set to 100%                                                                   | Adjust using both the "Brightness" slider and the "HDR content brightness slider" within the HDR Menu. For more information, see the [HDR content brightness setting](#hdr-settings-system--display--hdr-settings-page) section on this page. |
| **Brightness Slider Dropdown Settings** | | |
| Auto Brightness                      | Under the brightness slider dropdown, uncheck the setting for: **Change brightness automatically when lighting changes**             | Same as SDR Mode: Disable Auto Brightness.                                                                                    |
| Content-Based Brightness             | Off                                                                           | Off                                                                                                           |
| Night Light                          | Off                                                                           | Off                                                                                                           |
| Color Profile                        | Set to Vivid                                                                  | Set to HDR                                                                                                    |
| Adaptive Color                       | Off                                                                           | Off                                                                                                           |
| Use HDR                              | Off                                                                           | On                                                                                                            |

#### HDR settings (System > Display > HDR settings page)

| Setting               | SDR Mode | HDR Mode                                                                                                                                                                     |
|-----------------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| HDR Content Brightness | Not Applicable | Adjust according to the brightness slider value. For Surface Laptop Studio 2: Set "Brightness Slider" to 46 and "HDR Content Brightness Slider" to 1 for accurate measurement. |

### Advanced configuration tips for SDR and HDR accuracy

- **SDR Mode:**
  - For sRGB accuracy, use the settings listed earlier but switch the color profile to sRGB.
  - For measuring SDR luminance dynamic range, adjust the brightness slider from 0 to 100.
  - For ACM (Advanced Color Management) mode accuracy, enable "Automatically manage color for apps" under System->Display->Advanced Display settings.

- **HDR Mode:**
  - Brightness slider values are device-specific. Use the [VESA DisplayHDR Test app](https://www.microsoft.com/store/productid/9NN1GPN70NF3?ocid=pdpshare) to observe the "Current Brightness Slider Factor," aiming for a value close to 1.0. This app also provides "Reported Panel Characteristics" for detailed analysis.

## Presenting SDR and HDR content

- **sRGB (SDR) content (with HDR disabled or enabled):** Use Paint for presenting red, green, blue, and white targets as in SDR mode. Windows OS color management automatically handles SDR content transformations to ensure accurate sRGB output when HDR is enabled.
- **ACM content accuracy:** Utilize applications, such as [Microsoft Photos](https://www.microsoft.com/store/productId/9WZDNCRFJBH4?ocid=pdpshare), which uses Advanced Color APIs for proper color management and correct tone mapping based on display and content color profiles.
- **HDR content accuracy:** For presenting 10% and 100% red, green, blue, and white targets, use the VESA DisplayHDR Test app's test cases 6. This application considers the display's reported characteristics to render accurate PQ RGB values. Restart the DisplayHDR app after any display settings changes before taking measurements.

## Surface Laptop Studio 2 measurement examples

See the following gamut and luminance accuracy data measurements taken after following the guidance explained in this article.

:::image type="content" source="images/gamut-luminance-measurement-examples.png" alt-text="Screenshot of measurements for gamut and luminance accuracy data.":::

## Learn more

- [High Dynamic Range in Surface displays](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/high-dynamic-range-in-surface-displays/ba-p/4100353)
- [Display Requirements for HDR Video](https://support.microsoft.com/windows/display-requirements-for-hdr-video-in-windows-192f362e-1245-e14d-3d3f-4b3fc606b80f)
