---
title: "Surface Hub security overview"
description: "This page explains the Defense in Depth design of Surface Hub and describes security enhancements in Surface Hub 2S, wireless security protections, and related features."
ms.service: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: overview
ms.date: 01/26/2021
ms.localizationpriority: High
---
# Surface Hub security overview

Surface Hub provides a locked-down appliance-like experience with custom platform firmware running the Windows 10 Team operating system. The resulting device takes the traditional, "single-use" secure kiosk, "only run what you need" philosophy and delivers a modern take on it. Built to support a rich collaborative user experience, Surface Hub is protected against continually evolving security threats.

Built on Windows 10, Surface Hub delivers enterprise-grade modern security enabling IT admins to enforce data protection with BitLocker, Trusted Platform Module 2.0 (TPM), plus cloud-powered security with Windows Defender (also known as Microsoft Defender).

## Defense-in-depth security

Security protocols begin as soon as Surface Hub is turned on. Starting at the firmware level, Surface Hub will only load the operating system and its components in response to multiple security checks. Surface Hub employs a Defense in Depth strategy that involves layering independent defensive sub-components to protect the whole of the system in the event of partial failure. This industry practice has proven to be highly effective in mitigating potential unilateral exploits and weaknesses in sub-components.

The modern Unified Extensible Firmware Interface (UEFI) is statically and securely configured by Microsoft to only boot an authenticated Windows 10 Team operating system from internal storage. Every line of code that runs on Surface Hub has its signature verified before execution. Only applications signed by Microsoft, either as part of the operating system or installed via the Microsoft Store, can run on the Surface Hub. Code or apps not meeting these requirements are blocked.


Surface Hub security systems include the following:

- **Boot-time defenses.** Loads only trusted Surface Hub operating system components.
- **Operating system defenses.** Protects against the execution of unintended or malicious software or code.
- **User interface defenses.** Provides a user interface that's safe for end users, preventing access to potentially risky activities such as running executables from the command line.

### Boot-time defenses

The SoC has a security processor that's separate from every other core. When you first start Surface Hub, the security processor starts before anything else can be loaded.

![Hub startup boot phases showing security processor protections.](images/hub-sec-1.png)

#### Secure Boot

Secure Boot is used to verify that the components of the boot process, including drivers and the operating system, are validated against a database of valid and known signatures. On Surface Hub, a platform-specific signature must first be validated before the authorized Windows Team operating system can be loaded. This helps prevent attacks from a cloned or modified system running malicious code hidden in what appears to be an otherwise normal user experience.  For more information, see [Secure Boot overview](/windows-hardware/design/device-experiences/oem-secure-boot).

### Operating system defenses

Once the operating system is verified as originating from Microsoft and Surface Hub successfully completes the boot process, the device scrutinizes the executable code. Our approach to securing the operating system involves identifying the code signature of all executables, allowing only those that pass our restrictions to be loaded into the runtime. This code-signing method enables the operating system to verify the author and confirm that code was not altered prior to running on the device.

Surface Hub uses a code signing feature known as User Mode Code Integrity (UMCI) in Windows Application Control (formerly known as Device Guard). Policy settings are configured to only allow apps that meet one of these requirements:

- Universal Windows Platform (Microsoft Store) apps that are [officially certified](/windows/uwp/publish/the-app-certification-process).
- Apps signed with the unique Microsoft Production Root Certification Authority (CA), which can only be signed by Microsoft employees with authorized access to those certificates.
- Apps signed with the unique Surface Hub Production Root C.

The configuration file is signed using the Microsoft Production Root CA designed to prevent restrictions from being removed or modified by a third party. All other executables at this point are simply blocked at the operating system runtime level and prevented from accessing processing power. This attack surface reduction provides the following protections:

- No legacy document modes
- No legacy script engines
- No Vector Markup Language
- No Browser Helper Objects
- No ActiveX controls

In addition to blocking unsigned or incorrectly signed code via UMCI, Surface Hub uses Windows Application Control to block Windows components, such as the Command Prompt, PowerShell, and Task Manager. These safeguards reflect a key design feature of Surface Hub as a secure computing appliance. For more information, see the following:

