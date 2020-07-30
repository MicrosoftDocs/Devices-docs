---
title: How to enable Wake on Power for Surface
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom: 
- CI 121602
ms.reviewer: johnk@cadencepreferred.com  
description: Describes how to enable and disable Wake on Power for Surface devices.
keywords: update, deploy, driver, wol, wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
---

# Wake on Power for Surface devices

Surface devices can be powered off while away from the desk or set to hibernate mode to save battery. To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when reconnected to power. Configuring Wake on Power requires using Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.

Wake on Power is a feature available on the following devices:

- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X 

## Overview and prerequisites

You can use the Surface UEFI Configurator to configure individual UEFI settings that are saved in a Windows Installer .msi package for distribution to target devices. 

> [!NOTE]
> This article assumes that you are familiar with using SEMM. For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.

## To enable Wake on Power

1.	Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).
2.	Sign into your Surface device as an Administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="Select Surface Devices and select Next.":::
3.	Select **Start** and then under **Configuration Package** select **Create**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="Select Create Configuration Package.":::
4.	Select **Certificate Protection** and add your certificate .pfx file. After entering your password, select **Next**. Add **Password Protection**, as appropriate, and then select **Next**.
5.	On the **Choose which Surface type you want to target** page, select your target devices as appropriate. For example, **Surface Pro 7**.
6.	On the **Advanced Features** page, select **Wake on Power** and set to **On**. Select **Next**.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="Select Wake on Power and set to On."::: 
7.	On the **Successful** page, select **End**. If this is your first time providing settings to your device, you will be prompted to provide the last two characters of the certificate thumbprint. 
8.	Save the .msi package. 

## Apply the MSI package 

You can apply the MSI package to devices across your network using software distribution tools such as Microsoft Endpoint Configuration Manager. This procedure includes steps for installing the package on your local machine. 

1.	Open an elevated command prompt and enter the full path of the .msi file to run the .msi package. 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.	On the **Warning** dialog box, select **OK** or disable Bitlocker as appropriate.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="Select OK or disable Bitlocker as appropriate.":::
3.	On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="One the Welcome page, select Next.":::
4.	Restart your device. 

Wake on Power is now configured. To test the setting, turn off your device, disconnect the power, and then reconnect the power. The device will start automatically. 

## More information

For more information, see the following articles. 

- [Surface Enterprise Management Mode](surface-enterprise-management-mode.md)
- [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md)

Still need help? Go to [Microsoft Community](https://answers.microsoft.com/).