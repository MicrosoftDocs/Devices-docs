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

- [Change or remove the default local admin account](#change-or-remove-the-default-local-admin-account)
- [Set a UEFI password](#set-a-uefi-password)
- [Physically secure Surface Hub 3](#physically-secure-surface-hub-3)

## Change or remove the default local admin account

The default local admin account is a well-known entry point for malicious actors. If the default Admin password is not changed immediately after setup, there are several potential risks:

- **Unauthorized access**: The most immediate risk is that unauthorized individuals can easily access the system. Since the default password is likely known or can be easily found, it becomes a weak point for security.
- **Data breach**: Once inside the system, malicious actors can potentially access sensitive data, including meeting information, logs, or any other stored data.
- **System manipulation**: Unauthorized users can change settings, install malicious software, or alter the system in ways that can compromise its functionality or security.

### To change local admin password on Surface Hub 3 

1. Go to **Settings > Accounts > Sign-in options > Password > Change**
2. Enter the current password.
3. Create a new password, confirm the password, and add a hint.

### Remove the admin password 

Consider joining the device to Microsoft Entra ID (formerly named Azure AD). By doing so, you can enable a policy that removes the local admin password. (WIP - expand this)

## Set a UEFI password

The Unified Extensible Firmware Interface (UEFI) is a specification that defines a software interface between an operating system and platform firmware. By setting a UEFI password, you add an additional layer of security, preventing unauthorized users from making changes to the device's firmware settings. Set a strong UEFI password and ensure it's stored in a secure location. This password should be complex, combining letters, numbers, and special characters. 

It's recommended to set a UEFI password using Surface Enterprise Management Mode (SEMM). 

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
9. Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint. You need these characters when you import to the configuration to Surface Hub 3.

### Manage UEFI settings with SEMM

SEMM provides additional security options that you may wish to implement depending on your environment or organization. 

   ![Screenshot showing advanced UEFI settings for Surface Hub](images/uefi-hub-advanced-settings.png)
   
#### Simultaneous Multi-Threading (SMT)

Commonly known as hyperthreading in Intel processors, SMT allows a single physical CPU core to execute multiple threads concurrently. This can improve performance in multi-threaded applications. However, there are specific scenarios where you might want to control the SMT setting. 

Some vulnerabilities, like certain speculative execution side-channel attacks (e.g., L1 Terminal Fault, MDS vulnerabilities), can potentially exploit SMT to access sensitive data. Disabling SMT can mitigate the risk associated with these vulnerabilities, although at the cost of some performance. SMT is enabled by default. 

#### Alternate Boot

The ability to boot from another source, such as a USB or Ethernet device, provides flexibility but can also introduce vulnerabilies: 

- **Unauthorized Operating Systems**: If alternate boot is enabled, an attacker with physical access to the device could boot the system using an unauthorized operating system from a USB drive. This could bypass the security controls of the primary OS.
- **Data Extraction**: An attacker could boot from an external device to a system that allows direct access to the internal storage, potentially extracting sensitive data.
- **Malware Installation**: Booting from an untrusted source could introduce malware, rootkits, or other malicious software at the system level.
- **Bypassing Disk Encryption**: While strong disk encryption like BitLocker should prevent unauthorized access to data, booting from an alternate device might provide an attacker with tools or methods to attempt to circumvent this encryption.

Given these implications, many organizations with a strong focus on security disable alternate boot options on devices to reduce the risk of unauthorized access or tampering. While the alternate boot option provides flexibility and can be beneficial in certain scenarios, it also introduces potential security risks. Organizations should weigh these risks against the benefits and decide on the appropriate configuration based on their security posture and operational needs.

#### WIP - other settings

## Physically secure Surface Hub 3

Physical security is as crucial a tool as digital security. Devices like the Surface Hub, placed in public conference rooms, can be susceptible to physical damage or tampering. Consider the following steps to protect Surface Hub. 

- **Tamper-evident seals:** Use tamper-evident seals on the device. If someone attempts to open the device, the seal will show signs of tampering.
- **Security cables and locks:** Use security cables and locks to secure the device to a heavy or immovable object, making it difficult for someone to walk away with it.
- **Surveillance:** Depending on the workplace environment, you can opt to install surveillance cameras in the conference room. The mere presence of cameras can deter potential wrongdoers.

## Microsoft Teams Rooms Pro Management 

It’s strongly recommended to use a licence for the Microsoft Teams Rooms Pro Management portal, a cloud-based management solution designed to proactively monitor and update Microsoft Teams Rooms devices and their peripherals. This service is intended for organizations aiming to enhance the meeting room experience for end users, facilitated by real-time monitoring and management for Microsoft Teams Rooms devices like Surface Hub 3. 

- **Intelligent Operations**: Utilizes software and machine learning to automate updates, detect problems, and resolve issues for Microsoft Teams Rooms.
- **Timely Security Patches**: Automated update management ensures that security patches are applied promptly as they become available, minimizing the window of vulnerability and protecting devices from known security threats.
- **Update Management**: Automates the orchestration of meeting application and Windows updates based on customer-configurable deployment rings.

To learn more, see [Microsoft Teams Rooms Pro Management](/microsoftteams/rooms/rooms-pro-management)

## Differences with Windows 10 Team Edition

The following security features are not enabled by default on Surface Hub 3: 

- BitLocker 
- Code integrity policy

## Learn more

- [Secure Boot overview](/windows-hardware/design/device-experiences/oem-secure-boot)
- [BitLocker overview](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Application Control overview](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Secure and manage Surface Hub 2S with SEMM and UEFI](/surface-hub/surface-hub-2s-secure-with-uefi-semm)
- [Windows Defender Application Control and virtualization-based protection of code integrity](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)
- [FIPS 140-2 Level 2](/windows/security/threat-protection/fips-140-validation)
- [Common Criteria certification](/windows/security/threat-protection/windows-platform-common-criteria)
