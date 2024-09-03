---
title: Arm-based Surface devices FAQ
description: Explore how Arm-based Surface devices offer top performance, efficiency, and app compatibility for corporate environments.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 09/03/2024
ms.reviewer: jessko
manager: frankbu
appliesto:
- Windows 11
---
# Arm-based Surface devices FAQ



## Why should I consider ARM processors for new Surface devices in my corporate environment?

Arm-based Surface devices offer exceptional performance, efficiency, and compatibility with both native and emulated applications. The Surface Pro (11th Edition) and Surface Laptop (7th Edition)), powered by the Snapdragon X series processors, provide outstanding battery life and seamless integration with productivity tools like Microsoft 365. Our advanced emulation engine, Prism, ensures smooth operation of x86/x64 applications, making it easier to transition without compromising on performance. The expanded support for native Arm64 apps allows your organization to use cutting-edge technology while maintaining compatibility with existing software.

## How has Microsoft enhanced app performance?

Microsoft continues to invest in the developer ecosystem to ensure seamless performance for both native and emulated apps on Windows on Arm. We estimate that nearly 90% of total app minutes to be native apps, thanks to expanded tooling and support. Prism, our advanced emulation engine, optimizes performance and reduces CPU usage, delivering emulated app performance that surpasses even native apps on earlier models like Surface Laptop 5 and Surface Pro 9.

Microsoft's commitment to advancing Arm and app compatibility is evident through ongoing outreach to ISVs and the App Assure program, which offers developer resources to address app compatibility at no extra cost to eligible customers. This combination of state-of-the-art processors and innovative emulation technology provides exceptional performance on these new devices.

## What's new for Windows on Arm emulation? 

The latest Qualcomm Snapdragon X series processors in the Surface Pro (11th Edition) and Surface Laptop (7th Edition) deliver more native Arm64 experiences, including faster implementations of Microsoft 365 apps and other apps like Chrome, Spotify, and Zoom. For apps not yet optimized for Windows on Arm, our enhanced emulation engine helps ensure a smooth user experience.

## What is Prism?

Prism is Microsoft's emulation technology that enables x86/x64 applications to run on Windows PCs with ARM processors. It seamlessly translates app code to run on Arm architecture, optimizing performance, and reducing CPU usage, ensuring a smooth user experience on devices powered by Snapdragon X series chips.

## How do native and emulated apps differ on Windows on Arm?

**Native apps** are built to fully utilize the Arm64 architecture, offering optimal performance and compatibility. We expanded tooling and support to facilitate Arm64 development, ensuring broad availability of Arm64-compatible software.

**Emulated apps** run on Windows on Arm via the Prism emulation engine, which minimizes performance loss, allowing most x86/x64 applications to operate seamlessly on Arm64 systems.

## How do emulated and native apps perform on these new devices compared to previous generations?

Prism automatically handles x86/x64 apps, translating their code for the Arm architecture. Significant optimizations have improved performance and reduced CPU usage compared to previous generations. While apps requiring non-Arm drivers might not function, extensive collaboration with partners has brought many of these applications to Arm64 natively. Most x64 applications are expected to perform comparably to native apps under emulation.

## Where can I get help with app compatibility?

Visit [App Assure with Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365/app-assure) for assistance with app compatibility when deploying Windows 10 and Windows 11, including Arm64 devices. This service is available at no extra cost with eligible Microsoft 365 or Windows plans.

## Is App Assure just for Microsoft software?

No. App Assure also assists with custom line-of-business apps, third-party software, and addressing issues with Microsoft 365 Apps macros and add-ins.

## Windows 11 Arm devices

## What limitations should I be aware of when running a Windows 11 Arm-based device?

- **Drivers for hardware, games, and apps must be designed for Arm-based devices.** Most common drivers are now available, but specialized hardware or older peripherals might require verification from the manufacturer for Arm64 compatibility.
- **Peripheral compatibility depends on Arm64 drivers.** Devices like printers and scanners work if their drivers are built into Windows 11 or provided by the hardware developer. Without compatible drivers, functionality might be limited.
- **Certain games might face compatibility issues.** Games relying on OpenGL versions greater than 3.3 or "anti-cheat" drivers not updated for Arm might not work, though many are being optimized for Arm-based devices.
- **Customization apps might have limited functionality.** Apps that modify the Windows experience, such as input method editors (IMEs) and cloud storage clients, might encounter issues unless optimized for Arm64.
- **Antivirus software compatibility has improved but can vary.** While more non-Microsoft antivirus programs now support Arm-based PCs, we recommend confirming compatibility. Windows Security continues to offer comprehensive protection.
- **Windows Fax and Scan is still not available on Arm-based devices.** Alternative solutions are needed for faxing and scanning.

## Can I run Windows programs that aren't in the Microsoft Store on my Windows 11 Arm-based device?

Yes, you can install and run non-Store Windows apps on your Windows 11 Arm-based device. Most applications run natively or via the emulation engine, which has been optimized for performance.

## What should I know about using assistive technology on a Windows 11 Arm-based device?

Windows 11 includes [built-in accessibility features](https://www.microsoft.com/Accessibility/windows) and supports many assistive technology apps available in the Microsoft Store. To ensure compatibility, check the Microsoft Store or contact your assistive software vendor to see if your preferred apps are optimized for Windows 11 Arm-based devices. While many apps are now supported, some might require updates for seamless operation.
If you use a screen reader, NVDA has updated its app for Windows 11 Arm-based compatibility. Visit the [NV Access website](https://go.microsoft.com/fwlink/?linkid=867679) for more information. Other popular screen readers, like JAWS, are increasingly supporting Arm-based devices.
