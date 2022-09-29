---
title: ARM-based Surface devices FAQ
description: This article provides introductory app compatibility information for Surface Pro X ARM-based PCs.
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 09/29/2022
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
---
# ARM-based Surface devices FAQ

## Introduction

### What are the benefits of an ARM-based Surface device?

Windows 10 and Windows 11 ARM-based PCs, such as Surface Pro X, help you keep working wherever you go. Here are some primary benefits:

- **Always be connected to the internet**. With a cellular data connection, you can be online wherever you get a cellular signal, just like your mobile phone. You can connect to Wi-Fi to save cellular data and keep working when you're at work, home, or by another Wi-Fi network you trust.
- **Battery life that goes beyond all day**. You'll use less power than you would with other PCs, so you can go through a typical work or school day without running out of battery or worrying about finding a power outlet. If you want to use your device for something more fun, you can play videos stored on your device for many hours without charging your battery.
- **Turn on instantly.** When you're not using your device, press the power button as you do on your mobile phone to turn off the screen. When you take out your device and turn it back on, it turns on instantly. Whenever you have a few minutes in between classes, meetings, or other activities, you can get things done without waiting for your device to start.

### What is App assure?

Microsoft is committed to ensuring customers have a great compatibility experience with Windows 10 and Windows 11 on ARM64 devices such as the Surface Pro X. We've expanded the App Assure program to support customers who encounter app compatibility challenges by providing engineers to troubleshoot and provide app remediations – all at no extra cost. The service is available to commercial and EDU customers for your LOB, ISV, and Microsoft first-party apps targeting Windows 10 or Windows 11 on ARM64. To learn more, see [App Assure](https://www.microsoft.com/fasttrack/microsoft-365/app-assure).

## Windows 11 ARM devices

### What limitations should I be aware of when running a Windows 11 ARM-based device?

There are some limitations when you run a Windows 11 ARM-based device:

- **Drivers for hardware, games and apps will only work if designed for a Windows 11 ARM-based device**. For more info, check with the hardware manufacturer or the organization that developed the driver. Drivers are software programs that communicate with hardware devices—they're commonly used for antivirus and antimalware software, printing or PDF software, assistive technologies, CD and DVD utilities, and virtualization software.
- If a driver doesn't work, the app or hardware that relies on it won't work either (at least not entirely). Peripherals and devices only work if the drivers they depend on are built into Windows 11 or if the hardware developer has released Arm64 drivers for the device.
- **Certain games won't work**. Games and apps won't work if they use a version of OpenGL greater than 3.3 or rely on "anti-cheat" drivers that haven't been made for Windows 11 ARM-based PCs. Check with your game publisher to see if a game will work.
- **Apps that customize the Windows experience might have problems**. This includes input method editors (IMEs), assistive technologies, and cloud storage apps. The organization that develops the app determines whether its app will work on a Windows 11 ARM-based device.
- **Some third-party antivirus software can't be installed**. You won't be able to install some third-party antivirus software on a Windows 11 ARM-based PC—unless it's been made or updated for an ARM-based device. However, Windows Security will help keep you safe for the supported lifetime of your Windows 11 device.
- **Windows Fax and Scan isn't available**. This feature isn't available on a Windows 11 ARM-based device.

### I want to use Windows programs that aren't in the Microsoft Store. Can I run them on my Windows 11 ARM-based device?

- Yes, you can install Windows apps that aren't available in the Microsoft Store in Windows. Peripherals and devices only work if the drivers they depend on are built into Windows 11 or if the hardware developer has released Arm64 drivers for the device. It's a good idea to check whether the hardware developer has published a version of the driver that runs on a Windows 11 ARM-based device.

### I use assistive technology—what should I know before buying a Windows 11 ARM-based device?

