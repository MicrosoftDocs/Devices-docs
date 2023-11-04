---
title: "Surface Hub 3 security best practices"
description: "This page explains best practices for Surface Hub 3 security."
ms.prod: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: overview
ms.date: 11/05/2023
ms.localizationpriority: Medium
appliesto:
- Surface Hub 3
---
# Surface Hub 3 security best practices

In today's rapidly evolving digital landscape, ensuring the security of Windows devices is paramount. As IT admins, you are the frontline defense against a myriad of threats that seek to compromise your organization's data, infrastructure, and reputation. This article describes best practices for securing Surface Hub 3 running Microsoft Teams Rooms on Windows:

- [Change default local admin password](#change-default-local-admin-password)
- [Set a UEFI password](#set-a-uefi-password)
- [Physically secure Surface Hub 3](#physically-secure-surface-hub-3)

> [!TIP]
> Before you begin, review the guidance for [Microsoft Teams Rooms security](/microsoftteams/rooms/security?tabs=Windows), which primarily focuses on security for tabletop conference devices: [Teams Rooms certified systems](/microsoftteams/rooms/certified-hardware?tabs=Windows). For Surface Hub 3, start by treating it like any other Windows devices under your scope of management. (JK note: maybe there's a better way to state this but the point here is to stress the importance of ensuring that customers are familiar with the security options explained below so they approach secuirity depending on the needs of their organization)

## Change default local admin password

The default local admin account is a well-known entry point for malicious actors. At a minimum, it's important to change the local admin password on Surface Hub 3. If the default Admin password is not changed immediately after setup, the device may be vulnerable to data breaches, system manipulation, or other unauthorized access. 

### To change local admin password on Surface Hub 3 

1. Sign in with admin credentials and go to **Settings > Accounts > Sign-in options > Password > Change**
2. Enter the current password.
3. Create a new password, confirm the password, and add a hint. To learn more, see [Change or reset your Windows password](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c).

    ![Screenshot showing Change your password](images/hub3-change-admin-password.png)

> [!TIP]
> When joined to Microsoft Entra ID (Azure AD), you can utlize Windows LAPS (Local Administrator Password Solution). Although LAPS doesn't remove local admin accounts, it automatically manages local admin passwords, ensuring they're randomized and securely stored in AD. This reduces the risk associated with stale or widely-known admin passwords. See the section on this page: [Enterprise Management of Surface Hub 3](#enterprise-management-of-surface-hub-3).

## Set a UEFI password

The Unified Extensible Firmware Interface (UEFI) is a specification that defines a software interface between an operating system and platform firmware. By setting a UEFI password, you add an additional layer of security, preventing unauthorized users from making changes to the device's firmware settings. Set a strong UEFI password and ensure it's stored in a secure location. 

Set a UEFI password via the downloable  UEFI Configurator and Surface Enterprise Management Mode (SEMM).

### Enroll Surface Hub 3 into SEMM

You will need a dedicated USB drive with at least 50 MB of storage space.  

1. Download Surface UEFI Configurator from [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).

2. Install UEFI Configurator and select **Start**.
3. Select Configuration Package > DFI
4. Add your organizational Personal Information Exchange (PFE) certificate. 
5. Now you're ready to set a UEFI password. Select **Password Protection**. Enter and confirm your password. Select **Next.**

    ![Screenshot showing screen to set UEFI password](images/uefi-set-pw.png)

6. Select **Hub** as the Surface type you want to target. 
7. Optionally, you can configure components and advanced settings. Otherwise, continue to select Next. 
8. Select your USB drive and click **Build**.
9. Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint. You need these characters when you import the configuration to Surface Hub 3.

## Physically secure Surface Hub 3

Physical security is as crucial a tool as digital security. Devices like the Surface Hub, placed in public conference rooms, can be susceptible to physical damage or tampering. Consider the following steps to protect Surface Hub. 

- **Tamper-evident seals:** Use tamper-evident seals on the device. If someone attempts to open the device, the seal will show signs of tampering.
- **Security cables and locks:** Use security cables and locks to secure the device to a heavy or immovable object, making it difficult for someone to walk away with it.
- **Surveillance:** Depending on the workplace environment, you may opt to install surveillance cameras in the conference room. The mere presence of cameras can deter potential wrongdoers.

## Differences with Windows 10 Team on Surface Hub & Surface Hub 2S

The following security features are no longer enabled by default on Surface Hub 3:

- [BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [User Mode Code Integrity (UMCI)](/surface-hub/surface-hub-security#operating-system-defenses)

### BitLocker

It's recommended to enable to BitLocker by via Intune when joined to Entra ID. To learn more, see [Encrypt Windows devices with BitLocker in Intune - Microsoft Intune](/mem/intune/protect/encrypt-devices).

#### To enable BitLocker on a stand-alone Surface Hub 3:

1. Sign in to Surface Hub 3 with admin credentials.
2. Select Start, enter **Control** and open **Control Panel**. 
3. Select **System & Security** > **BitLocker Drive Encryption** > **Turn on BitLocker.**

![Screenshot showing how to turn on BitLocker via Control Panel](images/hub-3-turn-on-bitlocker.png). 

### User Mode Code Integrity (UMCI)

UMCI enforces code integrity policies and ensures that only trusted code runs in user mode, helping to prevent the execution of malicious or untrusted code. UMCI can be configured with Group Policy when joined to Entra ID or by using PowerShell cmdlets. It is part of a set of features that can be configured with the Windows Defender Application Control (WDAC), which also includes configurable code integrity policies. To learn more, see [Understand Windows Defender Application Control (WDAC) policy rules and file rules](/windows/security/application-security/application-control/windows-defender-application-control/design/select-types-of-rules-to-create)

## Microsoft Teams Rooms Pro Management 

It’s strongly recommended to use a licence for the Microsoft Teams Rooms Pro Management portal, a cloud-based management solution designed to proactively monitor and update Microsoft Teams Rooms devices and their peripherals. This service is intended for organizations aiming to enhance the meeting room experience for end users, facilitated by real-time monitoring and management for Microsoft Teams Rooms devices like Surface Hub 3. 

- **Intelligent Operations**: Utilizes software and machine learning to automate updates, detect problems, and resolve issues for Microsoft Teams Rooms.
- **Timely Security Patches**: Automated update management ensures that security patches are applied promptly as they become available, minimizing the window of vulnerability and protecting devices from known security threats.
- **Update Management**: Automates the orchestration of meeting application and Windows updates based on customer-configurable deployment rings.

To learn more, see [Microsoft Teams Rooms Pro Management](/microsoftteams/rooms/rooms-pro-management)   

### Enterprise Management of Surface Hub 3

It's recommended to join Surface Hub 3 to Microsoft Entra ID (Azure AD) and manage the device using Microsoft Intune or equivalent mobile device management (MDM) solution. The following table describes configuration management options for Intune.

| Feature                           | Description                                                                                                                                                                                                                                                                              | Learn More                                                                                                                                                                                                                                                                 |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Device configuration profiles** | Use Intune's endpoint protection settings to configure Windows Defender, firewall settings, and other security features to protect the device from potential threats.                                                                                                                    | [Create device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-create)                                                                                                                                             |
| **Device compliance policies**    | Ensure the device remains compliant with your organization's security standards. If a device falls out of compliance (e.g., if a required update isn't installed), you can configure automated remediation actions or notifications.                                                     | [Create device compliance policies in Microsoft Intune](/mem/intune/protect/create-compliance-policy)                                                                                                                                     |
| **Update management**             | Use default update management settings to automatically install updates during a nightly maintenance window. Intune provides additional options to customize if needed.                                                                                                                  | [Windows Update settings you can manage with Intune Update Ring policies for Windows 10/11 devices.](/mem/intune/protect/windows-update-settings)                                                                                         |
| **App management**                | Use Intune to manage the apps installed on Surface Hub 3. Ensure only necessary apps related to Teams Rooms functionality are installed and regularly updated.                                                                                                                           | [Manage and secure apps in Intune - Microsoft Intune](/mem/intune/fundamentals/manage-apps)                                                                                                                                               |
| **BitLocker encryption**          | Ensure that the device's storage is encrypted using BitLocker. This protects data in case of unauthorized access or device theft. Note unlike Surface Hub 2S, Bitlocker is not installed by default.                                                                                     | [Encrypt Windows devices with BitLocker in Intune - Microsoft Intune](/mem/intune/protect/encrypt-devices)                                                                                                                                |
|**WindowsLocal Administrator Password Solution**|Windows LAPS automatically manages local admin passwords, ensuring they're randomized and securely stored in Microsoft Entra ID. This reduces the risk associated with stale or widely-known admin passwords.|[Microsoft Intune support for Windows LAPS](/mem/intune/protect/windows-laps-overview)
| **Conditional access**            | Set up conditional access policies to ensure the device can access corporate resources only when it meets specific conditions, such as compliance with security policies.                                                                                                                | [Use Conditional Access with Microsoft Intune compliance policies - Microsoft Intune](/mem/intune/protect/conditional-access)                                                                                                             |
| **Network security**              | Ensure the device is connected to a secure network segment. Use Intune to configure Wi-Fi settings, VPNs, or other network configurations to ensure data in transit is protected.                                                                                                        | [Create a Wi-Fi profile for devices in Microsoft Intune](/mem/intune/configuration/wi-fi-settings-configure)<br> <br>[Network endpoints for Microsoft Intune](/mem/intune/fundamentals/intune-endpoints) |
| **Remote Wipe and Lock**          | In case of any security incidents, ensure you can remotely lock or wipe the device using Intune.                                                                                                                                                                                         | [Retire or wipe devices using Microsoft Intune](/mem/intune/remote-actions/devices-wipe)                                                                                                                                                  |
| **Audit and monitoring**          | Regularly review audit logs and set up alerts for any suspicious activities. Intune integrates with Microsoft Endpoint Manager and other Microsoft security solutions, providing a holistic view of device security.                                                                     | [Audit changes and events in Microsoft Intune](/mem/intune/fundamentals/monitor-audit-logs)                                                                                                                                               |
| **User training**                 | Educate users about not leaving sensitive information visible on the screen.<br> <br>If your organization has Microsoft Purview Data Loss Prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session. | [Data loss prevention and Microsoft Teams](/purview/dlp-microsoft-teams)                                                                                                                                                                  |

### Manage UEFI settings with SEMM

SEMM provides additional security options that you may wish to implement depending on your environment or organization. As shown in the following figure, advanced UEFI settings provide additional options for hardening Surface Hub that you may wish to configure depending on the security posture of your organization.

   ![Screenshot showing advanced UEFI settings for Surface Hub](images/uefi-hub-advanced-settings.png)
   

#### Simultaneous Multi-Threading (SMT)

Commonly known as hyperthreading in Intel processors, SMT allows a single physical CPU core to execute multiple threads concurrently. This can improve performance in multi-threaded applications. However, there are specific scenarios where you might want to control the SMT setting. 
Some vulnerabilities, like certain speculative execution side-channel attacks (for example, L1 Terminal Fault, MDS vulnerabilities), can potentially exploit SMT to access sensitive data. Disabling SMT can mitigate the risk associated with these vulnerabilities, although at the cost of some performance. SMT is enabled by default. 

#### IPv6 for PXE Boot

If your network infrastructure and security controls are primarily designed around IPv4 and are not yet fully equipped to handle IPv6 traffic securely, enabling IPv6 for PXE boot could introduce vulnerabilities. This is because IPv6 might bypass some of the existing security controls that are set up for IPv4.

While enabling IPv6 for PXE boot aligns with the broader industry move towards IPv6 adoption, it's essential to ensure that the network infrastructure, security controls, and operational practices are all equipped to handle IPv6 securely. If not, it might be safer to keep IPv6 for PXE boot disabled until those measures are in place.

#### Alternate Boot & USB Boot

The ability to boot from another source, such as a USB or Ethernet device, provides flexibility for system recovery but can also introduce vulnerabilies: 

- **Unauthorized Operating Systems**: If alternate boot is enabled, an attacker with physical access to the device could boot the system using an unauthorized operating system from a USB drive. This could bypass the security controls of the primary OS.
- **Data Extraction**: An attacker could boot from an external device to a system that allows direct access to the internal storage, potentially extracting sensitive data.
- **Malware Installation**: Booting from an untrusted source could introduce malware, rootkits, or other malicious software at the system level.

Given these implications, organizations in highly secure workplace environments may choose to disable Alternate Boot and USB Boot to reduce the risk of unauthorized access or tampering. 

#### Boot Order Lock

Enabling the "Boot Order Lock" enhances the security posture by ensuring it only boots from authorized sources. Boot Order Lock is disabled by default. 

## Learn more

- [Secure Boot overview](/windows-hardware/design/device-experiences/oem-secure-boot)
- [BitLocker overview](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Application Control overview](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Secure and manage Surface Hub 2S with SEMM and UEFI](/surface-hub/surface-hub-2s-secure-with-uefi-semm)
- [Windows Defender Application Control and virtualization-based protection of code integrity](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)
- [FIPS 140-2 Level 2](/windows/security/threat-protection/fips-140-validation)
- [Common Criteria certification](/windows/security/threat-protection/windows-platform-common-criteria)
