---
title: Troubleshoot display projection to Surface Hub
description: Learn how to resolve issues connecting external devices to Surface Hub.
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 02/15/2023
ms.reviewer: dpandre
manager: frankbu
ms.localizationpriority: medium
---

# Troubleshoot display projection to Surface Hub

Surface Hub is designed to enable end users to project their display from laptops or other external devices wirelessly via Miracast or via wired (USB-C/HDMI) connections. Surface Hub listens for incoming wireless connections via Miracast when Wi-Fi is enabled. If your external device supports Miracast and runs Windows 10 or Windows 11, you should be able to wirelessly project your screen onto Surface Hub. If you cannot, try the troubleshooting steps on this page.

**To connect with Miracast:**

1. On your Windows 10/11 device, press **the Windows logo key + K**.
2. In the **Connect** window, look for the name of your Surface Hub in the list of nearby devices, as shown in the bottom left corner of the Surface Hub display.
3. Enter a PIN if your system administrator has enabled the PIN setting for Miracast connections. This requires you to enter a PIN when you connect to Surface Hub for the first time.

> [!TIP]
> If you don’t see the name of the Surface Hub device as expected, it's possible the previous session was prematurely closed. If so, sign in to Surface Hub directly to end the previous session and connect from your external device.

## Troubleshoot Miracast

**Table 1. Troubleshoot Miracast connections to Surface Hub**

| Action                                      | Where                              | Notes                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ------------------------------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Restart devices**                         | External device/Surface Hub | If Miracast has worked previously, restart your external device or restart your external device and Surface Hub to reset the connection.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Restart wireless display adapter**        | External device                  | 1. **Start >** **Settings >** Bluetooth **& devices** > **Devices**. Under **Wireless displays & docks**, select the wireless display or adapter.<br>2. Select **Remove device** > **Yes**. <br>3. Try reconnecting.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Check Wi-Fi is turned on**                | Surface Hub                      | - Open **Settings > View as Admin**. Select **Network & Internet** and make sure **Wi-Fi** is turned **On**.<br><br> <br>**Note**: Surface Hub doesn't need to be connected to a wireless network, but Wi-Fi must be enabled for Miracast to work.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Verify Miracast projection is turned on** | Surface Hub                      | 1. Open **Settings > View as Admin**. Select Surface Hub> Projection.<br>2. Make sure the following settings are turned on:<br>    - **Connect automatically when someone projects**<br>    - **Presenters can use Miracast to protect wirelessly to this device**<br><br> <br>**Note:** If a PIN is required, users must enter it when they connect an external device for the first time.                                                                                                                                                                                                                                                                                                                                                                               |
| **Verify Miracast support**                 | External device                  | 1. Press **Windows logo key** + **R** and type **dxdiag**.<br>2. Select **Save all information.**<br>3. Open the saved **dxdiag.txt** file and find **Miracast**. It should indicate **Available, with HDCP**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Check Miracast channel**                  | Surface Hub                      | If you run a network scan, you should see Surface Hub Miracast listed as an access point. If Surface Hub's Miracast network shows up on the scan, but you can't see it as an available device, you can try to adjust the Miracast channel used by Surface Hub.<br> <br>When Surface Hub is connected to a Wi-Fi network, it will use the same channel settings as the Wi-Fi access point for its Miracast access point. For troubleshooting purposes, disconnect Surface Hub from any Wi-Fi networks (but keep Wi-Fi enabled), so you can control the channel used for Miracast. You can manually select the Miracast channel in Settings. You will need to restart Surface Hub after each change. Use channels that do not show heavy utilization from the network scan. |
| **Check drivers**                           | External device                  | Ensure the device drivers on your external device are up to date and the latest firmware is installed for your wireless display or adapter. In **Device Manager**, select **Network Adapters**, open the Wi-Fi adapter and video adapter and check for an updated driver version.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Check firewall**                      | External device                  | The Windows firewall can block Miracast traffic. The most straightforward test is to disable the firewall and test projection. If Miracast works with the firewall disabled, add an exception for:<br><br>- C:\Windows\System32\WUDFHost.exe<br>- Allow In/Out connections for TCP and UDP, Ports: All.                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Check Group Policy settings**        | External device (domain joined)  | On domain-joined devices only, Group Policy can also block Miracast.<br><br>1. Press **Windows Key + R** and type **rsop.msc.** The **Resultant Set of Policy** snap-in shows the current policy settings applied to the PC.<br>2. Review **Computer Configuration** > **Windows Settings** > **Security Settings** > **Wireless Network (IEEE 802.11) Policies**. There should be a setting for wireless policies.<br>3. Double-click the setting for wireless policies, and a dialog box will appear.<br>4. Open the **Network Permissions** tab and select **Allow everyone to create all user profiles**.<br><br>                                                                                                                                                 |
| **Check Event logs**                  | External device/Surface Hub | The last place to check is in the Event logs. Miracast events will be logged to **Wlanautoconfig** on both Surface Hub and the external device. If you export Surface Hub logs, you can view Surface Hub's Wlanautoconfig in the **WindowsEventLog** folder. The event log errors can provide additional details on where the connection fails.<br>                                                                                                                                                                                                                                                                                                                                                                                                                   |

