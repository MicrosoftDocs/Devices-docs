---
title: Manage Surface UEFI settings 
description: Learn how to manage Surface UEFI settings to enable or disable components, configure security, and adjust boot settings on supported Surface devices. 
ms.localizationpriority: medium
ms.service: surface
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.reviewer: chauncel
manager: frankbu
ms.date: 04/09/2024
appliesto:
- Windows 10
- Windows 11
---


# Manage Surface UEFI settings

Surface devices are designed to use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices. Surface UEFI settings allow IT admins to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.

## Supported products

UEFI management is supported on the following Surface devices:

- Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+ (commercial SKUs only), Surface Pro 8 (commercial SKUs only), Surface Pro 9 & Surface Pro 9 with 5G (commercial SKUs only), Surface Pro 10, Surface Pro (11th Edition), Surface Pro X
- Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3 (Intel processors only), Surface Laptop Go, Surface Laptop 4 (commercial SKUs only), Surface Laptop 5 (commercial SKUs only), Surface Laptop 6 (commercial SKUs only), Surface Laptop (7th Edition), Surface Laptop SE, Surface Laptop Go 2 (commercial SKUs only), Surface Laptop Go 3 (commercial SKUs only)
- Surface Studio (1st Gen), Surface Studio 2, Surface Studio 2+
- Surface Book (all generations)
- Surface Laptop Studio (all generations, commercial SKUs only)
- Surface Go, Surface Go 2[<sup>1</sup>](#references), Surface Go 3 (commercial SKUs only), Surface Go 4 (commercial SKUs only)

>[!TIP]
> Commercial SKUs (aka Surface for Business) run Windows 10 Pro/Enterprise or Windows 11 Pro/Enterprise; consumer SKUs run Windows 10/Windows 11 Home. In UEFI, commercial SKUs are the only models to feature the [Devices page](#uefi-devices-page) and [Management page](#uefi-management-page). To learn more, see [View your system info](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00).

## Support for cloud-based management

With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level. DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings and lays the groundwork for advanced security scenarios in the future.

DFCI is currently available for the following commercial devices: Surface Pro (11th Edition), Surface Pro 10, Surface Pro 10 with 5G, Surface Pro 9, Surface Pro 9 with 5G, Surface Pro 8, Surface Pro 7+, Surface Pro 7, Surface Pro X, Surface Laptop (7th Edition), Surface Laptop 6, Surface Laptop 5, Surface Laptop 4, Surface Laptop 3, Surface Laptop Studio 2, Surface Laptop Studio, Surface Laptop SE, Surface Laptop Go 2, Surface Laptop Go, Surface Book 3, Surface Studio 2+, Surface Go 3, and Surface Go 4. For more information, see [Manage DFCI on Surface devices](surface-manage-dfci-guide.md).

## Open Surface UEFI menu

To adjust UEFI settings during system startup:

1. Shut down your Surface and wait about 10 seconds to ensure it's off.
2. Press and hold the **Volume-up** button and - at the same time - press and release the **Power button.**
3. As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.

## UEFI PC information page

The PC information page includes detailed information about your Surface device:

- **Model** – Your Surface device's model, such as Surface Laptop Studio 2 or Surface Pro 9, is displayed here. The exact configuration of your device isn't shown (such as processor, disk size, or memory size).
- **System UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.

- **Serial number** – This number identifies this specific Surface device for asset tagging and support scenarios.
- **Asset tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](assettag.md).

You can also find detailed information about the firmware of your Surface device. Surface devices have several internal components that each run different versions of firmware. The firmware versions for these components are displayed on the **PC information** page. Components include the following and may vary depending on your device:

- System UEFI
- SMF Controller
- SAM Controller
- Intel Management Engine
- PD Controller
- Keyboard Controller
- Trackpad Controller
- Touch Firmware

:::image type="content" alt-text="System information and firmware version information." source="images/manage-surface-uefi-figure-1.png":::

*Figure 1. System information and firmware version information.*

You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.

## UEFI Security page

:::image type="content" alt-text="Configure Surface UEFI security settings." source="images/manage-surface-uefi-fig4.png":::

*Figure 2. Configure Surface UEFI security settings.*

The Security page allows you to set a password to protect UEFI settings. This password must be entered when you boot the Surface device to UEFI. The password can contain the following characters (as shown in Figure 3):

- Uppercase letters: A-Z

- Lowercase letters: a-z

- Numbers: 1-0

- Special characters: !@#$%^&*()?<>{}[]-_=+|.,;:’`”

The password must be at least six characters and is case-sensitive.

![Add a password to protect Surface UEFI settings.](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*Figure 3. Add a password to protect Surface UEFI settings.*

On the Security page, you can also change the configuration of Secure Boot on your Surface device. Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections. You can disable Secure Boot to allow your Surface device to boot other operating systems or bootable media. You can also configure Secure Boot to work with other certificates, as shown in Figure 4. To learn more, see [Secure Boot](/windows-hardware/design/device-experiences/oem-secure-boot).

![Configure Secure Boot.](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*Figure 4. Configure Secure Boot.*

Depending on your device, you may also see if your TPM is enabled or disabled. If you don't see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5. The TPM is used to authenticate your device's data encryption with BitLocker. To learn more, see [BitLocker overview](/windows/security/information-protection/bitlocker/bitlocker-overview).

![TPM console.](images/manage-surface-uefi-fig5-a.png "TPM console")

*Figure 5. TPM console.*

## UEFI Devices page

The Devices page allows you to turn specific components on eligible devices on or off. Components consist of the following:

- Docking USB port

- MicroSD or SD Card Slot

- Rear Camera

- Front Camera

- Infrared (IR) Camera

- Wi-Fi and Bluetooth

- Onboard Audio (Speakers and Microphone)

Each device has a slider button to move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.

:::image type="content" alt-text="Enable and disable specific devices." source="images/manage-surface-uefi-fig5a.png":::

*Figure 6. Enable and disable specific devices.*

## UEFI Boot configuration page

The Boot Configuration page allows you to change the order of your boot devices and enable or disable the boot of the following devices:

- Windows Boot Manager

- USB Storage

- PXE Network

- Internal Storage

You can boot from a specific device immediately or swipe left on that device's entry in the list using the touchscreen. You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.

For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.

:::image type= "content" alt-text= "Configure the boot order for your Surface device." source=" images/manage-surface-uefi-fig6.png" :::

*Figure 7. Configure the boot order for your Surface device.*

You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example, when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.  

## UEFI Management page

The Management page allows you to manage the use of Zero Touch UEFI Management and other features on eligible devices.

:::image type= "content" alt-text= "Manage access to Zero Touch UEFI Management and other features." source=" images/manage-surface-uefi-fig7a.png" :::

*Figure 8. Manage access to Zero Touch UEFI Management and other features.*

Zero Touch UEFI Management lets you remotely manage UEFI settings using a device profile within Intune called Device Firmware Configuration Interface (DFCI). If you don't configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**. To prevent DFCI, select **Opt-Out**.

## UEFI Exit page

Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.

:::image type="content" alt-text="Exit Surface UEFI and restart the device." source="images/manage-surface-uefi-fig7.png":::

*Figure 9. Select Restart Now to exit Surface UEFI and restart the device.*

## Surface UEFI boot screens

When you update the Surface device firmware using either Windows Update or manual installation, the updates aren't applied immediately to the device but during the next reboot cycle. You can learn more about the Surface firmware update process in [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md). The firmware update progress is displayed on a screen with progress bars of different colors to indicate the firmware for each component. Each component's progress bar is shown in Figures 9 through 18.

![Surface UEFI firmware update with blue progress bar.](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*Figure 10. The Surface UEFI firmware update displays a blue progress bar.*

![System Embedded Controller firmware with green progress bar.](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*Figure 11. The System Embedded Controller firmware update displays a green progress bar.*

![SAM Controller firmware update with orange progress bar.](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*Figure 12. The SAM Controller firmware update displays an orange progress bar.*

![Intel Management Engine firmware with red progress bar.](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*Figure 13. The Intel Management Engine firmware update displays a red progress bar.*

![Surface touch firmware with gray progress bar.](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*Figure 14. The Surface touch firmware update displays a gray progress bar.*

![Surface KIP firmware with light green progress bar.](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*Figure 15. The Surface KIP firmware update displays a light green progress bar.*

![Surface ISH firmware with pink progress bar.](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*Figure 16 The Surface ISH firmware update displays a light pink progress bar.*

![Surface Trackpad firmware with gray progress bar.](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*Figure 17. The Surface Trackpad firmware update displays a pink progress bar.*

![Surface TCON firmware with light gray progress bar.](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*Figure 18. The Surface TCON firmware update displays a light gray progress bar.*

![Surface TPM firmware with light purple progress bar.](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*Figure 19. The Surface TPM firmware update displays a purple progress bar.*

>[!NOTE]
>An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.

![Surface boot screen that indicates Secure Boot has been disabled.](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*Figure 20. Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings.*

## References

1. Surface Go and Surface Go 2 use a third-party UEFI and don't support DFCI.

## Related topics

- [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md)
- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
