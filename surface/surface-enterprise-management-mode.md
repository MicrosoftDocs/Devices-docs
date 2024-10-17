---
title: Get started with Surface Enterprise Management Mode (SEMM)
description: See how this feature of Surface devices with Surface UEFI helps you secure and manage firmware settings within your organization.
ms.service: surface
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.reviewer: chauncel
manager: frankbu
ms.localizationpriority: medium
ms.date: 04/25/2023
appliesto:
- Windows 10
- Windows 11
---

# Get started with Surface Enterprise Management Mode (SEMM)

Microsoft Surface Enterprise Management Mode (SEMM) is a feature of Surface devices with Surface Unified Extensible Firmware Interface (UEFI). You can use SEMM to:

- Secure and manage firmware settings in your organization.
- Prepare UEFI settings configurations and install them on a Surface device.

SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal. 

## Enroll Surface devices into SEMM

This article shows you how to create a Surface UEFI configuration package to enable or disable hardware components at the firmware level and enroll a Surface device in SEMM. When Surface devices are configured by SEMM and secured with the SEMM certificate, they're considered *enrolled* in SEMM. When the SEMM certificate is removed and control of UEFI settings is returned to the user of the device, the Surface device is considered *unenrolled* in SEMM.

You can also [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](use-system-center-configuration-manager-to-manage-devices-with-semm.md).

As an alternative to SEMM, newer Surface devices support remote management of a subset of firmware settings via Microsoft Intune. For more information, see [Manage DFCI on Surface devices](surface-manage-dfci-guide.md).

## Supported devices

SEMM is only available on devices with Surface UEFI firmware including:

- Surface Book (all generations)
- Surface Go 4 (commercial SKUs only)
- Surface Go 3 (commercial SKUs only)
- Surface Go 2 (all SKUs)
- Surface Go (all SKUs)
- Surface Hub 2S
- Surface Laptop (7th Edition) (commercial SKUs only)
- Surface Laptop 6 (commercial SKUs only)
- Surface Laptop 5 (commercial SKUs only)
- Surface Laptop 4 (commercial SKUs only)
- Surface Laptop 3 (Intel processors only)
- Surface Laptop 2 (all SKUs)
- Surface Laptop (all SKUs)
- Surface Laptop Go 3 (commercial SKUs only)
- Surface Laptop Go 2 (commercial SKUs only)
- Surface Laptop Go (all SKUs)
- Surface Laptop SE (all SKUs)
- Surface Laptop Studio 2 (commercial SKUs only)
- Surface Laptop Studio (commercial SKUs only)
- Surface Pro (11th Edition) (commercial SKUs only)
- Surface Pro 10 (commercial SKUs only)
- Surface Pro 10 with 5G (commercial SKUs only)
- Surface Pro 9 (commercial SKUs only)
- Surface Pro 9 with 5G (commercial SKUs only)
- Surface Pro 8 (commercial SKUs only)
- Surface Pro 7+ (commercial SKUs only)
- Surface Pro 7 (all SKUs)
- Surface Pro 6 (all SKUs)
- Surface Pro 5th Gen (all SKUs)
- Surface Pro 4 (all SKUs)
- Surface Pro X (all SKUs)
- Surface Studio 2+ (commercial SKUs only)
- Surface Studio 2 (all SKUs)
- Surface Studio (all SKUs)

>[!TIP]
> Commercial SKUs (aka Surface for Business) run Windows 10 Pro/Enterprise or Windows 11 Pro/Enterprise; consumer SKUs run Windows 10/Windows 11 Home. To learn more, see [View your system info](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00).

## Surface UEFI Configurator

The primary workspace of SEMM is the [Surface IT Toolkit](surface-it-toolkit.md), which contains the new [Surface UEFI Configurator](surface-it-toolkit-uefi-config.md). 

### Configuration package

Surface UEFI configuration packages are the primary mechanism to implement and manage SEMM on Surface devices. These packages contain a configuration file and a certificate file, as shown in Figure 2. The configuration file contains UEFI settings that are specified when the package is created in Microsoft Surface UEFI Configurator. When a configuration package runs for the first time on a Surface device that's not already enrolled in SEMM, it provisions the certificate file in the device’s firmware and enrolls the device in SEMM. When enrolling a device in SEMM, and before the certificate is stored and the enrollment finishes, you're prompted to confirm the operation by providing the last two digits of the SEMM certificate thumbprint. This confirmation requires a user to be physically present at the device during enrollment to perform the confirmation.