## Troubleshoot connection performance

After wireless projection is connected, it is possible to see performance issues causing latency. This is generally a result of overall channel saturation or a situation that causes channel switching.

For channel saturation, refer to the network scan and use channels with less traffic.

Channel switching is caused when the Wi-Fi adapter needs to send traffic to multiple channels. Specific channels support Dynamic Frequency Selection (DFS). DFS is used on channels 49 through 148. Some Wi-Fi drivers will show poor performance when connected to a DFS channel. If you see poor Miracast performance when connected to a DFS channel, try the projection on a non-DFS channel. Both Surface Hub and the external projecting device should use non-DFS channels.

If Surface Hub and the projecting device are connected to Wi-Fi but use different access points with different channels, forced channel switching degrades performance when Miracast is connected. The channel switching will affect the performance of all wireless traffic, not just wireless projection.

Channel switching will also occur if the projecting device is connected to a Wi-Fi network using a different channel than Surface Hub's channel for Miracast. So, a best practice is to set Surface Hub's Miracast channel to the same channel as the most commonly used access point. Some channel switching is unavoidable if there are multiple Wi-Fi networks or access points in the environment. In this scenario, ensure all Wi-Fi drivers are up to date.

## Surface Hub Miracast channels 149-165 not supported in Europe, Japan, Israel

In compliance with regional governmental regulations, all 5-GHz wireless devices in Europe, Japan, and Israel do not support the Unlicensed National Information Infrastructure-3 (U-NII-3) band. In Surface Hub, the channels associated with U-NII-3 are 149 through 165. This includes Miracast connections on these channels. Therefore, Surface Hubs used in Europe, Japan, and Israel can't use channels 149-165 for Miracast connections.

## Troubleshoot wired connections

- [Device resolution not supported error](#device-resolution-not-supported-error)
- [Connect app exits unexpectedly](#connect-app-exits-unexpectedly)

### Device resolution not supported error

When you try to project from a Surface Pro, Surface Book, or Surface Laptop to an 84-inch Surface Hub by using the HDMI port on the Surface Hub, the error message "Device Resolution is not supported" is displayed.

- **Cause:** The Surface device is not set to a supported 84-inch ingest resolution. By default, Windows tries to connect to the Surface Hub using *Duplicate* mode, duplicating your desktop on both screens. But the default resolution of the Surface device is higher than the 1080p resolution of the Surface Hub, so the Hub cannot display the higher-resolution image.
- **Resolution:** Projecting to a second screen can be accomplished by using *Extend*. Extend is used to expand the desktop user interface across your Surface and Surface Hub displays, allowing each to display the desktop in its native resolution. Both methods described below can configure your Surface to display your desktop in Extend mode.

**Method 1: Change the desktop resolution**

1. Open **Start**, and then select **Settings** > **System** > **Display**.
2. Select the Surface Hub display from the choice made available.
3. Under **Scale and layout**, change the setting under **Resolution** to **1920 x 1080**.

**Method 2: Change Project setting to Extend**

- Press **Windows key+P** and then select **Extend**.

### Connect app exits unexpectedly

At times, a wired Connect session that is started from the Welcome screen by connecting a DisplayPort input will exit back to the Welcome screen after using the side keypad or the source button to cycle through all source inputs.

- **Cause:** This is an issue in the Connect app and its default full-screen state. By changing the size of the app or by selecting a DisplayPort input thumbnail in the Connect app, you can prevent input cycling from affecting the app.
- **Resolution:** Launch the Connect app from the Welcome screen and connect a DisplayPort input to resolve this issue. If the input is already connected, manually select the thumbnail.

## Contact Support

If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).

## Learn more

- [Connect devices to Surface Hub 2S](surface-hub-2s-connect.md)
- [Connect other devices and display with Surface Hub v1](connect-and-display-with-surface-hub.md)
