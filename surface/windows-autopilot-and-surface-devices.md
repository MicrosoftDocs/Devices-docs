---
title: Windows Autopilot and Surface devices
ms.reviewer: 
manager: laurawi
description: Find out about Windows Autopilot deployment options for Surface devices.
keywords: autopilot, windows 10, surface, deployment
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 9/14/2020
---

# Windows Autopilot and Surface devices

Windows Autopilot is a cloud-based deployment technology in Windows 10. You can use Windows Autopilot to remotely deploy and configure devices in a zero-touch process right out of the box.

Traditionally, IT pros spend a lot of time building and customizing images that will later be deployed to devices that already come with a perfectly good OS already installed on them. Windows Autopilot introduces a new zero-touch deployment approach using a collection of technologies to set up and configure Windows devices. This enables an IT department to configure/customize images with little to no infrastructure to manage and a process that is easy and simple. From the user’s perspective, it only takes a few simple steps to get Surface to a productive state. In fact, the only interaction required from the end user is to connect to a network and to verify their credentials. Everything after that is fully automated.

Windows Autopilot allows you to:

- Automatically join devices to Azure Active Directory (Azure AD).
- Auto-enroll devices into MDM services, such as Microsoft Intune (requires an Azure AD Premium subscription).
- Restrict the Administrator account creation. Autopilot is the only way to have the first person who logs into Windows enter as a standard user.
- Create and auto-assign devices to configuration groups based on device profiles.
- Customize OOBE (Out of Box Experience) content and branding to meet organizational requirements.
- Enable full device configuration with Intune.
- Reset or restart devices remotely.

## How it works

Windows Autopilot-registered devices are identified over the Internet at first startup through a unique device signature that's called a *hardware hash*. They're automatically enrolled and configured by using modern management solutions such as Azure Active Directory (Azure AD) and mobile device management.

You can register Surface devices at the time of purchase from a Surface partner that's enabled for Windows Autopilot. These partners can ship new devices directly to your users. The devices will be automatically enrolled and configured when they are first turned on. This process eliminates reimaging during deployment, which lets you implement new, agile methods of device management and distribution.

## Modern management

Autopilot is the recommended deployment option for Surface devices, including Surface Pro 7+, Surface Laptop 3, Surface Pro 7, and Surface Pro X, which is specifically designed for deployment through Autopilot.

 It's best to enroll your Surface devices with the help of a Microsoft Cloud Solution Provider. This step allows you to manage UEFI firmware settings on Surface directly from Intune. It eliminates the need to physically touch devices for certificate management. See [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md) for details.

## Windows version considerations

Broad deployment of Surface devices through Windows Autopilot, including enrollment by Surface partners at the time of purchase, requires Windows 10 Version 1709 (Fall Creators Update) or later.

These Windows versions support a 4,000-byte (4k) hash value that uniquely identifies devices for Windows Autopilot, which is necessary for deployments at scale. All new Surface devices, including Surface Pro 7+, Surface Pro X, and Surface Laptop 3 ship with Windows 10 Version 1903 or later.

## Exchange experience on Surface devices in need of repair or replacement

Microsoft automatically checks every Surface for Autopilot enrollment and will deregister the device from the customer's tenant.  Microsoft ensures the replacement device is enrolled into Windows Autopilot once a replacement is shipped back to the customer. This service is available on all device exchange service orders directly with Microsoft.

> [!NOTE]
> When customers use a Partner to return devices, the Partner is responsible for managing the exchange process including deregistering and enrolling devices into Windows Autopilot.

## Microsoft Support registration

Customers and Microsoft Cloud Solution Providers (CSPs) have the option of registering Surface devices by submitting requests to Microsoft Support. To learn more, see [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md).

## Surface partners enabled for Windows Autopilot

Select Surface partners can enroll Surface devices in Windows Autopilot for you at the time of purchase. They can also ship enrolled devices directly to your users. The devices can be configured entirely through a zero-touch process by using Windows Autopilot, Azure AD, and mobile device management.

Surface partners that are enabled for Windows Autopilot include:

| US partners | Global partners | US distributors |
|--------------|---------------|-------------------|
|  [CDW](https://www.cdw.com/) |  [ALSO](https://www.also.com/ec/cms5/da_2800/2800-msportal/products-and-solutions/surface/surface-is-more/surface-and-wa/index.jsp) |  [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
|  [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)   |  [ATEA](https://www.atea.com/) |  [Techdata](https://www.techdata.com/)  |
|  [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  |  [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) |  [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
|  [SHI](https://www.shi.com/Surface) |  [Cancom](https://www.cancom.de/) |    |
|  [LDI Connect](https://www.myldi.com/managed-it/)  |  [Computacenter](https://www.computacenter.com/uk) |    |
|  [F1](https://www.functiononeit.com/#empower)  |   |  |
|  [Protected Trust](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | |

## Learn more

For more information about Windows Autopilot, see:

- [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Windows Autopilot requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md)
