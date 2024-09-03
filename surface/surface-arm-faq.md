---
title: Arm-based Surface devices FAQ
description: This article provides answers to questions about app compatibility and related issues for Surface Pro X Arm-based PCs.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 09/29/2022
ms.reviewer: jessko
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---
# Arm-based Surface devices FAQ


## Introduction

### Why should I consider Arm processors for new Surface devices in my corporate environment?

- Arm-based Surface devices offer exceptional performance, efficiency, and compatibility with a wide range of applications, both native and emulated. Surface Pro (11th Edition) and Surface Laptop (7th Edition), powered by the Snapdragon X series processors, provide outstanding battery life and seamless integration with key productivity tools like Microsoft 365, as well as other essential applications. Prism, our advanced emulation engine, ensures that most x86/x64 applications run smoothly, making it easier to transition without compromising on performance or user experience. Additionally, the expanded support for native ARM64 apps means your organization can benefit from cutting-edge technology while maintaining compatibility with existing software.

### What have you done to improve the Windows on Arm emulation? Are you confident that everyday apps will work well on these new devices?

- Starting with Qualcomm Snapdragon X series on Surface Pro (11th Edition) and Surface Laptop (7th Edition), we offer more native Arm64 experiences, including our fastest implementation of Microsoft 365 apps, like Teams, PowerPoint, Outlook, Word, Excel, OneDrive, and OneNote. Additionally, popular apps such as Chrome, Spotify, Zoom, WhatsApp, Blender, Affinity Suite, and Davinci Resolve now run natively on Arm.
- We’re confident that customers will have a great experience running their apps on these devices, whether they are native or emulated. Through strong partnerships, we’ve significantly increased the number of apps that support the platform by offering native versions that fully exploit the incredible performance of the Snapdragon X Series.
- For applications that are not yet built for Windows on Arm, our enhanced emulation engine offers improved performance, ensuring a smooth experience even with emulated apps.

### What is Prism?

Prism is Microsoft's emulation technology that enables x86/x64 applications to run on Windows PCs with Arm processors. It automatically translates an app's code to run seamlessly on Arm architecture, optimizing performance and reducing CPU usage. Prism leverages Snapdragon X series chips on Surface Pro (11th Edition) and Surface Laptop (7th Edition) to ensure a smooth user experience with both native and emulated apps.

### For apps running on Windows on Arm, what's the difference between running in emulation vs native?

- **Native apps** are specifically built to leverage the full capabilities of the Arm64 architecture, ensuring optimal performance and compatibility. Over the past few years, we’ve expanded our tooling support to facilitate Arm64 development, ensuring that open-source software (OSS) and other dependencies are readily available in Arm64. This has been a collaborative effort between Microsoft, hardware partners like Qualcomm, and key independent software vendors (ISVs).
- **Emulated apps** are those not initially designed for the Arm64 architecture but can still run on Windows on Arm through our emulation engine. Most x86 and x64 applications run seamlessly on Arm64 systems, with performance optimizations minimizing any potential performance loss during emulation.
- **User experience** remains consistent when interacting with both native and emulated apps, with the primary difference being potential performance variations, although these are increasingly negligible with the latest optimizations.

### What have you done to improve the Windows on Arm emulation?

- We are confident that customers will enjoy a smooth experience with their apps on these devices, whether they are running natively or under emulation. Through strong partnerships, we've significantly expanded the number of apps available as native versions that fully exploit the Snapdragon X Elite’s impressive performance. Currently, 87% of total app usage (excluding gaming) is spent in native applications. For apps not yet built for Windows on Arm, our emulation technology has been enhanced to be faster and more efficient than ever before, ensuring a seamless experience for everyday apps.

### How do emulated and native apps perform on these devices compared to previous generations?