For more information about the requirements for the SEMM certificate, see the [Surface Enterprise Management Mode certificate requirements](#semm-certificate-requirements) section later in this article.

Use Surface UEFI Configurator to create

| Category     | Description                                                                                                 | Learn more   |
| ------------ | ----------------------------------------------------------------------------------------------------------- |----|
| **MSI Packages** | **Enroll Surface devices** into SEMM and manage UEFI firmware settings for enrolled devices. <br> **Enroll Surface docks** into SEMM and manage UEFI firmware settings for enrolled docks.  |[Configure UEFI settings for Surface devices](surface-it-toolkit-uefi-config.md)<br> [Configure UEFI settings for Surface Docks](secure-surface-dock-ports-semm.md)      |
| **WinPE Image**s | Use WinPE images to enroll, configure, and unenroll SEMM on a Surface device.                              |
| **DFI Packages** | Create DFI packages to enroll Surface Hub devices into SEMM and manage UEFI firmware settings for enrolled Surface Hub devices. |

> [!TIP]
> You have the option to require a UEFI password with SEMM. If you do, the password is required to view the **Security**, **Devices**, **Boot Configuration**, and **Enterprise Management** pages of Surface UEFI.

After a device is enrolled in SEMM, the configuration file is read, and the settings specified in the file are applied to UEFI. When you run a configuration package on a device that's already enrolled in SEMM, the signature of the configuration file is checked against the certificate that's stored in the device firmware. If the signature doesn't match, no changes are applied to the device.

> [!TIP]
> Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr. To view the thumbprint with CertMgr:
>
>1. Select and hold (or right-click) the .pfx file, and then select **Open**.
>2. In the navigation pane, expand the folder.
>3. Select **Certificates**.
>4. In the main pane, select and hold (or right-click) your certificate, and then select **Open**.
>5. Select the **Details** tab.
>6. In the **Show** drop-down menu, **All** or **Properties Only** must be selected.
>7. Select the **Thumbprint** field.

To enroll a Surface device in SEMM or apply the UEFI configuration from a configuration package, run the .msi file with administrative privileges on the intended Surface device. You can use application deployment or operating system deployment technologies, like [Microsoft Endpoint Configuration Manager](/mem/configmgr) or the [Microsoft Deployment Toolkit](/mem/configmgr/mdt). When you enroll a device in SEMM, you must be physically present to confirm the enrollment on the device. When you apply a configuration to devices that are already enrolled in SEMM, user interaction isn’t required.

### Recovery request

 You can unenroll Surface devices from SEMM via the [Recovery Request](unenroll-surface-devices-from-semm.md) feature in the Surface IT Toolkit.

## SEMM certificate requirements

When you use SEMM with Microsoft Surface UEFI Configurator and want to apply UEFI settings, a certificate is required to verify the signature of configuration files. This certificate ensures that after a device enrolls in SEMM, only packages created with the approved certificate can be used to modify the UEFI settings.

>[!NOTE]
>To make any modification to SEMM or Surface UEFI settings on enrolled Surface devices, the SEMM certificate is required. If the SEMM certificate is corrupt or lost, SEMM can’t be removed or reset. Manage your SEMM certificate accordingly with an appropriate solution for backup and recovery

Packages created with the Microsoft Surface UEFI Configurator tool are signed with a certificate. This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.

### Recommended certificate settings

The following settings are recommended for the SEMM certificate:

- **Key Algorithm** – RSA
- **Key Length** – 2048
- **Hash Algorithm** – SHA-256
- **Type** – SSL Server Authentication
- **Key Usage** – Digital signature, Key Encipherment
- **Provider** – Microsoft Enhanced RSA and AES Cryptographic Provider
- **Expiration Date** – 15 Months from certificate creation
- **Key Export Policy** – Exportable

It's also recommended that the SEMM certificate is authenticated in a two-tier public key infrastructure (PKI) architecture where the intermediate certification authority (CA) is dedicated to SEMM, enabling certificate revocation. For more information about a two-tier PKI configuration, see [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831348(v=ws.11)).

### Self-signed certificate

You can use the following example PowerShell script to create a self-signed certificate for use in proof-of-concept scenarios.
To use this script, copy the following text into Notepad, and then save the file as a PowerShell script (.ps1).

> [!NOTE]
> This script creates a certificate with a password of `12345678`. The certificate generated by this script isn't recommended for production environments.
  
```powershell
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
```

>[!IMPORTANT]
>For use with SEMM and Microsoft Surface UEFI Configurator, the certificate must be exported with the private key and with password protection. Microsoft Surface UEFI Configurator prompts you to select the SEMM certificate file (.pfx) and certificate password.

To create a self-signed certificate:

1. On your C: drive, create the folder where you'll save the script; for example, C:\SEMM.
2. Copy the example script into Notepad (or equivalent text editor), and then save the file as a PowerShell script (.ps1).
3. Sign in to your computer with administrator credentials, and then open an elevated PowerShell session.
4. Make sure that your permissions are set to allow scripts to run. By default, scripts are blocked from running unless you modify the execution policy. To learn more, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
5. At the command prompt, enter the full path of the script and then press **Enter**. The script creates a Demo Certificate named TempOwner.pfx.

Alternatively, you can create your own self-signed certificate using PowerShell. For more information, see [New-SelfSignedCertificate](/powershell/module/pki/new-selfsignedcertificate?view=windowsserver2022-ps&preserve-view=true).

>[!NOTE]
>For organizations that use an offline root in their PKI infrastructure, Microsoft Surface UEFI Configurator must be run in an environment connected to the root CA to authenticate the SEMM certificate. The packages generated by Microsoft Surface UEFI Configurator can be transferred as files, so they can be transferred outside the offline network environment with removable storage, such as a USB stick.

### Managing certificates FAQ

The recommended *minimum* length is 15 months. You can use a certificate that expires in less than 15 months or use a certificate that expires in longer than 15 months.

>[!NOTE]
>When a certificate expires, it doesn't automatically renew.

**Will an expired certificate affect the functionality of SEMM-enrolled devices?**<br><br>
No, a certificate only impacts IT admin management tasks in SEMM and has no effect on device functionality when it expires.

**Will the SEMM package and certificate need to be updated on all machines that have it?**<br><br>
If you want SEMM reset or recovery to work, the certificate needs to be
valid and not expired.

**Can bulk reset packages be created for each surface that we order? Can one be built that resets all machines in our environment?**<br><br>
The PowerShell samples that create a config package for a specific device type can also be used to create a reset package that's serial-number independent. If the certificate is still valid, you can create a reset package using PowerShell to reset SEMM.

