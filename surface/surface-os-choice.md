---
title: OS choice for new Surface devices
description: This article describes how commercial customers can purchase new Surface for Business devices with Windows 10 or Windows 11. 
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 11/14/2023
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---

# OS choice for new Surface devices

Commercial customers can choose to have Windows 10 or Windows 11 installed on new Surface for Business devices:

- [Surface Pro 8](https://www.microsoft.com/surface/business/surface-pro-8)
- [Surface Pro 9](https://www.microsoft.com/surface/business/surface-pro-9)
- [Surface Laptop 4](https://www.microsoft.com/surface/business/surface-laptop-4)
- [Surface Laptop 5](https://www.microsoft.com/d/surface-laptop-5)
- [Surface Laptop Go 2](https://www.microsoft.com/surface/business/surface-laptop-go-2)
- [Surface Laptop Go 3](https://www.microsoft.com/surface/business/surface-laptop-go-3)
- [Surface Laptop Studio](https://www.microsoft.com/surface/business/surface-laptop-studio)
- [Surface Go 3](https://www.microsoft.com/surface/business/surface-go-3)
- [Surface Go 4](https://www.microsoft.com/surface/business/surface-go-4)

> [!IMPORTANT]
> When Windows 10 reaches end of support (EOS) on October 14, 2025, Microsoft will no longer release security updates, bug fixes, time zone updates, or technical support from Microsoft. To learn more, including transition options for organizations needing more time, see [Plan for Windows 10 EOS with Windows 11, Windows 365, and ESU](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/plan-for-windows-10-eos-with-windows-11-windows-365-and-esu/ba-p/4000414). 

## OS choice options

If you're selecting an OS for new devices in your organization and still using Windows 10, we strongly recommend migrating to Windows 11. Organizations running legacy software are vulnerable to significant security risk and potential compliance violations. The Surface OS choice program continues to offer Windows 10<sup>1</sup> as follows:

- **Windows 10 only.** Designed for customers who require Windows 10 out of the box and deploy devices using Windows Autopilot or Microsoft Entra domain join (AADJ). With **Windows 10 SKUs**, you avoid the need to compile driver packs and reimage devices before distributing them to users. It includes an additional per-device fee of $30 or $50 depending on the device, as noted below.<sup>2</sup> (Prices are based on MSRP, actual pricing may vary.)
- **Windows 10 & Windows 11.** Designed for customers who use Windows 11 and also deploy Windows 10 via traditional deployment methods that rely on reimaging devices. With **Windows 11 SKUs**, you can take advantage of built-in downgrade rights to Windows 10 and load custom Windows 10 images on devices as needed.

> [!TIP]
> Microsoft Windows 10 Pro is preinstalled with Windows 10 downgrade software. It includes a license for the Downgrade Facilitation Product available via downgrade rights from Windows 11 Pro. 

**Table 1. OS choice summary**

| Network environment     | Deployment method               | Recommended SKUs | Additional cost |
| ----------------------- | ------------------------------- | ---------------- | --------------- |
| Windows 10 only         | Modern: Autopilot/AADJ          | Windows 10       | $30-$50 <sup>2</sup>        |
| Windows 10 & Windows 11 | Legacy: Custom image deployment | Windows 11       | None            |

## Windows 10 only

> [!NOTE]
> Effective March 31, 2024, Microsoft will no longer offer Windows 10 Pro as a downgrade choice in operating systems on devices delivered from the factory. To run Windows 10 on a Surface device, see [Downgrade from Windows 11 to Windows 10 via MSI file](#downgrade-from-windows-11-to-windows-10-via-msi-file). 

The ability to get the OS version you need directly from Surface includes delivery of factory shrink-wrapped devices fully configured with the requisite firmware, drivers, and security policies. The extra fee covers the cost of this service along with the following benefits that allow you to:

- Provide your users with the latest Surface hardware today while upgrading to Windows 11 at your own pace.
- Reduce your exposure to potential supply chain vulnerabilities by eliminating the need to reimage to Windows 10.
- Save time with Windows Autopilot zero-touch deployment, including faster app and policy updates and fewer help desk calls.

### Windows 10 final version 

Windows 10 version 22H2 is the [final version of Windows 10](/windows/release-health/release-information) with monthly security updates continuing through October 14, 2025. (The Windows 10 IoT Enterprise Long-Term Servicing Channel (LTSC) and Windows 10 IoT Enterprise will continue to receive updates based on their specific lifecycles.)


|      Device           | Windows 10 | Windows 11 |
| --------------------- | ---------- | ---------- |
| Surface Laptop Go 2   | 22H2       | 22H2       |
| Surface Laptop Go 3   | 22H2       | 22H2       |
| Surface Laptop 4      | 22H2       | 22H2       |
| Surface Laptop 5      | 22H2       | 22H2       |
| Surface Laptop Studio | 22H2       | 22H2       |
| Surface Go 3          | 22H2       | 22H2       |
| Surface Go 4          | 22H2       | 22H2       |
| Surface Pro 8         | 22H2       | 22H2       |
| Surface Pro 9         | 22H2       | 22H2       |

> [!NOTE]
> Surface Pro 9 is available for Windows 10. Surface Pro 9 with 5G is only available with Windows 11. 

## How to order

Commercial customers can place orders for new devices via [authorized Microsoft Surface resellers](https://www.microsoft.com/surface/business/where-to-buy-microsoft-surface).


## Downgrade from Windows 11 to Windows 10 via MSI file

After March 31, 2024 -- when new devices will no longer ship with Windows 10 preinstalled -- you can manually downgrade Windows Pro or Enterprise editions with a Microsoft Installer (MSI) file designed for this purpose. 

- [Downgrade individual devices to Windows 10](#downgrade-individual-devices-to-windows-10)
- [Automate downgrade of multiple devices](#automate-downgrade-of-multiple-devices-to-windows-10)

### Licensing considerations

Use one of the following options:

- Use the downgrade rights allowed by the OEM End User License Agreement (EULA). This means you can install Windows 10 Pro on a Surface Device that has a Windows 11 Pro license, as long as you comply with the terms and conditions of the OEM EULA. 
- Use the Software Assurance rights with volume license agreements. This means that you can run Windows 10 Pro on a Surface device that has a Windows 11 Pro license, as long as you have a valid volume license agreement that covers the device and the operating system. 
- To learn more, see [Manage & deploy Surface driver & firmware updates](manage-surface-driver-and-firmware-updates.md)

## Downgrade individual devices to Windows 10

This section explains how to manually downgrade an individual Surface device to Windows 10. 

1. **Prepare your Surface device**:
   - Ensure that all important data on the device is backed up. To learn more, see [Back up your Windows PC](https://support.microsoft.com/en-us/windows/back-up-your-windows-pc-87a81f8a-78fa-456e-b521-ac0560e32338#ID0EBF=Windows_11) and view the following video:

      > [!VIDEO https://www.microsoft.com/videoplayer/embed/RW1g7Ie?]
 

2. **Download the Windows 10 MSI file**:
   - Go to [Manage & deploy Surface driver & firmware updates](/surface/manage-surface-driver-and-firmware-updates#download-msi-files) and select the appropriate MSI for your device. 
   - Select **Download** to display the available MSI files for your device. 
   - As an example, for Surface Laptop 5, select the MSI download for Windows 10 (look for **win10** in the file name) and click **Download**:
   
   :::image type="content" source="images/download-win10-msi-example.png" alt-text="Screenshot that shows selection of Windows 10 MSI file.":::
   
3. **Run the MSI file**:
   - Close all running applications on your Surface device.
   - Run the downloaded MSI file. This process automatically initiates the downgrade from Windows 11 to Windows 10. Follow the on-screen instructions carefully.

4. **Installation and setup**:
   - The MSI installer handles the downgrade process. Your device may restart several times during the installation.
   - Once the downgrade process is complete, go through the initial Windows 10 setup process. This may involve configuring settings, signing in with a Microsoft account, and installing updates.
   - IT admins can configure the first-time setup experience per the instructions in [Customize the Windows 10 Out of Box Experience (OOBE)](/windows-hardware/customize/desktop/customize-oobe).

5. **Post-installation checks**:
   - After the setup is complete, verify that all device drivers are correctly installed and updated for Windows 10. To learn more, see [Update drivers manually in Windows](https://support.microsoft.com/windows/update-drivers-manually-in-windows-ec62f46c-ff14-c91d-eead-d7126dc1f7b6).
   - Restore any previously backed-up data to the device. Follow the [Restore a backup](https://support.microsoft.com/windows/back-up-your-windows-pc-87a81f8a-78fa-456e-b521-ac0560e32338#ID0EBF=Windows_10) instructions and view the following video. 

   > [!VIDEO https://www.microsoft.com/videoplayer/embed/RW1ga0E?]

6. **Additional recommendations**:
   - Check for any available updates in Windows Update to ensure your Windows 10 installation is up to date. Go to **Start** > **Settings** > **Update & Security** > **Windows Update**. 
   - Reinstall any applications that were removed during the downgrade process. If you backed up your device with OneDrive, sign in to OneDrive with the same Microsoft account you used to make the original backup.You can also check your Download folder for any previously downloaded apps: Select the app and follow the prompts to reinstall. 

## Automate downgrade of multiple devices to Windows 10

When downgrading multiple devices from Windows 11 to Windows 10 in an IT environment, the basic steps outlined for individual downgrades still apply, but with additional considerations for scale, automation, and management. Review the insructions and guidance in [Configure a test lab to deploy Windows 10](/windows/deployment/windows-10-poc).

> [!IMPORTANT]
> After Windows 10 EOS, on October 14, 2025, Windows 10 MSI files for Surface devices will no longer be updated with newer drivers and firmware.

### References

1. Windows 10 Downgrade Facilitation SKU offered for Windows 11-capable devices.  
2. Effective July 1, 2023, additional fee increased from $30 to $50 for all new eligible devices as well as the following devices: Surface Pro 9, Surface Laptop 5, Surface Go 3 LTE, and Surface Pro 8 LTE. The fee remains set at $30 for Surface Laptop Go 2, Surface Laptop 4, and Surface Laptop Studio.

### Learn more

- [Surface for Business](https://www.microsoft.com/surface/business)
- [Surface IT Pro blog](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/bg-p/SurfaceITPro)
