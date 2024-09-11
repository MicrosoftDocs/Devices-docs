---
title: "Migrate to Windows 11 Pro or Enterprise on Surface Hub running Microsoft Teams Rooms on Windows"
description: Learn how to migrate Surface Hub 3 to Windows 11 Pro or Enterprise, including downloading the OS, creating a bootable USB, and installing necessary drivers and firmware.
ms.service: surface-hub
author: coveminer
ms.author: dpandre
manager: frankbu
ms.topic: how-to
ms.date: 12/04/2023
ms.localizationpriority: Medium
---

# Migrate to Windows 11 Pro or Enterprise on Surface Hub running Microsoft Teams Rooms on Windows

[!INCLUDE [Hub MTR Scope](includes/hub-mtr-scope.md)]

This article describes how to convert the operating system to Windows 11 Pro or Enterprise and use Surface Hub 3 much like any other PC.

## Before you begin

1. Obtain a Windows 11 Pro or Enterprise license as explained in [Windows commercial licensing overview](/windows/whats-new/windows-licensing).
2. On your Surface Hub 3, back up your data using an external hard drive, cloud storage, or other preferred backup method.
3. On a separate PC, insert a USB drive with at least 8 GB of storage.

## Download Windows 11 and create a bootable USB drive

1. Go to the [Windows 11 software download page](https://www.microsoft.com/software-download/windows11). Under **Create Windows 11 Installation Media**, select **Download Now**.
 ![Screenshot of Windows 11 download page.](images/windows11download.png)
2. Install the media creation tool, accept the license agreement, and select **Next.**
3. Follow the instructions to create a bootable USB drive with the Windows 11 installation files.
4. Remove the USB drive and insert it into Surface Hub 3.
5. While pressing the **Volume down** button, press the **Power** button. Keep pressing both buttons until you see the Windows logo. Release the **Power** button, but hold the **Volume down** button until the Install UI begins.
6. Follow the on-screen instructions to install Windows 11. This includes selecting the language, time, keyboard input, and edition (Pro or Enterprise).

## Install Surface Hub 3 drivers and firmware

To ensure that your Surface Hub 3's hardware is fully usable and up-to-date, download and install [drivers and firmware for Windows 11 Pro and Enterprise on Surface Hub 2S and Surface Hub 3](https://www.microsoft.com/download/details.aspx?id=101974). Then, reboot the device. Keep the Surface turned on for an hour, then reboot it again. You aren't prompted for the second reboot. This pause and extra reboot ensures that the firmware is fully updated.