- [Application Control overview](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender Application Control and virtualization-based protection of code integrity](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

### User interface defenses

While boot-time defenses and operating system lockdown safeguards deliver foundational security, the user interface provides an additional layer designed to further reduce risk. To prevent malicious code from reaching the device through drivers, Surface Hub does not download advanced drivers for plug and play (PnP) devices. Devices that leverage basic drivers, such as USB flash drives or certified Surface Hub peripherals (speakers, microphones, cameras), work as expected, but advanced systems, such as printers, will not.

User interface defenses also simplify the UI, further preventing the execution of malicious software or code. The following Surface Hub UI elements layer the core security provided by code signing:

- **File Explorer.** Surface Hub has a custom File Explorer that enables quick access to Music, Videos, Documents, Pictures, and Downloads folders — without exposing users to system or program files. Other locations on the local hard drive are not available through File Explorer. In addition, many file types running, such as .exe and .msi installation files, cannot run, providing another layer of safety against potentially malicious executables.

- **Start & All Apps.** The Start and All Apps components of Surface Hub do not expose access to Command Prompt, PowerShell, or other Windows components blocked via Application Control. In addition, Windows run functionality typically accessed on PCs from the Search box is turned off for Surface Hub.

## Security enhancements in Surface Hub 2S

Although Surface Hub and Surface Hub 2S both run the same operating system software, some features unique to Surface Hub 2S provide additional management and security capabilities, enabling IT admins to perform the following tasks:

- Manage UEFI settings with SEMM
- Recover Hub with bootable USB
- Harden device account with password rotation

### Manage UEFI settings with SEMM

UEFI is an interface between the underlying hardware platform pieces and the operating system. On Surface Hub, a custom UEFI implementation allows granular control over these settings and prevents any non-Microsoft entity from changing the UEFI settings of the device — or booting to a removable drive to modify or change the operating system.

At a high level, during the factory provisioning process, Surface Hub UEFI is preconfigured to enable Secure Boot and is set to only boot from the internal solid-state drive (SSD), with access to UEFI menus locked down and shortcuts removed. This seals UEFI access and ensures the device can only boot into the Windows Team operating system installed on Surface Hub.

When managed via Microsoft Surface Enterprise Management Mode (SEMM), IT admins can deploy UEFI settings on Hub devices across an organization. This includes the ability to enable or disable built-in hardware components, protect UEFI settings from being changed by unauthorized users, and adjust boot settings.

![Surface Hub UEFI settings.](images/hub-sec-2.png)

Admins can implement SEMM and enrolled Surface Hub 2S devices using the downloadable [Microsoft Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703). For more information, see [Secure and manage Surface Hub 2S with SEMM and UEFI](/surface-hub/surface-hub-2s-secure-with-uefi-semm).
Secured using a certificate to protect the configuration from unauthorized tampering or removal, SEMM enables management of the following components:

- Wired LAN
- Camera
- Bluetooth
- Wi-Fi
- Occupancy sensor
- IPv6 for PXE Boot
- Alternate Boot
- Boot Order Lock
- USB Boot
- UEFI front page interface
    - Devices
    - Boot
    - Date/Time

    
### Recover Hub with bootable USB

Surface Hub 2S enables admins to reinstall the device to factory settings using a recovery image in as little as 20 minutes. Typically, you would only need to do this if your Surface Hub is no longer functioning. Recovery is also useful if you have lost the Bitlocker key or no longer have admin credentials to the Settings app.

### Harden device account with password rotation

Surface Hub uses a device account, also known as a "room account," to authenticate with Exchange, Microsoft Teams, and other services. When you enable password rotation, Hub 2S automatically generates a new password every seven days, consisting of 15-32 characters with a combination of uppercase and lowercase letters, numbers, and special characters. Because no one knows the password, the device account password rotation effectively mitigates associated risks from human error and potential social engineering security attacks.

## Enterprise-grade security

In addition to Surface Hub-specific configurations and features addressed in this document, Surface Hub also uses standard Windows security features. These include:

- **BitLocker**. The Surface Hub SSD is equipped with BitLocker to protect the data on the device. Its configuration follows industry standards. For more information, see [BitLocker overview](/windows-hardware/design/device-experiences/oem-secure-boot).
- **Windows Defender.** The Windows Defender anti-malware engine runs continuously on Surface Hub and works to automatically remediate threats found on Surface Hub. The Windows Defender engine receives updates automatically and is manageable via remote management tools for IT admins. The Windows Defender engine is a perfect example of our Defense in Depth approach: If malware can find a way around our core code-signage-based security solution, it will be caught here. For more information, see [Windows Defender Application Control and virtualization-based protection of code integrity](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control).
- **Plug and play drivers.** To prevent malicious code from reaching the device through drivers, Surface Hub does not download advanced drivers for PnP devices. This allows devices that leverage basic drivers such as USB flash drives to work as expected while blocking more advanced systems such as printers.
- **Trusted Platform Module 2.0.** Surface Hub has an industry standard discrete Trusted Platform Module (dTPM) for generating and storing cryptographic keys and hashes. The dTPM protects keys used for the verification of boot phases, the BitLocker master key, password-less sign-on key, and more. The dTPM meets [FIPS 140-2 Level 2](/windows/security/threat-protection/fips-140-validation) certification, the U.S. government computer security standard, and is compliant with [Common Criteria](/windows/security/threat-protection/windows-platform-common-criteria) certification used worldwide.

## Wireless security for Surface Hub

Surface Hub uses Wi-Fi Direct / Miracast technology and the associated 802.11, Wi-Fi Protected Access (WPA2), and Wireless Protected Setup (WPS) standards. Since the device only supports WPS (as opposed to WPA2 Pre-Shared Key (PSK) or WPA2 Enterprise), issues traditionally associated with 802.11 encryption are simplified by design.

Surface Hub operates on par with the field of Miracast receivers. So, it's vulnerable to a similar set of exploits as all WPS-based wireless network devices. But the Surface Hub implementation of WPS has extra precautions built in. Also, its internal architecture helps prevent an attacker who has compromised the Wi-Fi Direct/Miracast layer from moving past the network interface onto other attack surfaces and connected enterprise networks.

Miracast is part of the Wi-Fi Display standard, which itself is supported by the Wi-Fi Direct protocol. These standards are supported in modern mobile devices for screen sharing and collaboration.
Wi-Fi Direct or Wi-Fi "peer to peer" (P2P) is a standard released by the Wi-Fi Alliance for "Ad-Hoc" networks. This allows supported devices to communicate directly and create groups of networks without requiring a traditional Wi-Fi Access Point or an Internet connection.

Security for Wi-Fi Direct is provided by WPA2 using the WPS standard. Devices can be authenticated using a numerical pin, a physical or virtual push button, or an out-of-band message using near-field communication. Surface Hub supports both push button by default as well PIN methods. 

## How Surface Hub addresses Wi-Fi Direct vulnerabilities

**Vulnerabilities and attacks in the Wi-Fi Direct invitation, broadcast, and discovery process:** Wi-Fi Direct/Miracast attacks may target weaknesses in the group establishment, peer discovery, device broadcast, or invitation processes.

|Wi-Fi Direct vulnerability | Surface Hub mitigation |
| --- | --- |
| The discovery process may remain active for an extended period of time, which could allow invitations and connections to be established without the approval of the device owner. | Surface Hub only operates as the group owner, which doesn't perform the client discovery or GO negotiation processes. You can fully disable wireless projection to turn off broadcast. |
| Invitation and discovery through PBC allow an unauthenticated attacker to perform repeated connection attempts, or unauthenticated connections are automatically accepted. | By requiring WPS PIN security, administrators can reduce the potential for such unauthorized connections or "invitation bombs," in which invitations are repeatedly sent until a user mistakenly accepts one. |

**Wi-Fi Protected Setup (WPS) push button connect (PBC) vs PIN entry:** Public weaknesses have been demonstrated in WPS-PIN method design and implementation. WPS-PBC has other vulnerabilities that could allow active attacks against a protocol that's designed for one-time use.

| Wi-Fi Direct vulnerability | Surface Hub mitigation |
| --- | --- |
| WPS-PBC is vulnerable to active attackers. The WPS specification states: *"The PBC method has zero bits of entropy and only protects against passive eavesdropping attacks. PBC protects against eavesdropping attacks and takes measures to prevent a device from joining a network that was not selected by the device owner. The absence of authentication, however, means that PBC does not protect against active attack."* Attackers can use selective wireless jamming or other denial-of-service techniques to trigger an unintended Wi-Fi Direct GO or connection. Also, an active attacker who merely has physical proximity can repeatedly tear down any Wi-Fi Direct group and attempt the attack until it succeeds. | Enable WPS-PIN security in Surface Hub configuration. The Wi-Fi WPS specification states: "The PBC method should only be used if no PIN-capable registrar is available and the WLAN user is willing to accept the risks associated with PBC." |
| WPS-PIN implementations can be subject to brute-force attacks that target a vulnerability in the WPS standard. The design of split PIN verification led to multiple implementation vulnerabilities over the past several years across a range of Wi-Fi hardware manufacturers. In 2011, researchers Stefan Viehböck and Craig Heffner released information about this vulnerability and tools such as "Reaver" as a proof of concept. |   The Microsoft implementation of WPS in Surface Hub changes the PIN every 30 seconds. To crack the PIN, an attacker must complete the entire exploit in less than 30 seconds. Given the current state of tools and research in this area, a brute-force PIN-cracking attack through WPS is unlikely to succeed. |
| WPS-PIN can be cracked by an offline attack because of weak initial key (E-S1, E-S2) entropy. In 2014, Dominique Bongard described a "Pixie Dust" attack where poor initial randomness for the pseudorandom number generator (PRNG) in the wireless device allowed an offline brute-force attack. | The Microsoft implementation of WPS in Surface Hub is not susceptible to this offline PIN brute-force attack. The WPS-PIN is randomized for each connection. |

**Unintended exposure of network services:** Network daemons that are intended for Ethernet or WLAN services may be accidentally exposed because of misconfiguration (such as binding to "all"/0.0.0.0 interfaces). Other possible causes include a poorly configured device firewall or missing firewall rules.

| Wi-Fi Direct vulnerability | Surface Hub mitigation |
| --- | --- |
| Misconfiguration binds a vulnerable or unauthenticated network service to "all" interfaces, which includes the Wi-Fi Direct interface. This can expose services that shouldn't be accessible to Wi-Fi Direct clients, which may be weakly or automatically authenticated. | In Surface Hub, the default firewall rules only permit the required TCP and UDP network ports and, by default, deny all inbound connections. Configure strong authentication by enabling the WPS-PIN mode.|

**Bridging Wi-Fi Direct and other wired or wireless networks:** Network bridging between WLAN or Ethernet networks is a violation of the Wi-Fi Direct specification. Such a bridge or misconfiguration may effectively lower or remove wireless access controls for the internal corporate network.

| Wi-Fi Direct vulnerability | Surface Hub mitigation |
| --- | --- |
| Wi-Fi Direct devices could allow unauthenticated or poorly authenticated access to bridged network connections. This might allow Wi-Fi Direct networks to route traffic to internal Ethernet LAN or other infrastructure or to enterprise WLAN networks in violation of existing IT security protocols. | Surface Hub can't be configured to bridge wireless interfaces or allow routing between disparate networks. The default firewall rules add defense in depth to any such routing or bridge connections. |

**The use of Wi-Fi Direct "legacy" mode:** Exposure to unintended networks or devices may occur when you operate in "legacy" mode. Device spoofing or unintended connections could occur if WPS-PIN is not enabled.

| Wi-Fi Direct vulnerability | Surface Hub mitigation |
| --- | --- |
| By supporting both Wi-Fi Direct and 802.11 infrastructure clients, the system is operating in a "legacy" support mode. This may expose the connection-setup phase indefinitely, allowing groups to be joined or devices invited to connect well after their intended setup phase terminates. |    Surface Hub doesn't support Wi-Fi Direct legacy clients. Only Wi-Fi Direct connections can be made to Surface Hub even when WPS-PIN mode is enabled. |

**Wi-Fi Direct GO negotiation during connection setup:** The group owner in Wi-Fi Direct is analogous to the "access point" in a conventional 802.11 wireless network. The negotiation can be gamed by a malicious device.

|Wi-Fi Direct vulnerability |   Surface Hub mitigation |
| --- | --- |
| If groups are dynamically established, or the Wi-Fi Direct device can be made to join new groups, the group owner negotiation can be won by a malicious device that always specifies the maximum group owner "intent" value of 15. (But the connection fails if the device is configured to always be a group owner.)  | Surface Hub takes advantage of Wi-Fi Direct "Autonomous mode," which skips the GO negotiation phase of connection setup. And Surface Hub is always the group owner. |

**Unintended or malicious Wi-Fi deauthentication:** Wi-Fi deauthentication is an old attack in which a local attacker can expedite information leaks in the connection-setup process, trigger new four-way handshakes, target Wi-Fi Direct WPS-PBC for active attacks, or create denial-of-service attacks.

| Wi-Fi Direct vulnerability | Surface Hub mitigation |
| --- | --- |
| Deauthentication packets can be sent by an unauthenticated attacker to cause the station to re-authenticate and then sniff the resulting handshake. Cryptographic or brute-force attacks can be attempted on the resulting handshake. Mitigation for these attacks includes enforcing length and complexity policies for pre-shared keys, configuring the access point (if applicable) to detect malicious levels of deauthentication packets, and using WPS to automatically generate strong keys. In PBC mode, the user interacts with a physical or virtual button to allow arbitrary device association. This process should happen only at setup, within a short window. After the button is automatically "pushed," the device will accept any station that associates via a canonical PIN value (all zeros). Deauthentication can force a repeated setup process. |   Surface Hub uses WPS in PIN or PBC mode. No PSK configuration is permitted. This method helps enforce generation of strong keys. It's best to enable WPS-PIN security for Surface Hub. |
| In addition to denial-of-service attacks, deauthentication packets can be used to trigger a reconnect that re-opens the window of opportunity for active attacks against WPS-PBC. |   Enable WPS-PIN security in the Surface Hub configuration. |

**Basic wireless information disclosure:** Wireless networks, 802.11 or otherwise, are inherently at risk of information disclosure. Although this information is mostly connection or device metadata, this problem remains a known risk for any 802.11 network administrator. Wi-Fi Direct with device authentication via WPS-PIN effectively reveals the same information as a PSK or Enterprise 802.11 network.

| Wi-Fi Direct vulnerability | Surface Hub mitigation |
| --- | --- |
| During broadcast, connection setup, or even normal operation of already-encrypted connections, basic information about devices and packet sizes is wirelessly transmitted. At a basic level, a local attacker who's within wireless range can examine the relevant 802.11 information elements to determine the names of wireless devices, the MAC addresses of communicating equipment, and possibly other details, such as the version of the wireless stack, packet sizes, or the configured access point or group owner options.  | The Wi-Fi Direct network that Surface Hub uses can't be further protected from metadata leaks, just like for 802.11 Enterprise or PSK wireless networks. Physical security and removal of potential threats from wireless proximity can help reduce potential information leaks. |

**Wireless evil twin or spoofing attacks:**  Spoofing the wireless name is a simple, well-known exploit a local attacker can use to lure unsuspecting or mistaken users to connect.

| Wi-Fi Direct vulnerability | Surface Hub mitigation |
| --- | --- |
| By spoofing or cloning the wireless name or "SSID" of the target network, an attacker may trick the user into connecting to a fake, malicious network. By supporting unauthenticated, auto-join Miracast, an attacker could capture the intended display materials or launch network attacks on the connecting device. | While there are no specific protections against joining a spoofed Surface Hub, this vulnerability is partially mitigated in two ways. First, any potential attack must be physically within Wi-Fi range. Second, this attack is only possible during the first connection. Subsequent connections use a persistent Wi-Fi Direct group, and Windows will remember and prioritize this prior connection during future Hub use. (Note: Spoofing the MAC address, Wi-Fi channel, and SSID simultaneously was not considered for this report and may result in inconsistent Wi-Fi behavior.) Overall, this weakness is a fundamental problem for any 802.11 wireless network that lacks Enterprise WPA2 protocols such as EAP-TLS or EAP-PWD, which Wi-Fi Direct doesn't support. |

## Surface Hub hardening guidelines

Surface Hub is designed to facilitate collaboration and allow users to start or join meetings quickly and efficiently. The default Wi-Fi Direct settings for Surface Hub are optimized for this scenario.

For additional wireless interface security, Surface Hub users should enable the WPS-PIN security setting. This setting disables WPS-PBC mode and offers client authentication. It provides the strongest level of protection by preventing unauthorized connection to Surface Hub.

If you still have concerns about authentication and authorization for Surface Hub, we recommend that you connect the device to a separate network. You could use Wi-Fi (such as a "guest" Wi-Fi network) or a separate Ethernet network, preferably an entirely different physical network. But a VLAN can also provide added security. Of course, this approach may preclude connections to internal network resources or services and may require additional network configuration to regain access.

Also recommended:

- [Install regular system updates](manage-windows-updates-for-surface-hub.md) 
- Update Miracast settings to disable auto-present mode


## Learn more

- [Secure Boot overview](/windows-hardware/design/device-experiences/oem-secure-boot)
- [BitLocker overview](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [Application Control overview](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Secure and manage Surface Hub 2S with SEMM and UEFI](/surface-hub/surface-hub-2s-secure-with-uefi-semm)
- [How Surface Hub addresses Wi-Fi Direct security issues](/surface-hub/surface-hub-wifi-direct)
- [Windows Defender Application Control and virtualization-based protection of code integrity](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)
- [FIPS 140-2 Level 2](/windows/security/threat-protection/fips-140-validation)
- [Common Criteria certification](/windows/security/threat-protection/windows-platform-common-criteria)
