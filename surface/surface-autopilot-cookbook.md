---
title: Surface Autopilot Cookbook for Cloud Solution Providers
description: Step-by-step walkthrough for cloud solution providers to setup Windows Autopilot for customers with Surface devices
manager: frankbu
ms.service: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 03/01/2023
ms.localizationpriority: medium
---
# Surface Autopilot Cookbook for Cloud Solution Providers

With Windows Autopilot, customers can quickly deploy and manage Surface devices without having to manually configure them or maintain their own infrastructure. When users first receive a Surface device, they must connect to a network and verify their credentials. Everything after that is fully automated.

This [downloadable step-by-step walkthrough](/surface/media/surface-autopilot-cookbook.pdf) is primarily intended for [Cloud Solution Providers (CSPs)](/partner-center/csp-overview) with access to the [Microsoft Partner Center](https://partner.microsoft.com).

## Contents

### Introduction

- CSP Microsoft Partner Center requirements
- Network connectivity requirements

### Register Surface devices to Autopilot

- CSP partner submits Autopilot registration to Microsoft Support
- CSP partner registers Autopilot devices via Microsoft Partner Center
- Customer self-registers Autopilot devices via Intune

### Prepare Surface devices for Autopilot

- Reset current in-market devices to OOBE
- Reset earlier Surface devices to OOBE

### Prepare Azure demo tenant

- Create demo tenant from CDX
- Select demo user

<a name='aad-and-intune-setup'></a>

### Microsoft Entra ID and Intune setup

- Configure automatic MDM enrollment
- Configure company branding
- Create Microsoft Entra group for all new Autopilot devices
- Configure Autopilot deployment profile

### Intune device configuration

- Device profiles  
- Enable the enrollment status page
- Deploy software – Microsoft 365 Apps  
- Windows edition upgrade

### DFCI - Intune management of Surface UEFI settings

- Configure Device Firmware Configuration Interface (DFCI) management for Surface devices

### Remove devices from Windows Autopilot Enrollment

- Check device registration status in Intune
- Assign device to a user  

### Reset devices and deregister from Autopilot

- Reset the device to OOBE
- Deregister the device from Windows Autopilot

### Return and exchange scenarios

- Prepare devices for repair
- Remove devices from Autopilot and Device Firmware Configuration Interface (DFCI)
- Reset UEFI to enable boot from USB to reimage
- Enroll device into Autopilot and DFCI to restore previous state

### Appendix

- Generate hardware hash with PowerShell script
- Create and manage Autopilot profiles in the Microsoft Partner Center
- Configure settings as a partner on behalf of your customer from the Microsoft Partner Center
- Apply an Autopilot profile to devices in the Microsoft Partner Center
- Manage devices not supported for OEM enrollment
- Order Specific OS Versions for Windows Autopilot customers

## Learn more

- [Windows Autopilot and Surface devices](windows-autopilot-and-surface-devices.md)
- [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md)
- [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot)
- [Overview of Windows Autopilot](/mem/autopilot/windows-autopilot)
- [Surface System SKU reference](surface-system-sku-reference.md)
