---
title: "Connect devices to Surface Hub 2S"
description: "This page explains how to connect external devices to Surface Hub 2S."
ms.prod: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: how-to
ms.date: 02/24/2020
ms.localizationpriority: Medium
---

# Connect devices to Surface Hub 2S

Surface Hub 2S enables you to connect external devices, mirror the display on Surface Hub 2S to another device, and connect multiple third-party peripherals including video conference cameras, conference phones, and room system devices.

You can display content from your devices to Surface Hub 2S. If the source device is Windows-based, that device can also provide [TouchBack and InkBack](#control-your-laptop-from-the-surface-hub), which takes video and audio from the connected device and presents them on Surface Hub 2S. If Surface Hub 2S encounters a High-Bandwidth Digital Content Protection (HDCP) signal, such as a Blu-ray DVD player, the source is displayed as a black image.

> [!NOTE]
> Surface Hub 2S uses the video input selected until a new connection is made, the existing connection is disrupted, or the Connect app is closed.

## Project using cables to Surface Hub 2S

To project your screen with cables, connect using the ports along the bottom edge of the compute cartridge. The compute cartridge has an HDMI port, a USB-C port, USB-A, as well as the Ethernet port and DisplayPort.

You can project in with USB-C or HDMI—the DisplayPort is only for mirroring your Surface Hub’s screen on another screen.

:::image type="content" source="images/computer-cartridge-ports.png" alt-text="Screenshot of the compute cartridge that has an HDMI port, a USB-C port, USB-A, as well as the Ethernet port and DisplayPort.":::

### Recommended wired configurations 

In general, it’s recommended to use native cable connections whenever possible such as USB-C to USB-C or HDMI to HDMI. Other combinations such as MiniDP to HDMI or MiniDP to USB-C will also work. Some additional configuration may be required to optimize the video-out experience, as described on this page.

| **Connection** | **Functionality** | **Description**|
| --- | --- | ---|
| HDMI + USB-C | HDMI-in for audio and video<br><br>USB-C for TouchBack and InkBack | USB-C supports TouchBack and InkBack with the HDMI A/V connection.<br><br>Use USB-C to USB-A to connect to legacy computers.<br><br>**NOTE:** For best results, connect HDMI before connecting a USB-C cable. If the computer you're using for HDMI is not compatible with TouchBack and InkBack, you won't need a USB-C cable. |
| USB-C <br> (via compute module) | Video-in <br>Audio-in | Single cable needed for A/V<br><br>TouchBack and InkBack is supported<br><br>HDCP enabled |
| HDMI (in port) | Video, Audio into Surface Hub 2S | Single cable needed for A/V<br><br>TouchBack and InkBack not supported<br><br>HDCP enabled |
| MiniDP 1.2 output | Video-out such as mirroring to a larger projector. | Single cable needed for A/V |

When you connect a guest computer to Surface Hub 2S via the USB-C port, several USB devices are discovered and configured. These peripheral devices are created for TouchBack and InkBack. As shown in the following table, the peripheral devices can be viewed in Device Manager, which will show duplicate names for some devices, as shown in the following table.

 
|Peripheral| Listing in Device Manager |
| ---------------------------- |------------- | 
| Human interface devices | HID-compliant consumer control device<br>HID-compliant pen<br>HID-compliant pen (duplicate item)<br>HID-compliant pen (duplicate item)<br>HID-compliant touch screen<br>USB Input Device<br>USB Input Device (duplicate item) |
| Keyboards | Standard PS/2 keyboard |
| Mice and other pointing devices | HID-compliant mouse |
| USB controllers | Generic USB hub<br>USB composite device |

## Connect video-in to Surface Hub 2S

You can input video to Surface Hub 2S using USB-C or HDMI, as indicated in the following table.  

### Surface Hub 2S video-in settings

| **Signal Type** | **Resolution** | **Frame rate** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| PC              | 640 x 480      | 60             | X        | X         |
| PC              | 720 x 480      | 60             | X        | X         |
| PC              | 1024 x 768     | 60             | X        | X         |
| PC              | 1920 x 1080    | 60             | X        | X         |
| PC              | 3840x2560      | 30             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 30             | X        | X         |

> [!NOTE]
> The 4K UHD resolution (3840×2560) is only supported when connecting to ports on the compute module. It is not supported on the “guest” USB ports located on the left, top, and right sides of the device.

> [!NOTE]
> Video from a connected external PC may appear smaller when displayed on Surface Hub 2S.

## Mirror Surface Hub 2S display on another device

You can output video to another display using MiniDP, as indicated in the following table.

### Surface Hub 2S video-out settings

| **Signal Type** | **Resolution** | **Frame rate** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| PC              | 640 x 480      | 60             | X          |
| PC              | 720 x 480      | 60             | X          |
| PC              | 1024 x 768     | 60             | X          |
| PC              | 1920 x 1080    | 60             | X          |
| PC              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4K UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 2S includes a MiniDP video-out port for projecting visual content from Surface Hub 2S to another display. If you plan to use Surface Hub 2S to project to another display, note the following recommendations:

- **Keyboard required.** Before you begin, you’ll need to connect either a wired or Bluetooth-enabled external keyboard  to Surface Hub 2S. Note that unlike the original Surface Hub, a keyboard for Surface Hub 2S is sold separately and is not included in the shipping package.<br><br>
- **Set duplicate mode.** Surface Hub 2S supports video-out in duplicate mode only. However, you will still need to manually configure the display mode when you connect for the first time:
    1. Enter the **Windows logo key** + **P**, which opens the Project pane on the right side of Surface Hub 2S, and then select **Duplicate** mode.
    2. When you’re finished with your Surface Hub 2S session, select **End Session**. This ensures that the duplicate setting is saved for the next session.<br><br>
- **Plan for different aspect ratios.** Like other Surface devices, Surface Hub 2S uses a 3:2 display aspect ratio (the relationship between the width and the height of the display). Projecting Surface Hub 2S onto displays with different aspect ratios is supported. Note however that because Surface Hub 2S duplicates the display, the MiniDP output will also only display in a 3:2 aspect ratio, which may result in letterboxing or curtaining depending on the aspect ratio of the receiving display. 

> [!NOTE]
> if your second monitor uses a 16:9 aspect ratio (the predominant ratio for most TV monitors), black bars may appear on the left and right sides of the mirrored display. If this occurs, you may wish to inform your users that there is no need to adjust the second display.

## Select cables

Note the following recommendations:

- **USB.** USB 3.1 Gen 2 cables.
- **MiniDP.** DisplayPort cables certified for up to 3 meters in length.
- **HDMI.** If a long cable is necessary, HDMI is recommended due to the wide availability of cost-effective, long-haul cables with the ability to install repeaters if needed.

> [!TIP]
> Most DisplayPort sources will automatically switch to HDMI signaling if HDMI is detected.

## Wirelessly connect to Surface Hub 2S

Windows 10/11 natively supports Miracast, which lets you wireless connect to Surface Hub 2S.<br><br>

### To connect using Miracast:

1. On your Windows 10/11 device, enter **Windows logo key** + **K**. 
2. In the Connect window, look for the name of your Surface Hub 2S in the list of nearby devices. You can find the name of your Surface Hub 2S in the bottom left corner of the display or when you press **Connect** on the welcome screen.

:::image type="content" source="images/surface-hub-ready-connect-wirelessly.png" alt-text="Screenshot of a welcome screen shows that Surface Hub is ready for you to connect wirelessly.":::

3. Enter a PIN if your system administrator has enabled the PIN setting for Miracast connections. This requires you to enter a PIN number when you connect to Surface Hub 2S for the first time.

> [!NOTE]
>If you do not see the name of the Surface Hub 2S device as expected, it’s possible the previous session was prematurely closed. If so, sign into Surface Hub 2S directly to end the previous session and then connect from your external device.

### Control your laptop from the Surface Hub

Sometimes when you’re presenting or collaborating on Surface Hub, you’ll want to be able to leave your laptop at your seat and be able to fully pay attention to what's on the big screen.

When you've connected a device that has Windows 8 or later to Surface Hub, on that device, you’ll see a checkbox to **Allow mouse, keyboard, touch, and pen input**.

:::image type="content" source="images/checkbox-allow-mouse-keyboard-touch-pen-input.png" alt-text="Screenshot of a checkbox to allow mouse, keyboard, touch, and pen input.":::

When this is checked, you’ll be able to use touch and inking on the Surface Hub to control and make changes on your own connected device. If you’re connecting via USB-C, you’ll be able to use the touch and inking to make changes on your device automatically. However, if you’re connecting with HDMI, you’ll need to connect a USB cable as well to use touch and pen input on your device.

## Connect peripherals to Surface Hub 2S

### Bluetooth accessories

You can connect the following accessories to Surface Hub-2S using Bluetooth:

- Mice
- Keyboards
- Headsets
- Speakers
- Surface Hub 2 pens

> [!TIP]
> After you connect a Bluetooth headset or speaker, you might need to change the default microphone and speaker settings. For more information, see [Local management for Surface Hub settings](local-management-surface-hub-settings.md).
