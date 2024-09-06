---
title: Downgrade to Windows 10
description: Explore options for downgrading to Windows 10 from Windows 11, including manual and bulk methods, and licensing considerations for commercial customers. 
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 06/11/2024
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---

# Downgrade to Windows 10

> [!IMPORTANT]
> When Windows 10 reaches end of support (EOS) on October 14, 2025, Microsoft will no longer release security updates, bug fixes, time zone updates, or technical support from Microsoft. To learn more, including transition options for organizations needing more time, see [Plan for Windows 10 EOS with Windows 11, Windows 365, and ESU](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/plan-for-windows-10-eos-with-windows-11-windows-365-and-esu/ba-p/4000414).

> [!NOTE]
> Effective March 31, 2024, Microsoft no longer offers Windows 10 Pro as a downgrade choice in operating systems on devices delivered from the factory. PC manufacturers can no longer install Windows 10 Pro on Windows 11 Pro PCs during manufacturing. Any current stock of devices with Windows 10 preinstalled is only available while supplies last. The right for customers to install Windows 10 Pro on OEM-licensed versions of Windows 11 Pro continues while Windows 10 Pro is still supported.

## Windows 10 final version

Windows 10 version 22H2 is the [final version of Windows 10](/windows/release-health/release-information) with monthly security updates continuing through October 14, 2025. (The Windows 10 IoT Enterprise Long-Term Servicing Channel (LTSC) and Windows 10 IoT Enterprise will continue to receive updates based on their specific lifecycles.)

## Downgrade from Windows 11 to Windows 10 via BMR

You can manually downgrade Windows Pro or Enterprise editions with a Surface Bare Metal Recovery (BMR) file designed for this purpose.

- [Downgrade individual devices to Windows 10](#downgrade-individual-devices-to-windows-10)
- [Manage downgrade of multiple devices](#manage-downgrade-of-multiple-devices-to-windows-10)

### Licensing considerations

Use one of the following options:

- Use the downgrade rights allowed by the OEM End User License Agreement (EULA). This means you can install Windows 10 Pro on a Surface Device that has a Windows 11 Pro license, as long as you comply with the terms and conditions of the OEM EULA.
- Use the Software Assurance rights with volume license agreements. This means that you can run Windows 10 Pro on a Surface device that has a Windows 11 Pro license, as long as you have a valid volume license agreement that covers the device and the operating system.

## Downgrade individual devices to Windows 10

This section explains how to manually downgrade an individual Surface device to Windows 10.

> [!NOTE]
> Some newer Surface devices are not compatible with Windows 10, including Surface Pro (11th Edition), Surface Pro 10 with 5G, Surface Laptop (7th Edition), and Surface Laptop Studio 2.

1. **Prepare your Surface device**:
   - Ensure that all important data on the device is backed up. To learn more, see [Back up your Windows PC](https://support.microsoft.com/windows/back-up-your-windows-pc-87a81f8a-78fa-456e-b521-ac0560e32338#ID0EBF=Windows_11) and view the following video:

   > [!VIDEO https://www.microsoft.com/videoplayer/embed/RW1g7Ie?]

2. **Download the Windows 10 BMR file for your device**:
   - Go to [Surface Recovery Image Download](https://support.microsoft.com/surface-recovery-image), sign in, and select your device from the dropdown list.
   - Follow the instructions.

5. **Post-installation checks**:
   - After the setup is complete, verify that all device drivers are correctly installed and updated for Windows 10. To learn more, see [Update drivers manually in Windows](https://support.microsoft.com/windows/update-drivers-manually-in-windows-ec62f46c-ff14-c91d-eead-d7126dc1f7b6).
   - Restore any previously backed-up data to the device. Follow the [Restore a backup](https://support.microsoft.com/windows/back-up-your-windows-pc-87a81f8a-78fa-456e-b521-ac0560e32338#ID0EBF=Windows_10) instructions and view the following video.

   > [!VIDEO https://www.microsoft.com/videoplayer/embed/RW1ga0E?]

6. **Additional recommendations**:
   - Check for any available updates in Windows Update to ensure your Windows 10 installation is up to date. Go to **Start** > **Settings** > **Update & Security** > **Windows Update**.
   - Reinstall any applications that were removed during the downgrade process. If you backed up your device with OneDrive, sign in to OneDrive with the same Microsoft account you used to make the original backup. You can also check your Download folder for any previously downloaded apps: Select the app and follow the prompts to reinstall.

## Manage downgrade of multiple devices to Windows 10

In a commercial organization, IT admins can create a Windows 10 custom image with the appropriate BMR and drivers.

1. **Download the Windows 10 MSI file**:
   - Go to [Manage & deploy Surface driver & firmware updates](/surface/manage-surface-driver-and-firmware-updates#download-msi-files) and select the appropriate MSI for your device.
   - Select **Download** to display the available MSI files for your device.
   - As an example, for Surface Laptop 5, select the MSI download for Windows 10 (look for **win10** in the file name) and select **Download**:

   :::image type="content" source="images/download-win10-msi-example.png" alt-text="Screenshot that shows selection of Windows 10 MSI file.":::

2. Integrate the MSI or the drivers/firmware from the MSI with the appropriate deployment tool for your environment.

- Examples include: [Microsoft Endpoint Configuration Manager](/mem/configmgr) including [Microsoft Deployment Toolkit (MDT)](/mem/configmgr/mdt/), [PowerShell](/powershell/), [DISM - Deployment Image Servicing and Management](/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows), or third-party solutions.

> [!IMPORTANT]
> After Windows 10 EOS, on October 14, 2025, Windows 10 MSI files for Surface devices will no longer be updated with newer drivers and firmware.

### Learn more

- [Surface for Business](https://www.microsoft.com/surface/business)
