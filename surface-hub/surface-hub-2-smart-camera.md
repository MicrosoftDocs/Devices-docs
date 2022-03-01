---
title: "Install and manage Surface Hub 2 Smart Camera"
description: "Explains how to install and manage settings for the Surface Hub 2 Smart Camera."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/16/2022
ms.localizationpriority: Medium
---

# Install and Manage Surface Hub 2 Smart Camera

Surface Hub 2 Smart Camera <sup>1</sup> is designed for hybrid teams and optimized for remote participants. With sharp focus on the foreground and background, remote participants can see people interact with content on the Surface Hub while also viewing everyone else in the room. Surface Hub 2 Smart Camera has a wide field of view greater than 130 degrees, digital pan-tilt-zoom, high-quality glass optics, and a low light sensor.

## Install smart camera

1. Attach the camera to the USB-C port in the middle of the top of Surface Hub 2. The indicator LED will light briefly when the camera is connected and continuously when the camera is in use.

     ![Attach the camera to the USB-C port in the middle of the top of Surface Hub 2.](images/hub2smartcamera1.png)

2. To remove the camera, pull up and forward. A magnetic tether prevents the camera from being knocked off or pulled  backward.

    ![To remove the camera, pull up and forward.](images/hub2smartcamera2.png)

3. Attach the lens cover to the back of the camera when not in use.

## Auto-framing

AI-powered Surface Hub 2 Smart Camera dynamically adjusts the video feed, re-framing the view when someone leaves, more people come in, or a person interacts with content on the display.

### Manage auto-framing settings

When you install the Surface Hub Smart Camera, auto-framing is enabled by default for every Surface Hub session or when the camera is connected.

**To adjust auto-framing:**

1. On your Surface Hub 2S, sign in as **Admin**.

> [!NOTE]
> If you don't know your user name or admin password, you'll need to reset the device. For more information, see [Reset and recovery for Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset).

2. Open the **Settings** app and go to  **Surface Hub > Calling & Audio.**
3. Under **Automatic Framing**, adjust the toggle, as appropriate:

- **Set the Surface Hub 2 Smart Camera to automatically zoom and keep people centered in the video when they move around.**

4. Restart Surface Hub. 

If the toggle is set to **On**, auto-framing will always be on by default when users begin a session on Surface Hub. If the toggle is set to **Off**, auto-framing will always be off by default when starting a session on Surface Hub.

## Manage camera settings via an MDM provider

You can manage auto-framing via the [Surface Hub configuration service provider](/windows/client-management/mdm/surfacehub-csp) (CSP) from Intune or a third-party mobile device management (MDM) provider. To learn more, refer to the following:

- [Manage settings with an MDM provider](/surface-hub/manage-settings-with-mdm-for-surface-hub#create-custom-configuration-profile)
- [SurfaceHub CSP - Windows Client Management](/windows/client-management/mdm/surfacehub-csp)

## Windows 11 Desktop on Surface Hub

If you have [migrated your Surface Hub](surface-hub-2s-migrate-os.md) to run Windows 11 Pro or Windows 11 Enterprise, you'll need to turn on auto-framing for the Surface Hub Smart Camera. By default, auto-framing is turned off.

- To turn on auto-framing, go to **Settings > Bluetooth & devices > Manage Cameras>  Surface Hub 2 Smart Camera.**

## Windows 10 Desktop on Surface Hub

Auto-framing is always enabled and cannot be disabled or otherwise configured.

## Order Surface Hub 2 Smart Camera

Purchase Surface Hub 2 Smart Camera from your [authorized Microsoft Surface reseller](https://www.microsoft.com/surface/business/where-to-buy-microsoft-surface?).

## Learn more

- 

### References

1. Surface Hub 2 Smart Camera, sold separately starting March 16, 2022, dynamically adjusts the video feed for remote participants. Surface Hub 2 Smart Camera will be included in the box with Surface Hub 2S 85” starting in May 2022.
