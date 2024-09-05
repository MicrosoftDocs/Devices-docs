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

## Why should I consider Arm processors for new Surface devices in my corporate environment?

Arm-based Surface devices, such as the Surface Pro (11th Edition) and Surface Laptop (7th Edition), deliver exceptional performance, efficiency, and compatibility with both native and emulated applications. These devices, powered by the Snapdragon X series processors, provide outstanding battery life and integrate seamlessly with key productivity tools like Microsoft 365. The Prism emulation engine ensures smooth operation of x86/x64 applications, facilitating an easy transition to Arm architecture without sacrificing performance. Plus, the expanded support for native Arm64 apps ensures that your organization can use cutting-edge technology while maintaining compatibility with existing software.

## How has Microsoft enhanced app performance?

Microsoft continues to invest in the developer ecosystem to ensure optimal performance for both native and emulated apps on Windows on Arm. Nearly 90% of total app usage is projected to come from native apps, thanks to expanded development tools and support. Prism, the advanced emulation engine, optimizes performance and reduces CPU usage, allowing emulated apps to perform on par with, or even exceed, native apps on older models such as Surface Laptop 5 and Surface Pro 9.

Additionally, Microsoft's [App Assure program](https://www.microsoft.com/fasttrack/microsoft-365/app-assure) offers developer resources at no extra cost to help customers resolve app compatibility issues, ensuring smooth deployment of Arm-based devices.

## What is Prism?

Prism is Microsoft's emulation technology that enables x86/x64 applications to run on Windows PCs with Arm processors, such as Surface Pro (11th Edition), Surface Pro 9 with 5G, Surface Pro X, and Surface Laptop (7th Edition). It seamlessly translates app code to run on Arm architecture, optimizing performance, and reducing CPU usage to ensure a smooth user experience on devices powered by Snapdragon X series chips.

## What's new with Windows on Arm emulation?

We now offer more native Arm64 experiences than ever before, including the fastest implementation of Microsoft 365 apps like Teams, PowerPoint, Outlook, Word, Excel, OneDrive, and OneNote. Popular apps such as Chrome, Spotify, Zoom, WhatsApp, Blender, Affinity Suite, and Davinci Resolve now run natively on Arm, delivering excellent performance.

Through partnerships, we increased the number of apps that support Arm architecture. Native versions, optimized to take full advantage of the Snapdragon X Series, also run well on earlier devices, including Surface Pro 9 with 5G and Surface Pro X.

## How do native and emulated apps differ on Windows on Arm?

- **Native apps** are designed to fully utilize the Arm64 architecture, providing optimal performance and compatibility. Microsoft has expanded its support for Arm64 development, ensuring broad availability of Arm64-compatible software.
- **Emulated apps** run via the Prism emulation engine, which minimizes performance loss and ensures that most x86/x64 applications operate seamlessly on Arm64 systems. Users shouldn't notice any significant difference between native and emulated apps apart from potential performance variations.

## What's the performance for emulated apps?

Prism automatically handles x86/x64 apps, translating their code to run efficiently on Arm architecture. Significant optimizations in Prism have improved performance and reduced CPU usage compared to previous emulation technologies. Although apps requiring non-Arm drivers might not function, Microsoft has worked extensively with partners to migrate many apps to run natively on Arm64. Most x64 applications are expected to perform comparably to native apps under emulation.

### How does emulation affect battery life?

Battery life depends on workload, but Microsoft has optimized emulation efficiency and native apps to ensure excellent battery life. Resource-heavy apps, however, might drain the battery faster than lightweight ones.

## Can I run Windows programs that aren't in the Microsoft Store on my Windows 11 Arm-based device?

Yes, non-Store Windows apps can be installed and run on Windows 11 Arm-based devices. Most applications run natively or through Prism emulation, providing smooth performance.

## Where can I get help with app compatibility?

For assistance with app compatibility on Windows 10 and Windows 11 Arm64 devices, visit [App Assure with Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365/app-assure). This service is available at no extra cost for eligible Microsoft 365 or Windows plans.

## Is App Assure just for Microsoft software?

No. The App Assure program supports custom line-of-business apps, non-Microsoft software, and resolves issues related to Microsoft 365 Apps macros and add-ins.

## What limitations should I be aware of when running a Windows 11 Arm-based device?

- **Drivers for hardware, games, and apps must be designed for Arm-based devices.** Most common drivers are now available, but specialized hardware or older peripherals might require verification for Arm64 compatibility.
- **Peripheral compatibility depends on Arm64 drivers.** Devices like printers and scanners work if their drivers are built into Windows 11 or provided by the hardware developer. Without compatible drivers, functionality might be limited.
- **Certain games might face compatibility issues.** Games that rely on OpenGL versions greater than 3.3 or on "anti-cheat" drivers not updated for Arm might not work, although many are being optimized for Arm-based devices.
- **Customization apps might have limited functionality.** Apps that modify the Windows experience, such as input method editors (IMEs) and cloud storage clients, might encounter issues unless optimized for Arm64.
- **Antivirus software compatibility has improved but can vary.** While many non-Microsoft antivirus programs now support Arm-based PCs, we recommend verifying compatibility. Windows Security continues to offer comprehensive protection.
- **Windows Fax and Scan is not available on Arm-based devices.** Alternative solutions are required for faxing and scanning.

## What should I know about using assistive technology on a Windows 11 Arm-based device?

Windows 11 includes various [built-in accessibility features](https://www.microsoft.com/Accessibility/windows) and supports many assistive technology apps available in the Microsoft Store. To ensure compatibility, check with your assistive software vendor or the Microsoft Store to confirm if your preferred apps are optimized for Windows 11 Arm-based devices. While many assistive apps are now supported, some might still require updates for optimal performance.

If you use a screen reader, NVDA has updated its app for compatibility with Windows 11 Arm-based devices. For more information, visit the [NV Access website](https://go.microsoft.com/fwlink/?linkid=867679). Other popular screen readers like JAWS are increasingly supporting Arm-based devices.