- Windows 11 provides [built-in accessibility features](https://www.microsoft.com/Accessibility/windows) that help you do more on your device. You can also find assistive technology apps in the Microsoft Store in Windows, such as the [KNFB Reader](https://www.microsoft.com/store/p/knfb-reader/9nblggh6hqkk) and the [Read&Write extension for Microsoft Edge](https://microsoftedge.microsoft.com/addons/detail/readwrite-for-microsoft-/bjglhpoliipklkfjcahfefdlfpifcinb?hl)—and we're working to offer more apps soon.
- You can check the Microsoft Store or contact your assistive software vendor to see if your preferred assistive technology apps are available for a Windows 11 ARM-based device.
- You may want to check with the vendor to determine if their app is compatible with a Windows 11 ARM-based device. Not all assistive technology apps work as expected.
- If you use a screen reader, NVDA has updated its app to be compatible with a Windows 11 ARM-based device. For more info, visit the [NV Access website](https://go.microsoft.com/fwlink/?linkid=867679).

## Windows 10 ARM devices

### What limitations should I be aware of when running a Windows 10 ARM-based device?

There are some limitations when you run a Windows 10 ARM-based device:

- **Drivers for hardware, games and apps will only work if designed for a Windows 10 ARM-based device**. For more info, check with the hardware manufacturer or the organization that developed the driver. Drivers are software programs that communicate with hardware devices—they're commonly used for antivirus and antimalware software, printing or PDF software, assistive technologies, CD and DVD utilities, and virtualization software.
- If a driver doesn't work, the app or hardware that relies on it won't work either (at least not entirely). Peripherals and devices only work if the drivers they depend on are built into Windows 10 or if the hardware developer has released Arm64 drivers for the device.
- **64-bit (x64) apps won't work**. You'll need 64-bit (Arm64) apps, 32-bit (Arm32) apps, or 32-bit (x86) apps. You can usually find 32-bit (x86) versions of apps, but some app developers only offer 64-bit (x64) apps.
- **Certain games won't work**. Games and apps won't work if they use a version of OpenGL greater than 1.1 or rely on "anti-cheat" drivers that haven't been made for Windows 10 ARM-based PCs. Check with your game publisher to see if a game will work.
- **Apps that customize the Windows experience might have problems**. This includes input method editors (IMEs), assistive technologies, and cloud storage apps. The organization that develops the app determines whether their app will work on a Windows 10 ARM-based device.
- **Some third-party antivirus software can't be installed**. You won't be able to install some third-party antivirus software on a Windows 10 ARM-based device. However, Windows Security will help keep you safe for the supported lifetime of your Windows 10 device.
- **Windows Fax and Scan isn't available**. This feature isn't available on a Windows 10 ARM-based device.

### I want to use Windows programs that aren't in the Microsoft Store. Can I run them on my Windows 10 ARM-based device?

- You can install 32-bit (x86) and 64-bit (Arm64) Windows apps that aren't available in the Microsoft Store in Windows. 64-bit (x64) apps won't run. Peripherals and devices only work if the drivers they depend on are built into Windows 10 or if the hardware developer has released Arm64 drivers for the device. It's a good idea to check whether the hardware developer has published a version of the driver that runs on a Windows 10 ARM-based device.

### I use assistive technology—what should I know before buying a Windows 10 ARM-based device?

- Windows 10 provides [built-in accessibility features](https://www.microsoft.com/Accessibility/windows) that help you do more on your device. You can also find assistive technology apps in the Microsoft Store in Windows, such as the [KNFB Reader](https://www.microsoft.com/store/p/knfb-reader/9nblggh6hqkk) and the [Read&Write extension for Microsoft Edge](https://microsoftedge.microsoft.com/addons/detail/readwrite-for-microsoft-/bjglhpoliipklkfjcahfefdlfpifcinb?hl=en-US)—and we're working to offer more apps soon.
- You can check the Microsoft Store or contact your assistive software vendor to see if your preferred assistive technology apps are available for a Windows 10 ARM-based device.
- You may want to check with the vendor to determine if their app is compatible with a Windows 10 ARM-based device. Not all assistive technology apps work as expected.
- If you use a screen reader, NVDA has updated its app to be compatible with a Windows 10 ARM-based device. For more info, visit the [NV Access website](https://go.microsoft.com/fwlink/?linkid=867679).
