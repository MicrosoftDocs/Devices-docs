---
title: Secure and manage Surface Hub with SEMM
description: Learn more about securing Surface Hub with SEMM.
ms.service: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: how-to
ms.date: 12/04/2023
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S
- Surface Hub 3
---

# Secure and manage Surface Hub with SEMM

You can use [Microsoft Surface Enterprise Management Mode](/surface/surface-enterprise-management-mode) (SEMM) to manage UEFI settings on one or more Surface Hub devices. Use the Microsoft Surface UEFI Configurator to control the following components:

- On-board Audio
- Wired LAN
- Bluetooth
- Wi-Fi
- Occupancy sensor

Use the Microsoft Surface UEFI Configurator to turn on or off the following UEFI settings:

**Security**

- SMT (Simultaneous Multi-Threading)

**Boot**

- IPv6 for PXE Boot
- Alternate Boot
- Boot Order Lock
- USB Boot

**UEFI Front Page**

- Devices
- Boot
- Date/Time

> [!TIP]
> To learn more about the security implications of configuring SEMM settings, see [Manage UEFI settings with SEMM](/surface-hub/surface-hub-3-security#manage-uefi-settings-with-semm)

## Create UEFI configuration image

Unlike other Surface devices, you cannot use an MSI file or a Win PE image to apply these settings on Surface Hub. Instead, you need to create a USB image to load into the device. 

> [!NOTE]
> This article assumes that you either obtain certificates from a third-party provider or already have expertise in PKI certificate services and know how to create your own. See [Certificate Services Architecture](/windows/win32/seccrypto/certificate-services-architecture) documentation to learn more.


### Download Surface IT Toolkit and Surface Hub 2S Drivers and Firmware

On a separate PC, perform the following tasks:

1. Download the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703), which includes the [Surface UEFI Configurator](/surface/surface-it-toolkit-uefi-config).
2. Follow the installation instructions in [Get started with Surface IT Toolkit](/surface/surface-it-toolkit#get-started-with-surface-it-toolkit).
3. Download the [Surface Hub 2S drivers and firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974), **SurfaceHub2S_Win10_19045_24.043.31687.0.MSI**, to use during the new OS installation.

### Prepare the SEMM certificate

Before using the UEFI Configurator for the first time, prepare a certificate to secure the SEMM package:

- **Large enterprises** should generate certificates using their established security infrastructure.
- **Medium-sized businesses** may opt for certificates from trusted partner providers, especially if they lack dedicated IT security resources.
- **Self-signed certificates** can be created using PowerShell for smaller setups. For details, refer to [Self-signed certificate guide](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) and [Surface Enterprise Management Mode certificate requirements](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).

>[!WARNING]
>To unenroll a device from SEMM and restore user control of Surface UEFI settings, you must have the SEMM certificate used to enroll the device in SEMM. If this certificate becomes lost or corrupted, it is not possible to unenroll from SEMM. Back up and protect your SEMM certificate accordingly.

### Create a SEMM package

To create a SEMM package for Surface Hub, follow these steps using the Surface IT Toolkit on a separate PC:

1. Open the [Surface IT Toolkit](/surface/surface-it-toolkit), select **UEFI Configurator**, and then choose **Configure devices**.

    :::image type="content" alt-text="Screenshot of Surface UEFI Configurator start screen." source="images/uefi-config-hub.png":::

2. On the Device Configuration and Certification page, configure the items as follows, then select **Next**:
   - **Choose Deployment Build**: Select **DFI**.
   - **Import Certificate Protection**: Select **Add**, browse to select your certificate (.pfx file), and enter the associated password.
   - **Choose DFI Package Type**: Select **Configuration Package**.
   - **Select Device**: Choose **Surface Hub** and **Surface Hub 2S** or Surface Hub 3.

    :::image type="content" alt-text="Screenshot of Device Configuration and Certification." source="images/uefi-config-device.png":::

3. Navigate to the Device Configuration Settings page:
   - Go to **Advanced Settings**, select **UEFI Front Page**.......

4. Insert a USB drive into your PC. This drive will be formatted, and all files on it will be erased. Select **Create** to build the SEMM package.

    :::image type="content" alt-text="Screenshot that shows creation of SEMM package for Surface Hub 2S." source="images/create-hub-semm-package.png":::

5. Upon completion, note the last two characters of the certificate thumbprint displayed, then select **Finish**. Your SEMM package, named *DfciUpdate.dfi*, is now ready for use.

    :::image type="content" alt-text="Screenshot that shows successful creation of SEMM package for Surface Hub 2S." source="images/finish-create-hub-semm-package.png":::



4. Enter the certificate’s private key’s password.

    ![Screenshot that shows screen to enter the certificate’s private key’s password.](images/uefi-hub-cert-pw.png)

5. After importing the private key, you have the option of setting a UEFI password, a recommended security best practice.

    ![Screenshot showing screen to set UEFI password](images/uefi-set-pw.png)

6. Choose **Surface Hub 2S** or **Surface Hub 3** as the target for the UEFI configuration package.

    ![* Choose Surface Hub 2S or Surface Hub 3 as the target for the UEFI configuration package *.](images/uefi-hub-choose.png)

7. Choose the components that you want to activate or deactivate and select **Next**.

   ![Screenshot showing components to activate or deactivate.](images/uefi-hub-components.png)

8. Choose the advanced settings that you wish to configure and select **Next**.

   ![Screenshot showing advanced settings to turn on or off.](images/uefi-hub-advanced.png).

9. Connect a USB drive and select **Build** to export the file.

    ![Screenshot showing screen to build UEFI DFI Package](images/uefi-hub-build.png)

10. Upon successful creation of the package, the Configurator displays the last two characters of your certificate's thumbprint. You need these characters when you import the configuration to Surface Hub 3.

    ![Screenshot showing UEFI Configurator completion](images/uefi-hub-end.png)

## Apply SEMM package to Surface Hub 2S or Surface Hub 3

To apply the package and enroll a Surface Hub into SEMM, insert the USB drive into the USB-A port and boot directly into the UEFI menu.

1. Turn off Surface Hub. Press and hold the **Volume up** button and press the **Power** Button. Keep holding the **Volume up** button until the UEFI menu appears.

## Learn more

- [Security best practices for Surface Hubs running Microsoft Teams Rooms on Windows](surface-hub-3-security.md)