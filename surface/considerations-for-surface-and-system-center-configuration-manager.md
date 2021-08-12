---
title: Considerations for Surface and Microsoft Endpoint Configuration Manager
description: The management and deployment of Surface devices with Configuration Manager is fundamentally the same as any other PC; this article describes scenarios that may require additional considerations.
keywords: manage, deployment, updates, driver, firmware
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: 
manager: laurawi
ms.date: 08/12/2021
---

# Considerations for Surface and Microsoft Endpoint Configuration Manager

Fundamentally, management and deployment of Surface devices with Microsoft Endpoint Configuration Manager is the same as the management and deployment of any other PC. Like any other PC, a deployment of Surface devices includes importing drivers, importing a Windows image, preparing a deployment task sequence, and then deploying the task sequence to a collection. After deployment, Surface devices are like any other Windows client; to publish apps, settings, and policies, you use the same process as you would use for any other device.

To learn more, see [Microsoft Endpoint Configuration Manager documentation](/mem/configmgr/).

Although the deployment and management of Surface devices is fundamentally similar to other PCs, some scenarios may require additional IT tasks, as described in this article. 

> [!TIP]
> Use the [Current Branch of Microsoft Endpoint Configuration Manager](/mem/configmgr/core/servers/manage/updates) to manage Surface devices .

## Update Surface device drivers and firmware

Although drivers for Surface components and firmware updates are applied automatically as part of the Windows Update process, many organizations rely on managed updates using Windows Server Update Services (WSUS) or Configuration Manager. To learn more, see [Manage Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).

## Surface Ethernet adapters and Configuration Manager deployment

The default mechanism that Configuration Manager uses to identify devices during deployment is the Media Access Control (MAC) address. Because the MAC address is associated with the Ethernet controller, an Ethernet adapter shared among multiple devices will cause Configuration Manager to identify each of the devices as only a single device, resulting in a failed deployment. 

To ensure that Surface devices using the same Ethernet adapter are identified as unique devices during deployment, you can instruct Configuration Manager to identify devices using another method. You can specify that Configuration Manager use other identification methods, as documented in [Manage duplicate hardware identifiers](/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers):

- Add an exclusion for the MAC addresses of Surface Ethernet adapters, which forces Configuration Manager to overlook the MAC address in preference of the System UUID.

- Use a script to identify a newly deployed Surface device by the MAC address of its wireless adapter.

### Surface Ethernet Driver

Since 2016, the driver for the Surface Ethernet adapter has been included by default in Windows and requires no additional IT configuration. With its inclusion in Windows 10, the driver is no longer available for download from the Microsoft Download Center. (If you need to deploy earlier versions of Windows 10 Pro, you can download the latest driver from the [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=surface%20ethernet%20drivers)).

## Deploy Surface app with Configuration Manager

With the release of Microsoft Store for Business, Surface app is no longer available as a driver and firmware download. Organizations deploying Surface app to managed Surface devices or during deployment via  Configuration Manager, must first acquire Surface app through Microsoft Store for Business. To learn more, see [Deploy Surface app with Microsoft Store for Business](deploy-surface-app-with-windows-store-for-business.md).

## Use prestaged media with Surface clients

If your organization uses prestaged media to load deployment resources onto machines prior to deployment with Configuration Manager, the nature of Surface devices as UEFI devices may require you to take additional steps. Specifically, a native UEFI environment requires that you create multiple partitions on the boot disk of the system. If you are following along with the [documentation for prestaged media](/mem/configmgr/osd/deploy-use/create-prestaged-media), the instructions provide for only single partition boot disks and therefore will fail when applied to Surface devices.

Instructions for applying prestaged media to UEFI devices, such as Surface devices, can be found in the [How to apply Task Sequence Prestaged Media on multi-partitioned disks for BIOS or UEFI PCs in System](https://techcommunity.microsoft.com/t5/configuration-manager-archive/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned/ba-p/392239) blog post.

## Licensing conflicts with OEM Activation 3.0

Surface devices come preinstalled with a licensed copy of Windows. The license key for this preinstalled copy of Windows is embedded in the firmware of the device with [OEM Activation 3.0](/windows-hardware/manufacture/desktop/oem-activation-3) (OA 3.0). When you run Windows installation media on a device with an OA 3.0 key, Windows setup automatically reads the license key and uses it to install and activate Windows. In most situations, this simplifies the reinstallation of Windows, because the user does not have to find or enter a license key.

When you reimage a device by using Windows Enterprise, this embedded license key does not cause a conflict. This is because the installation media for Windows Enterprise is configured to install only an Enterprise edition of Windows and therefore is incompatible with the license key embedded in the system firmware. If a product key is not specified (such as when you intend to activate with Key Management Services [KMS] or Active Directory Based Activation), a Generic Volume License Key (GVLK) is used until Windows is activated by one of those technologies.

However, issues may arise when organizations intend to use versions of Windows that are compatible with the firmware embedded key. For example, an organization that wants to install Windows 10 Pro on a device that originally shipped with Windows 10 Home  may encounter difficulty when Windows setup automatically reads the Home edition key during installation and installs as Windows 10 Home instead of Windows 10 Pro. To avoid this conflict, use the Ei.cfg or Pid.txt file to explicitly instruct Windows setup to prompt for a product key, or enter a specific product key in the deployment task sequence. For more information, see [Windows Setup Edition Configuration and Product ID Files](/windows-hardware/manufacture/desktop/windows-setup-edition-configuration-and-product-id-files--eicfg-and-pidtxt). If you do not have a specific key, you can use the default product keys for Windows. For more information, refer to the documentation to [Deploy Windows 10](/windows/deployment/deploy).

## Apply an asset tag during deployment

With the [Surface Asset tag tool](assettag.md), you can identify devices from UEFI even if the operating system fails. 

To learn more about managing assets with Configuration Manager, see [Introduction to asset intelligence in Configuration Manager](/mem/configmgr/core/clients/manage/asset-intelligence/introduction-to-asset-intelligence).

## Configure push-button reset

When you deploy Windows to a Surface device, the push-button reset functionality of Windows is configured by default to revert the system back to a state where the environment is not yet configured. When the reset function is used, the system discards any installed applications and settings. Although in some situations it can be beneficial to restore the system to a state without applications and settings, in a professional environment this effectively renders the system unusable to the end user.

Push-button reset can be configured, however, to restore the system configuration to a state where it is ready for use by the end user. Follow the process outlined in [Deploy push-button reset features](/windows-hardware/manufacture/desktop/deploy-push-button-reset-features) to customize the push-button reset experience for your devices.
