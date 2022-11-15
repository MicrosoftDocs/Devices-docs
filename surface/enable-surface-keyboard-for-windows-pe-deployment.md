---
title: How to enable the Surface Laptop keyboard during MDT deployment 
description: When you use MDT to deploy Windows 10 to Surface laptops, you need to import keyboard drivers to use in the Windows PE environment.
keywords: windows 10 surface, automate, customize, mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 10/25/2022
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
- Surface Laptop 4
- Surface Laptop 5
- Surface Laptop Studio
- Surface Pro 8
- Windows 10
- Windows 11
---

# How to enable the Surface Laptop keyboard during MDT deployment

This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT). You can also apply this information to other deployment methodologies. On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI). However, Surface Laptop requires some additional drivers to enable the keyboard. For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI. For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).

> [!TIP]
> When using keyboard drivers for Surface Laptop 2 and Surface Laptop 3 in the same Windows PE boot instance, you may need to manually reset the firmware if the keyboard or touchpad don’t work in Windows PE:
>
> - Press and hold the Power button for 30 seconds. If you are connected to a power supply unit (PSU), press and hold the Power button until you see the light at the end of the PSU cord briefly turn off before turning back on.

> [!IMPORTANT]
> If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).

## Add keyboard drivers to the selection profile

1. Download the latest Surface Laptop .msi file from the appropriate locations:
    - [Surface Laptop (1st Gen) Drivers and Firmware](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 Drivers and Firmware](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 with Intel Processor Drivers and Firmware](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 with Intel Processor Drivers and Firmware](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 with AMD Processor Drivers and Firmware](https://www.microsoft.com/download/102923)
    - [Surface Laptop 5 with Intel Processor Drivers and Firmware](https://www.microsoft.com/download/104679)
    - [Surface Laptop Studio Drivers and Firmware](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 Drivers and Firmware](https://www.microsoft.com/download/details.aspx?id=103503)

2. Extract the contents of the Surface Laptop .msi file to a folder that you can easily locate (for example, c:\surface_laptop_drivers). To extract the contents, open an elevated Command Prompt window and run the command from the following example:

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.
4. Right-click the **WindowsPEX64** folder and select **Import Drivers**.
5. Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.

 > [!NOTE]
 > Check the downloaded .msi package to determine the format and directory structure.  The directory structure will start with either SurfacePlatformInstaller (older .msi files) or SurfaceUpdate (newer .msi files) depending on when the .msi file was released.

## Import drivers for Surface devices

Import the following folders as appropriate for your Surface Laptop device.

| Device                                    | Import folders                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | More information       |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -----------------------|
| **Surface Laptop Studio**                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol                                                                                                                                                                                                                                                 | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Pro 8**                         | intelthcbase<br>ManagementEngine<br>surfaceacpiplatformextension<br>SurfaceBattery<br>SurfaceCoverClick<br>SurfaceEthernetAdapter<br>SurfaceHidMini<br>SurfaceHotPlug<br>surfaceintegrationdriver<br>SurfaceSar<br>SurfaceSerialHub<br>surfacetimealarmacpifilter<br>surfacetypecoverv7fprude<br>SurfaceUcmUcsiHidClient<br>surfacevirtualfunctionenum<br>tbtslimhostcontroller<br>TglChipset<br>TglSerial                                                                                                                                                                     | n/a  |                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Surface Laptop 5 with Intel processor**  | adlserial<br>alderlakepchpsystem<br>gna<br>heci<br>intelprecisetouch<br>msump64x64sta<br>surfaceacpiplatformextensiondriver<br>surfacebattery<br>surfacebutton<br>surfacedockintegration<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegration<br>surfaceserialhubdriver<br>surfacetimealarmacpifilter<br>tbtslimhostcontroller                                                                                                                                                                                                                                     |  n/a |
| **Surface Laptop 4 with Intel processor** | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 4 with AMD processor**   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient | n/a                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 3 with Intel processor** | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE:<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>itouch<br>Chipset<br>ChipsetLPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| **Surface Laptop 2**                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | For newer .msi files beginning with "SurfaceUpdate", use:<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                               |
| **Surface Laptop (1st Gen)**              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | For newer .msi files beginning with **"SurfaceUpdate"**, use:<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                       |

  > [!TIP]
  > Check the downloaded .msi package to determine the format and directory structure.  The directory structure will start with either SurfacePlatformInstaller (older .msi files) or SurfaceUpdate (Newer .msi files) depending on when the .msi was released.

## Verify imported drivers & configure Windows PE properties

1. Verify that the WindowsPEX64 folder now contains the imported drivers, as shown in the following figure:

   ![Image that shows the newly imported drivers in the WindowsPEX64 folder of the Deployment Workbench.](./images/surface-laptop-keyboard-2.png)
1. Configure a selection profile that uses the WindowsPEX64 folder, as shown in the following figure:

   ![Image that shows the WindowsPEX64 folder selected as part of a selection profile.](./images/surface-laptop-keyboard-3.png)
1. Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:
    - For **Platform**, select **x64**.
    - For **Selection profile**, select the new profile.
    - Select **Include all drivers from the selection profile**.

    ![Image that shows the Windows PE properties of the MDT Deployment Share.](./images/surface-laptop-keyboard-4.png)
4. Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.
    - For Surface Laptop (1st Gen), the model is **Surface Laptop**. The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the following figure.
    - For Surface Laptop 2, the model is **Surface Laptop 2**. The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.
    - For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3. The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.

    ![Image that shows the regular Surface Laptop (1st Gen) drivers in the Surface Laptop folder of the Deployment Workbench.](./images/surface-laptop-keyboard-5.png)

After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).
