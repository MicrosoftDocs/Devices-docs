---
title: Wake-on-Power for Surface devices
ms.author: chauncel
author: mccoybot
search.appverid:
- SPO160
- MET150
ms.custom: 
- CI 121602
ms.reviewer: chauncel  
description: Describes how to enable and disable Wake-on-Power for Surface devices.
ms.prod: surface
ms.localizationpriority: medium
ms.topic: how-to
manager: frankbu
ms.date: 12/08/2021
appliesto:
- Windows 10
- Windows 11

---

# Wake-on-Power for Surface devices

Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life. To improve the manageability of these devices, Wake-on-Power enables compatible Surface devices to automatically start when they're reconnected to power. To configure Wake-on-Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.

The Wake-on-Power feature is available on the following devices:

- Surface Pro 9 (commercial SKUs only)
- Surface Pro 9 with 5G
- Surface Pro 8 (commercial SKUs only)
- Surface Pro 7+ (commercial SKUs only)
- Surface Pro X (all SKUs)
- Surface Pro 7 (all SKUs)
- Surface Go 3 (commercial SKUs only)
- Surface Laptop Studio (commercial SKUs only)
- Surface Laptop Studio 2 (commercial SKUs only)
- Surface Book 3 (all SKUs)
- Surface Laptop 5 (commercial SKUs only)
- Surface Laptop 4 (commercial SKUs only)
- Surface Laptop 3 (all SKUs)
- Surface Laptop Go (all SKUs)
- Surface Laptop Go 2 (commercial SKUs only)
- Surface Laptop Go 3 (commercial SKUs only)
- Surface Studio 2+

>[!TIP]
> Commercial SKUs (aka Surface for Business) run Windows 10 Pro/Enterprise or Windows 11 Pro/Enterprise; consumer SKUs run Windows 10/Windows 11 Home. To learn more, see [View your system info](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00).

## Overview and prerequisites

Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.

> [!NOTE]
> This article assumes that you know how to use SEMM. For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.

## To enable Wake-on-Power

1. Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2. Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Select Surface Devices and select Next.":::
3. Select **Start**, and then select **Create** under **Configuration Package**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Select Create Configuration Package.":::
4. Select **Certificate Protection**, and add your certificate .pfx file.
5. Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.
6. On the **Choose which Surface type you want to target** page, select your target devices as appropriate. For example, select **Surface Pro 7**.
7. On the **Advanced Features** page, select **Wake-on-Power**, set the feature to **On**, and then select **Next**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Select Wake-on-Power and set to On.":::
8. On the **Successful** page, select **End**.

    > [!NOTE]
    > If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.
9. Save the .msi package.

## Apply the MSI package

You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager. This procedure includes steps to install the package on your local computer.

1. At an elevated command prompt, enter the full path of the .msi file to run the .msi package.

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2. In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Select OK or disable BitLocker as appropriate.":::
3. On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="One the Welcome page, select Next.":::
4. Restart your device.

Wake-on-Power is now configured. To test the settings, turn off your device, disconnect the power, and then reconnect the power. The device should start automatically.

## References

For more information, see the following articles.

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md)

Still need help? Go to [Microsoft Community](https://answers.microsoft.com/).
