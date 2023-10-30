---
title: "Surface Hub 3 security best practices"
description: "This page explains best practices for Surface Hub 3 security."
ms.prod: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: overview
ms.date: 11/15/2023
ms.localizationpriority: Medium
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

Consider joining the device to Azure AD. By doing so, you can enable a policy that removes the local admin password. (WIP - expand this)

## Set a UEFI password

The Unified Extensible Firmware Interface (UEFI) is a specification that defines a software interface between an operating system and platform firmware. By setting a UEFI password, you add an additional layer of security, preventing unauthorized users from making changes to the device's firmware settings.
Set a strong UEFI password and ensure it's stored in a secure location. This password should be complex, combining letters, numbers, and special characters.

### Enroll Surface Hub 3 into SEMM

1. WIP: add steps to set password

## Physically secure Surface Hub 3

Physical security is as crucia tol as digital security. Devices like the Surface Hub, placed in public conference rooms, can be susceptible physical damage or tampering.

- **Tamper-evident seals:** Use tamper-evident seals on the device. If someone attempts to open the device, the seal will show signs of tampering.
- **Security cables and locks:** Use security cables and locks to secure the device to a heavy or immovable object, making it difficult for someone to walk away with it.
- **Surveillance:** If possible, install surveillance cameras in the conference room. The mere presence of cameras can deter potential wrongdoers.

## Microsoft Teams Rooms Pro Management 

It’s strongly recommended to use a licence for the Microsoft Teams Rooms Pro Management portal, a cloud-based management solution designed to proactively monitor and update Microsoft Teams Rooms devices and their peripherals. This service is tailored for organizations aiming to enhance the meeting room experience for end users, facilitated by real-time monitoring and management for Microsoft Teams Rooms devices like Surface Hub 3. 

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
