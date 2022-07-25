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

Surface Hub 2 Smart Camera<sup>1</sup> is designed for hybrid teams and optimized for remote participants. With a sharp focus on the foreground and background, remote participants can see people interact with content on the Surface Hub while also viewing everyone else in the room. Surface Hub 2 Smart Camera has a wide field of view greater than 136 degrees, automatic framing, high-quality glass optics, and a low light sensor.
![Ultra-wide camera view includes people whiteboarding on extreme edges of 85" Hub](images/surface-hub-2-smart-camera-fov.png)

*Ultra-wide camera view includes people whiteboarding on extreme edges of 85" Hub*

## System requirements

For Surface Hubs running Team OS, Surface Hub 2 Smart Camera requires the following updates for the [Windows 10 Team 2020 update](surface-hub-2020-update-whats-new.md) (20H2) on Surface Hub 2:

- Windows 10 Team 2020 Update 2 (KB5010415 or a subsequent Windows update)
- System Hardware Update-January 21, 2022 (or a subsequent System Hardware Update)

To learn more, refer to [Surface Hub update history](surface-hub-update-history.md).

> [!NOTE]
> No additional updates are required for Surface Hubs  migrated to run Windows 10/11 Pro or Enterprise.

## Install smart camera

1. Attach the camera to the USB-C port in the middle of the top of Surface Hub 2. The indicator LED will light briefly when the camera is connected and continuously when the camera is in use.

     ![Attach the camera to the USB-C port in the middle of the top of Surface Hub 2.](images/hub2smartcamera1.png)

2. To remove the camera, pull up and forward. A magnetic tether prevents the camera from being knocked off or pulled  backward.

    ![To remove the camera, pull up and forward.](images/hub2smartcamera2.png)

### Camera cover

The camera cover magnetically snaps to the front for privacy and the back for storage when not in use.

:::image type="content" source="images/smart-camera-cover.png" alt-text="Remove the cover and place it on rear of the camera " :::

> [!NOTE]
> Do not place the cover in the vented slot at the top of the camera.


## Manage automatic framing settings

Automatic framing dynamically zooms and keeps you centered in the video when you move around. How you manage the settings depends on the OS installed on Surface Hub:

- [Windows 10 Team 2020 update (20H2)](#windows-10-team-2020-update-20h2)
- [Windows 11 Desktop on Surface Hub](#windows-11-desktop-on-surface-hub)
- [Windows 10 Desktop on Surface Hub](#windows-10-desktop-on-surface-hub)

### Windows 10 Team 2020 update (20H2)

When you install the Surface Hub Smart Camera, automatic framing is enabled by default. Admins can manage automatic framing from Settings via an On/Off toggle that sets the automatic framing state at the start of each Surface Hub session.

**To adjust automatic framing:**

1. On your Surface Hub 2S, sign in as **Admin**.

> [!NOTE]
> If you don't know your user name or admin password, you'll need to reset the device. For more information, see [Reset and recovery for Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset).

2. Open **Settings** and go to  **Surface Hub > Calling & Audio.**
3. Under **Automatic framing**, adjust the toggle as appropriate. 
4. Select **End session**; modified settings are applied when you start a new session. 

If the toggle is set to **On**, automatic framing will always be on by default when users begin a session on Surface Hub. If the toggle is set to **Off**, automatic framing will always be off by default when starting a session on Surface Hub.

#### Manage camera settings via an MDM provider

Admins can manage automatic framing via the [Surface Hub configuration service provider](/windows/client-management/mdm/surfacehub-csp) (CSP) from Intune or a third-party mobile device management (MDM) provider.

|CSP policy setting| Description|
|------------------|------------|
|DefaultAutomaticFraming|If you turn on this policy setting, automatic framing is enabled. If you turn off this policy setting, automatic framing is disabled. If you don't configure this policy setting, automatic framing is enabled. |

To learn more, refer to the following pages:

- [Manage settings with an MDM provider](/surface-hub/manage-settings-with-mdm-for-surface-hub#create-custom-configuration-profile)
- [SurfaceHub CSP - Windows Client Management](/windows/client-management/mdm/surfacehub-csp)

### Windows 11 Desktop on Surface Hub

If you've [migrated your Surface Hub](surface-hub-2s-migrate-os.md) to run Windows 11 Pro or Windows 11 Enterprise, you'll need to turn on automatic framing for the Surface Hub Smart Camera. By default, automatic framing is turned off.

To turn on automatic framing, go to **Settings > Bluetooth & devices > Manage Cameras>  Surface Hub 2 Smart Camera.**

### Windows 10 Desktop on Surface Hub

Automatic framing is always enabled and can't be disabled or otherwise configured.

### Order Surface Hub 2 Smart Camera

Purchase Surface Hub 2 Smart Camera from your [authorized Microsoft Surface reseller](https://www.microsoft.com/surface/business/where-to-buy-microsoft-surface?).

### Learn more

-[Video: The new Surface Hub 2 Smart Camera](https://youtu.be/sgv_TeT8RB8)

### References

<sup>1</sup> Surface Hub 2 Smart Camera, sold separately starting March 16, 2022, dynamically adjusts the video feed for remote participants. Surface Hub 2 Smart Camera will be included in the box with Surface Hub 2S 85” starting in May 2022.
