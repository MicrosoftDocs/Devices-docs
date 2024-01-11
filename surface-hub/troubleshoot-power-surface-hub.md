---
title: Troubleshoot Surface Hub power issues
description: This page explains how to troubleshoot power issues on Surface Hub. 
ms.reviewer: 
manager: frankbu
keywords: troubleshoot Surface Hub power
ms.service: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: troubleshooting
ms.date: 12/06/2023
ms.localizationpriority: medium
appliesto:
- Surface Hub 2S
- Surface Hub 3
---

# Troubleshoot Surface Hub power issues

If you encounter an issue powering on your Surface Hub 2S or Surface Hub 3, review the troubleshooting steps outlined on this page.

1. First, remove all connections to the Surface Hub except for Ethernet and power.
2. Ensure Surface Hub has a direct connection to a dedicated power outlet.
3. Do you have an [APC Charge Mobile Battery](https://www.apc.com/us/en/campaign/apc-charge-mobile-battery-for-microsoft-surface-hub-2.jsp) connected to Surface Hub? If yes, disconnect the battery and try again. If the power-on issue only occurs when using the APC battery, please contact [APC support](https://www.apc.com/us/en/support/contact-us/) for further assistance.
4. Test with another power cord (see [Label 2](#port-and-keypad-component-reference) in Figure 1 below) and a different power outlet.
5. Initiate a hardware reset on Surface Hub: Hold and press the power button (see [Label 11](#port-and-keypad-component-reference) in Figure 1 below) for at least 20 seconds.
6. If you’re still unable to power on the device, try [reseating the compute cartridge](/surface-hub/surface-hub-2s-pack-components#how-to-replace-and-pack-your-surface-hub-2s-compute-cartridge).

## Support requests

If your Surface Hub still fails to power on after trying these troubleshooting steps, please [create a support request](https://support.serviceshub.microsoft.com/supportforbusiness/onboarding) and include the following details:

- Results of your troubleshooting steps.
- Is the backlight visible on the device?
- Can you use the Source button on the keypad to select other sources? (To locate the Source button, see [Label 9](#port-and-keypad-component-reference) in Figure 1 below). Are the sources visible on the screen?
- If you try to connect an external device (via HDMI, for example), does the Hub display the external content?
- If you [Miracast to the Surface Hub](surface-hub-2s-connect.md) from a projecting device, does the Surface Hub appear as an available connection, as shown below?

    :::image type="content" source="images/hub-project.png" alt-text="Screenshot that shows the how Check Surface Hub appears as an available connection when projecting." :::

- Date of Surface Hub delivery and discovery of the unresponsive unit.
- The serial number of the Surface Hub.

> [!TIP]
> The serial number is printed on Surface Hub 2S and Surface Hub 3 near the power cord, as shown below.

:::image type="content" source="images/hub-serial-number.png" alt-text="Screenshot that shows how to find the serial number printed on Surface Hub 2S and Surface Hub 3 near the power cord." :::

## Port and keypad component reference

 ![Front facing and underside view of I/O connections and physical buttons.](images/hub2s-schematic.png)
*Figure 1. Ports and physical buttons on Surface Hub 2S*

|**Key**|**Component**|**Description**|**Key parameters**|
|:--- |:--------- |:----------- |:-------------- |
| 1 | **USB C** | **USB 3.1 Gen 1** <br> Use as a walk-up port for plugging in peripherals such as thumb-drives. Guest ports are on each side of the device (4).<br> <br> *NOTE: This is the recommended port for connecting an external camera. Additional camera mount features are incorporated into the design to help support retention of attached cameras.*<br> <br> NOTE: TouchBack and video ingest are not supported on these ports. | Type C <br> <br> 15 W Port (5V/3A)       |
| 2 | **AC power** | **100-240 V input** <br> Connect to standard AC power and Surface Hub will auto switch to the local power standard such as110 volts in the US and Canada or 220 volts in the UK. | IEC 60320 C14 |
| 3 | **DC power** | **24V DC input port** <br> Use for connecting to mobile battery. | Xbox1 Dual barrel to Anderson connector |
| 4 | **Ethernet** | **1000/100/10 Base-T** <br> Use for providing a continuous connection in a corporate environment and related scenarios requiring maximum stability or capacity. | RJ45 |
| 5 | **USB-A** | **USB 3.1 Gen 1** <br> Use as a walk-up port for plugging in peripherals such as thumb-drives. | Type A<br>7.5 W Port (5V/1.5A) |
| 6 | **USB-C** | **USB 3.1 Gen 1** <br> Use as a walk-up port for connecting external PCs and related devices or plugging in peripherals such as thumb-drives.<br> <br> *NOTE: This is the recommended  input port for video, TouchBack, and InkBack.* | Type C <br> 18 W Port (5V/3A, 9V/2A) |
| 7 | **HDMI-in** | **HDMI 2.0, HDCP 2.2 /1.4** <br> Use for multiple scenarios including HDMI-to-HDMI guest input. | Standard HDMI |
| 8 | **Mini DP-out** | **Mini DP 1.2 output** <br> Use for video-out scenarios such as mirroring the Surface Hub 2S display to a larger projector.<br> <br> *NOTE: This supports a maximum resolution of 3840 x 2160 (4K UHD) @60Hz.* | Mini DP |
| 9 | **Source**  | Use to toggle among connected ingest sources — external PC, HDMI, and Mini DP modes. | n/a |
| 10 | **Volume** | Use +/- to adjust audio locally on the device. <br> <br> *NOTE: When navigating to the brightness control, use +/- on the volume slider to control display brightness.* | n/a |
| 11 | **Power** | Power device on/off. <br> Use also to navigate display menus and select items. | n/a |
