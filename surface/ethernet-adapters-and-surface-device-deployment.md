---
title: Ethernet adapters and Surface deployment (Surface)
description: This article provides guidance and answers to help you perform a network deployment to Surface devices.
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: 
manager: laurawi
keywords: ethernet, deploy, removable, network, connectivity, boot, firmware, device, adapter, PXE boot, USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
---

# Ethernet adapters and Surface deployment

This article describes how to perform a network deployment of the latest Surface devices including Surface Pro 3 and later.

Network deployment to Surface devices can pose some unique challenges for system administrators. Due to the lack of a native wired Ethernet adapter, administrators must provide connectivity through a removable Ethernet adapter.

## Select an Ethernet adapter for Surface devices

Before you can address the concerns of how you'll boot to your deployment environment or how devices will be recognized by your deployment solution, you have to use a wired network adapter.

When selecting Ethernet adapters, the primary concern is how adapters will boot your Surface devices from the network. Suppose you're pre-staging clients with Windows Deployment Services (WDS) or using Microsoft Endpoint Configuration Manager. In that case, you may also want to consider whether the removable Ethernet adapters will be dedicated to a specific Surface device or shared among multiple devices. For more information on potential conflicts with shared adapters, see [Manage MAC addresses with removable Ethernet adapters](#manage-mac-addresses) later in this article.

Booting from the network (PXE boot) is only supported when using an Ethernet adapter or docking station from Microsoft. The chipset in the Ethernet adapter or dock must be detected and configured as a boot device in the firmware of the Surface device. Microsoft Ethernet adapters, such as the Surface Ethernet Adapter and the [Surface Dock](https://www.microsoft.com/surface/accessories/surface-dock), use a chipset compatible with the Surface firmware.

The following Ethernet devices are supported for network boot with Surface devices:

- Surface USB-C to Ethernet and USB 3.0 Adapter
- Surface USB 3.0 to Gigabit Ethernet Adapter
- Microsoft USB-C Travel Hub
- Surface Dock
- Surface Dock 2
- Docking Station for Surface 3
- Docking Station for Surface Pro 3 
- Docking Station for Surface Pro and Surface Pro 2

Third-party Ethernet adapters are also supported for network deployment, although they don't support PXE boot. To use a third-party Ethernet adapter, you must load the drivers into the deployment boot image, and you must launch that boot image from a separate storage device, such as a USB stick.

## Boot Surface devices from the network

To boot from the network or a connected USB stick, you must instruct the Surface device to boot from an alternate boot device. You can alter the boot order in the system firmware to prioritize USB boot devices or  boot from an alternate boot device during the boot-up process.

**To boot from an alternate boot device:**

1. Ensure the Surface device is powered off.
2. Press and hold the **Volume Down** button.
3. Press and release the **Power** button.
4. After the system begins to boot from the USB stick or Ethernet adapter, release the **Volume Down** button.

>[!NOTE]
>In addition to an Ethernet adapter, a keyboard must also be connected to the Surface device to enter the preinstallation environment and navigate the deployment wizard.

For Windows 10, version 1511 and later – including the Windows Assessment and Deployment Kit (Windows ADK) for Windows 10, version 1511 – the drivers for Microsoft Surface Ethernet Adapters are present by default. If you're using a deployment solution that uses Windows Preinstallation Environment (WinPE), like the Microsoft Deployment Toolkit, and booting from the network with PXE, ensure that your deployment solution uses the latest version of the Windows ADK.

## <a href="" id="manage-mac-addresses"></a>Manage MAC addresses with removable Ethernet adapters

Another consideration for administrators performing Windows deployment over the network is identifying computers when using the same Ethernet adapter to deploy to more than one computer. A common identifier used by deployment technologies is the Media Access Control (MAC) address associated with each Ethernet adapter. However, when you use the same Ethernet adapter to deploy to multiple computers, you can't use a deployment technology that inspects MAC addresses because there's no way to differentiate the MAC address of the removable adapter when used on different computers.

The simplest solution to avoid MAC address conflicts is to provide a dedicated removable Ethernet adapter for each Surface device. This can make sense in many scenarios where the Ethernet adapter or the extra functionality of the docking station will be used regularly. However, not all scenarios call for the extra connectivity of a docking station or support for wired networks.

Another potential solution to avoid conflict when adapters are shared is to use the [Microsoft Deployment Toolkit (MDT)](/mem/configmgr/mdt) to perform deployment to Surface devices. MDT doesn't use the MAC address to identify individual computers and thus isn't subject to this limitation. However, MDT does use Windows Deployment Services to provide PXE boot functionality, and is subject to the limitations regarding pre-staged clients, as described later in this section.

When you use a shared adapter for deployment, the solution for affected deployment technologies is to use another means to identify unique systems. For Configuration Manager and WDS, both of which can be affected by this issue, the solution is to use the System Universal Unique Identifier (System UUID) embedded in the computer firmware by the computer manufacturer. For Surface devices, you can see this entry in the computer firmware under **Device Information**.

**To access the firmware of a Surface device:**

1. Ensure the Surface device is powered off.
2. Press and hold the **Volume Up** button.
3. Press and release the **Power** button.
4. After the machine begins to boot, release the **Volume Up** button.

When deploying with WDS, the MAC address is only used to identify a computer when the deployment server is configured to respond only to known, pre-staged clients. When pre-staging a client, an administrator creates a computer account in Active Directory and defines that computer by the MAC address or the System UUID. To avoid the identity conflicts caused by shared Ethernet adapters, you should use [System UUID to define pre-staged clients](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc742034(v=ws.11)). 

Alternatively, you can configure WDS to respond to unknown clients that don't require definition by either MAC address or System UUID. Select the **Respond to all client computers (known and unknown)** option on the [**PXE Response** tab](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732360(v=ws.11)) in **Windows Deployment Server Properties**.

The potential for conflicts with shared Ethernet adapters is much higher with Configuration Manager. Where WDS only uses MAC addresses to define individual systems, Configuration Manager uses the MAC address to define separate systems whenever deploying to new or unknown computers. This can result in improperly configured devices or even the inability to deploy more than one system with a shared Ethernet adapter. Several potential solutions for this situation are described in detail in [How to Use The Same External Ethernet Adapter For Multiple SCCM OSD](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374).
