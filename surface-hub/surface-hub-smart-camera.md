---
title: "Install and manage Surface Hub Smart Camera"
description: "Explains how to install and manage settings for the Surface Hub Smart Camera."
ms.service: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: how-to
ms.date: 01/30/2024
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S
- Surface Hub 3
---
# Install and manage Surface Hub Smart Camera

Surface Hub Smart Camera<sup>1</sup> is designed for hybrid teams and optimized for remote participants. With a sharp focus on the foreground and background, remote participants can see people interact with content on the Surface Hub while viewing everyone else in the room. Surface Hub Smart Camera has a wide field of view greater than 136 degrees, automatic framing<sup>2</sup>, high-quality glass optics, and a low light sensor. To learn more, see the following resources: 

- [Surface Hub Smart Camera tech specs](surface-hub-smart-camera-tech-specs.md)
- [Video demo](https://youtu.be/sgv_TeT8RB8)

![Screenshot that shows ultra-wide camera view including people whiteboarding on extreme edges of 85" Hub.](images/surface-hub-smart-camera-fov.png)

*Ultra-wide camera view includes people whiteboarding on extreme edges of 85" Hub*

## System requirements

Surface Hub Smart Camera requires the following updates for the [Windows 10 Team 2020 update](surface-hub-2020-update-whats-new.md) (20H2) on Surface Hub 2S:

- Windows 10 Team 2020 Update 2 (KB5010415 or a subsequent Windows update)
- System Hardware Update-January 21, 2022 (or a subsequent System Hardware Update)

To learn more, refer to [Surface Hub update history](surface-hub-update-history.md).

> [!NOTE]
> No additional updates are required for Surface Hubs migrated to run Windows 10/11 Pro or Enterprise.

## Install smart camera

1. Attach the camera to the USB-C port in the middle of the top of Surface Hub 2S. The indicator LED lights briefly when the camera is connected and continuously when the camera is in use.

     ![Screenshot that shows how to attach the camera to the USB-C port in the middle of the top of Surface Hub 2S.](images/hub2smartcamera1.png)

2. To remove the camera, pull up and forward. A magnetic tether prevents the camera from being knocked off or pulled backward.

    ![Screenshot that shows how to remove the camera, pull up and forward.](images/hub2smartcamera2.png)

### Camera cover

The camera cover magnetically snaps to the front for privacy and the back for storage when not in use.

:::image type= "content" source= "images/smart-camera-cover.png" alt-text= "Screenshot that shows how to remove the cover and place it on rear of the camera." :::

> [!NOTE]
> Do not place the cover in the vented slot at the top of the camera.

## Manage automatic framing settings

Automatic framing<sup>2</sup> dynamically adjusts the camera's focus and framing during video calls. This technology ensures that participants are centered and visible in the frame, even as they move around the room.

How you manage the settings depends on the OS installed on Surface Hub:

- [Windows 10 Team 2022 update (22H2)](#windows-10-team-2022-update-22h2)
- [Windows 11 Desktop on Surface Hub](#windows-11-desktop-on-surface-hub)
- [Windows 10 Desktop on Surface Hub](#windows-10-desktop-on-surface-hub)

### Windows 10 Team 2022 update (22H2)

When you install the Surface Hub Smart Camera, automatic framing is enabled by default. Admins can manage automatic framing from Settings via an On/Off toggle that sets the automatic framing state at the start of each Surface Hub session.

**To adjust automatic framing:**

1. On your Surface Hub 2S, sign in as **Admin**.

> [!NOTE]
> You'll need to reset the device if you don't know your username or admin password. For more information, see [Reset and recovery for Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset).

2. Open **Settings** and go to  **Surface Hub > Calling & Audio.**
3. Under **Automatic framing**, adjust the toggle as appropriate.
4. Select **End session**; modified settings are applied when you start a new session.

If the toggle is set to **On**, automatic framing is always on by default when users begin a session on Surface Hub. If the toggle is set to **Off**, automatic framing is always off by default when starting a session on Surface Hub.

#### Manage camera settings via an MDM provider

Admins can manage automatic framing via the [Surface Hub configuration service provider](/windows/client-management/mdm/surfacehub-csp) (CSP) from Intune or other mobile device management (MDM) provider.

|CSP policy setting| Description|
|------------------|------------|
|DefaultAutomaticFraming|If you turn on this policy setting, automatic framing is enabled. If you turn off this policy setting, automatic framing is disabled. If you don't configure this policy setting, automatic framing is enabled. |

To learn more, refer to the following pages:

- [Manage settings with an MDM provider](/surface-hub/manage-settings-with-mdm-for-surface-hub#create-custom-configuration-profile)
- [SurfaceHub CSP - Windows Client Management](/windows/client-management/mdm/surfacehub-csp)

### Windows 11 Desktop on Surface Hub

If you [migrated your Surface Hub](surface-hub-2s-migrate-os.md) to run Windows 11 Pro or Windows 11 Enterprise, you need to turn on automatic framing for the Surface Hub Smart Camera. Automatic framing is turned off by default.

To turn on automatic framing, go to **Settings > Bluetooth & devices > Manage Cameras>  Surface Hub Smart Camera.**

### Windows 10 Desktop on Surface Hub

If you [migrated your Surface Hub](surface-hub-2s-migrate-os.md) to run Windows 10 Pro or Windows 10 Enterprise, automatic framing is always enabled and can't be disabled or otherwise configured.

### Get Surface Hub Smart Camera

Surface Hub Smart Camera is included in the box with the following models: Surface Hub 3 50", Surface Hub 3" 85", and Surface Hub 2S 85". Or 
you can [purchase Surface Hub Smart Camera separately](https://www.microsoft.com/d/surface-hub-smart-camera/8n983ctks176?activetab=pivot:techspecstab). 

### Learn more

- [Surface Hub Smart Camera tech specs](surface-hub-smart-camera-tech-specs.md)
- [Video demo](https://youtu.be/sgv_TeT8RB8)

### References

1.  Surface Hub Smart Camera dynamically adjusts the video feed for remote participants.<sup>2</sup> Surface Hub Smart Camera is available for purchase separately and included in the box with the following models: Surface Hub 3 50", Surface Hub 3" 85", and Surface Hub 2S 85". 

2. Automatic framing is available when running Windows 10 Team edition or Windows 10/11 Pro/Enterprise.

