---
title: Surface IT Toolkit
description: The new Surface IT Toolkit compiles essential commercial tools in a single application, helping streamline Surface device management for IT admins.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 09/10/2024
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 11
- Windows 10
---

# Surface IT Toolkit

The Surface IT Toolkit is a modern desktop application that compiles essential commercial tools in a single application, helping streamline Surface device management for IT admins.

The Surface IT Toolkit ensures you're using the latest version thanks to [MSIX](/windows/msix/overview) the Windows app package format that automatically checks for updates and downloads them for you.

## Get started with Surface IT Toolkit

1. Download the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703) and install it on the PC you use to manage devices in your organization.

2. Open Surface IT Toolkit and select **Configure App**.

    :::image type="content" source="images/it-toolkit-configure-app.png" alt-text="Screenshot of Start App Configuration page.":::

3. Scroll to review and accept the License Agreement.

    :::image type="content" source="images/it-toolkit-eula.png" alt-text="Screenshot of License Agreement for Surface IT Toolkit.":::

4. Select the devices you intend to manage with the toolkit. Use the provided device family and model selection to choose the appropriate Surface devices such as Surface Laptop 6 for Business, Surface Pro 10, or others. Select **Next**.

    :::image type="content" source="images/it-toolkit-managed-devices.png" alt-text="Screenshot that shows list of managed devices.":::

5. Help improve the app by agreeing to send anonymous usage data. All information is collected anonymously for the purpose of software development and isn't shared or accessible by any third party. If you wish to opt out, uncheck the checkbox **Send required and optional diagnostic data**.

    :::image type="content" source="images/it-toolkit-diagnostics.png" alt-text="Screenshot of anonymous data sharing info.":::

6. Review & complete the configuration. Confirm the information is correct and select **Finish**.

    :::image type="content" source="images/it-toolkit-setup.png" alt-text="Screenshot that shows review and completion of app configuration.":::

### Supported devices

Commercial SKUs for the following devices are supported: Surface Pro (11th Edition), Surface Pro 10, Surface Pro 10 with 5G, Surface Pro 9, Surface Pro 8, Surface Pro 7+, Surface Pro 7, Surface Pro X Wi-Fi, Surface Pro X SQ2,  Surface Pro X SQ1; Surface Laptop (7th Edition), Surface Laptop 6, Surface Laptop 5, Surface Laptop 4, Surface Laptop 3; Surface Laptop Studio 2, Surface Laptop Studio; Surface Laptop SE; Surface Laptop Go 3, Surface Laptop Go 2, and Surface Laptop Go;  Surface Go 4, Surface Go 3, and Surface Go 2; Surface Book 3; Surface Studio 2+ and Surface Studio 2.

## What's in the Surface IT Toolkit?

The Surface IT Toolkit provides a user-friendly interface designed to assist IT admins in managing and configuring Surface devices within their organization. Quickly access toolkit functions including:

- Data Eraser
- UEFI Configurator
- Recovery Tool  
- Tool Library

### Managed devices 

The Managed Devices area displays your selected device models that can be managed with the toolkit, allowing quick and efficient administration of your organization’s deployed devices.

### Quick tasks

- **Build USB for Data Eraser:** Create a USB to securely erase data from Surface SSDs.
- **Create Certificate:** Generate a certificate of sanitization for a previously erased Surface SSD.
- **Create USB Recovery Image:**  Download and build a USB drive to restore a Surface device to factory state.
- **Create UEFI Configuration:** Prepare a UEFI configuration package for Surface devices.

### Tool Library in the Surface IT Toolkit

The Tool Library in the Surface IT Toolkit is a centralized repository that provides IT admins with a suite of tools essential for the configuration and support of Surface devices. This library ensures that the most up-to-date versions of each tool are readily available for deployment. Each tool comes with a "Save Copy" option, allowing IT admins to download and save a copy of the installer for the respective tool. To learn more, see [Surface IT Toolkit Tool Library](surface-it-toolkit-library.md).

## Release notes

### Version 1.198.0

This version of Surface IT Toolkit, released September 10, 2024, includes the following updates:

- Added support for Wi-Fi+5G models of Surface Pro (11th Edition) and Wi-Fi+5G models of Surface Pro 10 for Business
- Improved accessibility options

### Version 1.186.139

This version of Surface IT Toolkit, released May 30, 2024, includes the following updates:

- Added support for Surface Pro 11th Edition, Surface Laptop 7th Edition, and Surface Pro X running Windows 10
- Improved accessibility options
- Resolved a font issue for non-English languages
- The [Recovery Tool](surface-it-toolkit-usb-recover.md) now prevents the device from going to sleep while the process is active

### Version 1.143.139

- Initial release