- Our emulation engine automatically handles x86/x64 apps, translating their code to function on the Arm architecture. Significant optimizations have improved performance and reduced CPU usage compared to previous generations.
- **Driver-dependent apps**: Apps that require drivers not updated for Arm will not function under emulation. This includes certain antivirus programs, VPNs, and games that rely on specific anti-cheat software. However, thanks to extensive collaboration across Microsoft and our partners, many apps that previously struggled under emulation are now available natively for Windows on Arm.
- With these exceptions in mind, we expect the vast majority of x64 applications to perform well under emulation, offering a comparable experience to native apps.

### What is App Assure?

Microsoft is committed to ensuring customers have a great compatibility experience with Windows 10 and Windows 11 on Arm64 devices such as the Surface Pro X. We've expanded the App Assure program to support customers who encounter app compatibility challenges by providing engineers to troubleshoot and provide app remediations—all at no extra cost. The service is available to commercial and EDU customers for your LOB, ISV, and Microsoft first-party apps targeting Windows 10 or Windows 11 on Arm64. To learn more, see [App Assure](https://www.microsoft.com/fasttrack/microsoft-365/app-assure).

## Windows 11 Arm devices

### What limitations should I be aware of when running a Windows 11 Arm-based device?

While Windows 11 on Arm-based devices has matured significantly, there are still some limitations to consider:

- **Drivers for hardware, games, and apps must be designed for Arm-based devices**. Most common drivers are now available, but for specialized hardware or older peripherals, it’s important to verify with the manufacturer whether Arm64 drivers are provided. This is particularly relevant for certain antivirus software, printing and PDF utilities, assistive technologies, and virtualization software.
- **Peripheral compatibility depends on Arm64 drivers**. Devices like printers, scanners, and other peripherals will work if their drivers are built into Windows 11 or provided by the hardware developer. Without compatible drivers, the device may not function properly.
- **Certain games may still face compatibility issues**. Games relying on OpenGL versions greater than 3.3 or "anti-cheat" drivers not updated for Arm-based PCs may not work. However, an increasing number of games are being optimized for Arm-based devices.
- **Customization apps may have limited functionality**. Some apps that modify the Windows experience, including input method editors (IMEs), assistive technologies, and cloud storage clients, may encounter issues unless optimized for Arm64.
- **Antivirus software compatibility has improved but can vary**. While more third-party antivirus programs now support Arm-based PCs, it’s advisable to confirm compatibility. Windows Security continues to provide comprehensive protection.
- **Windows Fax and Scan** is still not available on Arm-based devices. Users will need to use alternative solutions for faxing and scanning.

### I want to use Windows programs that aren't in the Microsoft Store. Can I run them on my Windows 11 Arm-based device?

- Yes, you can install and run Windows apps that aren't available in the Microsoft Store on your Windows 11 Arm-based device. Most applications will run natively or via the emulation engine, which has been optimized for performance.

### I use assistive technology—what should I know before buying a Windows 11 Arm-based device?

- Windows 11 includes [built-in accessibility features](https://www.microsoft.com/Accessibility/windows) that enhance usability across a wide range of needs. Additionally, assistive technology apps are available in the Microsoft Store, including popular options like the [KNFB Reader](https://www.microsoft.com/store/p/knfb-reader/9nblggh6hqkk) and the [Read&Write extension for Microsoft Edge](https://microsoftedge.microsoft.com/addons/detail/readwrite-for-microsoft-/bjglhpoliipklkfjcahfefdlfpifcinb?hl), with more apps being added regularly.
- To ensure compatibility, check the Microsoft Store or contact your assistive software vendor to see if your preferred assistive technology apps are available and optimized for Windows 11 Arm-based devices. While many apps are now supported, some may still require updates from the vendor to work seamlessly on these devices.
- It's important to confirm with the app vendor whether their assistive technology software is fully compatible with Windows 11 on Arm. Not all assistive technology apps may function as expected, particularly if they rely on older drivers or have not yet been optimized for Arm architecture.
- If you use a screen reader, NVDA has updated its app for compatibility with Windows 11 Arm-based devices. For more information, visit the [NV Access website](https://go.microsoft.com/fwlink/?linkid=867679). Additionally, other popular screen readers like JAWS are also increasingly supporting Arm-based devices, so it's worth checking with the software provider.