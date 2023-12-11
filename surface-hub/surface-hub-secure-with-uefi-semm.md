---
title: "Secure and manage Surface Hub with SEMM"
description: "Learn more about securing Surface Hub with SEMM."
ms.prod: surface-hub
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

You can use Surface Enterprise Management Mode (SEMM) to manage UEFI settings on one or more Surface Hub devices. Use the Microsoft Surface UEFI Configurator to control the following components:

- Wired LAN
- Cameras
- Bluetooth
- Wi-Fi
- Occupancy sensor

Use the Microsoft Surface UEFI Configurator to turn on or off the following UEFI settings:

- Boot

  - IPv6 for PXE Boot
  - Alternate Boot
  - Boot Order Lock
  - USB Boot
  - UEFI Front Page

  - Devices
  - Boot
  - Date/Time

## Create UEFI configuration image

Unlike other Surface devices, you cannot use an MSI file or a Win PE image to apply these settings on Surface Hub. Instead, you need to create a USB image to load into the device. To create a Surface Hub UEFI configuration image, download and install the latest version of the Microsoft Surface UEFI Configurator from [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).For more information about using UEFI and SEMM, see [Microsoft Surface Enterprise Management Mode](/surface/surface-enterprise-management-mode).

## To configure UEFI on Surface Hub

1. Open **UEFI Configurator** and select **Start**.

    ![Screenshot showing UEFI Configurator Start](images/uefi-hub-start.png)

3. Select **Configuration Package** > **DFI**.

    ![Screenshot showing screen to select DFI File](images/uefi-hub-dfi.png)

4. Add your organizational Personal Information Exchange (PFE) certificate.

> [!NOTE]
> This article assumes that you either obtain certificates from a third-party provider or already have expertise in PKI certificate services and know how to create your own. See [Certificate Services Architecture](/windows/win32/seccrypto/certificate-services-architecture) documentation to learn more.


1. Enter the certificate’s private key’s password.<br>
![* Enter the certificate’s private key’s password *.](images/uefi-hub-cert-pw.png) <br><br>
1. After importing the private key, you have the option of setting a UEFI password, a recommended security best practice.<br>
![* Set UEFI password*.](images/sh2-uefi4.png) <br><br>
1. Choose **Surface Hub 2S** or **Surface Hub 3** as the target for the UEFI configuration package.<br>
![* Choose Surface Hub 2S or Surface Hub 3 as the target for the UEFI configuration package *.](images/sh2-uefi5.png) <br><br>
1. Choose the components and settings you want to activate or deactivate on Surface Hub.<br>
![* Choose the components and settings you want to activate or deactivate *.](images/sh2-uefi6.png) <br><br>
1. Use the USB option to export the file.<br>
![* Use the USB option to export the file *.](images/sh2-uefi8.png) <br><br>
1. Insert and choose the USB drive you’d like to use for this package. The USB drive will be formatted and you lose any information you have on it.<br>
![* Insert and choose the USB drive for your package  *.](images/sh2-uefi9.png) <br><br>
1. Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint. You need these characters when you import to the configuration to Surface Hub.<br>
![* Successful configuration of package *.](images/sh2-uefi10.png) <br>

## To boot into UEFI

Turn off Surface Hub. Press and hold the **Volume Up** button and press the **Power** Button. Keep holding the Volume Up button until the UEFI menu appears.
