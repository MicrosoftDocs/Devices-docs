---
title: Surface device compatibility with Windows 10 Long-Term Servicing Channel (Surface)
description: Find out about compatibility and limitations of Surface devices running Windows 10 Enterprise LTSB edition.
ms.service: surface
author: coveminer
ms.author: chauncel
ms.topic: conceptual
ms.localizationpriority: medium
ms.date: 07/21/2021
manager: frankbu
---

# Surface device compatibility with Windows 10 Long-Term Servicing Channel (LTSC)

Surface devices are designed to provide best-in-class experiences in productivity and general-purpose scenarios. Regular updates enable Surface devices to bring innovations and include capabilities delivered by Windows Feature Updates. Feature Updates are available only in Windows 10 Pro or Windows 10 Enterprise editions that receive continuous updates through the Semi-Annual Channel (SAC).

In contrast to the SAC servicing option, formerly known as the Current Branch (CB) or Current Branch for Business (CBB) servicing options, you can't select the Long-Term Servicing Channel (LTSC) option in Windows 10 settings. To use the LTSC servicing option, you must install a separate edition of Windows 10 Enterprise, known as Windows 10 Enterprise LTSC, formerly known as Windows 10 Enterprise LTSB (Long-Term Servicing Branch.

>[!TIP]
>For the latest information about LTSC, refer to the following resources:[Windows 10 release information](/windows/release-health/release-information) and [The next Windows 10 Long Term Servicing Channel (LTSC) release](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/the-next-windows-10-long-term-servicing-channel-ltsc-release/ba-p/2147232).

 In addition to providing an extended servicing model, the Windows 10 Enterprise LTSC edition also provides an environment with several Windows components removed. The core Surface experiences that LTSC impacts include:

* Windows Feature Updates, including enhancements such as:

  * Improvements to Direct Ink and palm rejection provided in Windows 10, version 1607 (also referred to as the Anniversary Update)
  * Improved support for high DPI applications provided in Windows 10, version 1703 (also referred to as the Creators Update)

* Pressure sensitivity settings provided by the Surface app

* The Windows Ink Workspace

* Key touch-optimized in-box applications including Microsoft Edge, OneNote, Calendar, and Camera

The use of the Windows 10 Enterprise LTSC environment on Surface devices results in sub-optimal end-user experiences, and you should avoid using it in environments where users want and expect a premium, up-to-date user experience.

The LTSC servicing option is designed for device types and scenarios where the key attribute is for features or functionality to never change. Examples include power manufacturing or medical equipment systems, or embedded systems in kiosks, such as ATMs or airport ticketing systems.

>[!NOTE]
>For general information about Windows servicing branches, including LTSC, see [Overview of Windows as a service](/windows/deployment/update/waas-overview).

As a general guideline, devices that fulfill the following criteria are considered general-purpose devices and should be paired with Windows 10 Pro or Windows 10 Enterprise using the Semi-Annual Channel servicing option:

* Devices that run productivity software such as Microsoft Office

* Devices that use Microsoft Store applications

* Devices that are used for general Internet browsing (for example, research or access to social media)

Before you choose to use Windows 10 Enterprise LTSC edition on Surface devices, consider the following limitations:

* Driver and firmware updates aren't explicitly tested against releases of Windows 10 Enterprise LTSC.

* If you encounter problems, Microsoft Support will provide troubleshooting assistance. However, due to the servicing nature of the Windows LTSC, issue resolution may require that devices be upgraded to a more recent version of Windows 10 Enterprise LTSC or Windows 10 Pro or Enterprise with the SAC servicing option.

* Surface device replacements (for example, devices replaced under warranty) may contain subtle variations in hardware components that require updated device drivers and firmware. Compatibility with these updates may require the installation of a more recent version of Windows 10 Enterprise LTSC or Windows 10 Pro or Enterprise with the SAC servicing option.

>[!NOTE]
>Organizations that standardize on a specific version of Windows 10 Enterprise LTSC may be unable to adopt new generations of Surface hardware, such as Surface Pro 9 or Surface Laptop 5, without updating to a later version of Windows 10 Enterprise LTSC or Windows 10 Pro or Enterprise. For more information, refer to the [Lifecycle FAQ - Windows](/lifecycle/faq/windows#what-are-the-requirements-for-servicing-and-updating-the-windows-10-long-term-servicing-channel--ltsc--).

Surface devices running Windows 10 Enterprise LTSC edition won't receive new features. In many cases, customers request these features to improve the usability and capabilities of Surface hardware. For example, further improvements for High DPI applications in Windows 10, version 1703. Customers that use Surface devices in the LTSC configuration won't see the improvements until they either update to a new Windows 10 Enterprise LTSC release or upgrade to a version of Windows 10 or Windows 11 with support for the SAC servicing option.

Devices can be changed from Windows 10 Enterprise LTSC to a more recent version of Windows 10 Enterprise, with support for the SAC servicing option, without losing user data by performing an upgrade installation. You can also perform an upgrade installation on multiple devices by leveraging the Upgrade Task Sequence Templates available in the Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager. For more information, see [Perform an in-place upgrade to Windows 10 with MDT](/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).
