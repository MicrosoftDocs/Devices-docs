---
title: Wake On LAN for Surface devices 
description: See how you can use Wake On LAN to remotely wake up devices to perform management tasks automatically.
keywords: update, deploy, driver, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 3/19/2021
---

# Wake On LAN for Surface devices

Surface devices that use a Surface Ethernet adapter to connect to a wired network can take advantage of Wake On LAN (WOL) from Connected Standby. With WOL, you can remotely wake up devices and automatically perform management tasks using management solutions such as Microsoft Endpoint Manager/Microsoft Intune.

## WOL-supported devices

- Surface Ethernet adapter
- Surface USB-C to Ethernet and USB Adapter
- Surface Dock 2
- Surface Pro 6 and later
- Surface Book (all generations)
- Surface Laptop (all generations)
- Surface Go (all generations)
- Surface Studio 2 (see Appendix)


## Using Surface WOL

IT admins can trigger devices using a wake on LAN request (magic packet) that contains the target computer’s MAC address. To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter. Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.

Many management solutions, such as Microsoft Endpoint Configuration Manager and third party Microsoft Store apps provide built-in support for WOL. Note that devices need to be in Connected Standby (Sleep) mode and connected to AC power. To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).


### To check WOL is enabled on your device

1. On your Ethernet connected device, select your network adapter, and then select **Properties**.

     ![Surface Ethernet Adapter](images/surface-ethernet.png)

2. Select **Configure** > **Advanced**.
3. Scroll to **Modern Standby WoL Magic Packet** and ensure **Enabled** is selected.

     ![Check WOL is enabled on your device](images/ethernet-wol-setting.png)

## Appendix: Surface Studio 2

To enable WOL on Surface Studio 2, use the following procedure.

1. Create the following registry keys:

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. Run the following command

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## Learn more

- [Microsoft Surface USB-C to Ethernet and USB Adapter](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [Surface USB 3.0 Gigabit Ethernet Adapter](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)