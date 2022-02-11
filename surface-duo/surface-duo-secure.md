---
title: Surface Duo security overview
description: This article highlights how Surface Duo delivers enterprise-grade security on a mobile device via the Android OS and Microsoft engineered UEFI.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/12/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto: 
- Surface Duo
---

# Surface Duo security overview

Surface Duo has built-in protection at every layer with deeply integrated hardware, firmware, and software to secure your devices, identities, and data. As an Android 10 device, Surface Duo utilizes Android security features at the OS level and the Google services layer. The Android OS leverages traditional OS security controls to protect user data and system resources, protects device integrity against malware, and provides application isolation. Additionally, Google provides various services layered on top of the OS that, when combined with Android OS security, help continuously protect the Android user.

- **Custom engineered UEFI.** Unique to Surface Duo, among Android devices, is Microsoft's custom engineered Unified Extensible Firmware Interface (UEFI), which enables complete control over firmware components. Microsoft delivers Enterprise-grade security to Surface Duo by writing or reviewing every line of firmware code in-house, allowing Microsoft to respond directly and agilely to potential firmware threats and mitigate supply chain security risks.
- **Verified Boot.** Starting at the hardware level upon sign-in, Verified Boot strives to ensure executed code only comes from a trusted source. It establishes a full chain of trust -- from the hardware-protected root of trust to the bootloader, boot partition and other verified partitions. When Surface Duo boots up, each stage verifies the integrity and authenticity of the next stage before handing over execution.
- **App separation.** Application sandboxing isolates and guards Android apps, preventing malicious apps from accessing private information. Mandatory, always-on encryption and key handling help protect data in transit and at rest -- even if devices fall into the wrong hands. Encryption is protected with Keystore keys, which store cryptographic keys in a container, making it more difficult to extract from a device.
- **Google Play Protect.** At the software layer, Surface Duo uses Google Play Protect threat detection, which scans all applications including public apps from Google Play, system apps updated by Microsoft and carriers, and sideloaded apps.
- **Microsoft Defender ATP.** The enterprise-grade antivirus and malware protection software for Window 10 is now available for Android devices managed from Intune. To learn more, see [Microsoft defender ATP for Android](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-android).

## Mobile device management security

Surface Duo is secured in a corporate environment using an Enterprise Mobility Management (EMM) solution that provides a consistent set of protection tools, technologies, and best practices that you can tailor to meet your organizational and compliance requirements. A broad range of management APIs gives IT departments the tools to help prevent data leakage and enforce compliance in various scenarios. Multi-profile support and device-management options enable the separation of work and personal data, helping keep company data secure.

MDM security is built on an expanding set of configuration technologies to enable users to be productive on the go while also protecting critical corporate intellectual property. This includes app protection policies, device restriction policies, and related technologies designed to enable you to meet specific goals depending on your environment --  whether your business consists of delivering restaurant takeout orders, managing IT services for dental offices, or handling sensitive national security information.

For example, you may wish to strengthen device authentication by requiring users to enter a 6-digit alphanumeric pin along with 2-factor authentication. You may want to restrict the devices users can enroll in to help you stay compliant with licensing limits or avoid granting access to "jailbroken" phones or other unsupported device types. Intune and other EMMs allow organizations to manage devices according to their needs.

## App protection policies

App protection policies (APP) are rules that ensure an organization's data remains safe or contained in a managed app. A policy can be a rule that is enforced when the user attempts to access or move "corporate" data or a set of actions that are prohibited or monitored when the user is inside the app. A managed app is an app that has app protection policies applied to it and can be managed by Intune.

App protection policies allow you to manage and protect your organization's data within an application. Many productivity apps, such as the Microsoft Office apps, can be managed by Intune MAM. See the official list of [Microsoft Intune protected apps](/mem/intune/apps/apps-supported-intune-apps) available for public use.

## Security considerations for managing Surface Duo

The growing number of policy settings available in mobile device management solutions enable organizations to adjust protection levels to meet their specific needs. To help organizations prioritize security settings for Surface Duo (or any other Android device), Intune has introduced its [Android Enterprise security configuration framework](/mem/intune/enrollment/android-configuration-framework) organized into several distinct configuration scenarios, providing guidance for work profile and fully managed scenarios.

| Security level                                                                                                       | Targeted to                                                                                                                                                                      | Summary                                                                                                                                                                                     | Settings info                                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Work profile basic security - Level 1                                                                                | Personal devices with access to work or school data.                                                                                                                             | Introduces password requirements, separates work and personal data, and validates Android device attestation.                                                                               | [Work profile level 1 settings](/mem/intune/enrollment/android-work-profile-security-settings) |
| Work profile high security - Level 3<br>(Due to framework conventions, this is the next level above Level 1.)<br>  | Devices used by users or groups who are uniquely high risk. For example, users handling highly sensitive data where unauthorized disclosure causes considerable material loss. | Introduces mobile threat defense or Microsoft Defender ATP, sets the minimum Android version to 8.0, enacts stronger password policies, and further restricts work and personal separation. | [Work profile level 3 settings](/mem/intune/enrollment/android-work-profile-security-settings#work-profile-high-security)                                                                                         |
| Fully managed basic security -Level 1                                                                                | Minimum-security configuration for an enterprise device, applicable to most mobile users accessing work or school data.                                                          | Introduces password requirements, sets the minimum Android version to 8.0, and enacts certain device restrictions.                                                                          | [Fully managed Level 1 settings](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-basic-security)                                                                                     |
| Fully managed enhanced security Level 2                                                                              | Devices where users access sensitive or confidential information.                                                                                                                | Enacts stronger password policies and disables user/account capabilities.                                                                                                                   | [Fully managed Level 2 settngs](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-enhanced-security)                                                                                   |
| Fully managed high security Level 3                                                                                  | Devices used by users or groups who are uniquely high risk. For example, users handling highly sensitive data where unauthorized disclosure causes considerable material loss. | Increases the minimum Android version to 10.0, introduces mobile threat defense or Microsoft Defender ATP, and enforces additional device restrictions.                                     | [Fully managed Level 3 settings](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-high-security)                                                                                      |
 As with any framework, settings within a corresponding level may need to be adjusted based on the organization's needs as security must evaluate the threat environment, risk appetite, and impact on usability.

## Learn more

- [Android Enterprise security configuration framework](/mem/intune/enrollment/android-configuration-framework)
- [App protection policies overview](/mem/intune/apps/app-protection-policy)
- [Android app protection policy settings in Microsoft Intune](/mem/intune/apps/app-protection-policy-settings-android)
- [Set enrollment restrictions](/mem/intune/enrollment/enrollment-restrictions-set)
- [Android Enterprise Security white paper](https://static.googleusercontent.com/media/www.android.com/en//static/2016/pdfs/enterprise/Android_Enterprise_Security_White_Paper_2019.pdf)
