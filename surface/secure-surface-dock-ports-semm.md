---
title:  Configure UEFI settings for Surface Docks
description: Manage UEFI settings for Surface Docks with .msi packages using Surface IT Toolkit. Secure and manage ports on supported devices.
ms.assetid: 2808a8be-e2d4-4cb6-bd53-9d10c0d3e1d6
manager: frankbu
ms.service: surface
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 09/06/2024
ms.localizationpriority: medium
appliesto:
- Windows 10
- Windows 11
---

# Configure UEFI settings for Surface Docks

IT admins can secure and manage ports on Surface Dock 2 or Surface Thunderbolt 4 Dock by configuring UEFI settings in a Windows Installer configuration package (.msi file) deployed to compatible Surface devices across a corporate environment.

## Supported devices

Managing Surface Dock 2 or Surface Thunderbolt 4 Dock with SEMM is available for docks connected to Surface Laptop Studio (all generations), Surface Laptop (7th Edition), Surface Laptop 6, Surface Laptop 5, Surface Laptop 4, Surface Laptop 3, Surface Laptop Go (all generations), Surface Pro (11th Edition), Surface Pro 10, Surface Pro 10 with 5G, Surface Pro 9, Surface Pro 9 with 5G, Surface Pro 8, Surface Pro 7+, Surface Pro 7, Surface Pro X, and Surface Book 3.

> [!TIP]
> These compatible Surface devices are commonly referred to as **host devices**. A package is applied to host devices based on whether a host device is **Authenticated** or **Unauthenticated**. Configured settings reside in the UEFI layer on host devices, enabling IT admins to manage compatible Surface Docks like any other built-in peripheral, such as the camera.

## Configure and deploy UEFI settings for Surface Docks

This section provides step-by-step guidance for the following tasks:

1. Install [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703).
2. Create or obtain public key certificates.
3. Create an .msi configuration package.
   a. Add your certificates.
   b. Enter the 16-digit RN number for your Surface Dock 2 or Surface Thunderbolt 4 Dock devices.
   c. Configure UEFI settings for component policies: USB Data, Ethernet, or Audio.
4. Create and apply the configuration package to targeted Surface devices.
5. Use Surface App to confirm the resultant policy state of the managed Surface Dock.

>[!IMPORTANT]
>The **Random Number (RN)** is a unique 16-digit hex code identifier provisioned at the factory and printed in small type on the dock's underside. The RN differs from most serial numbers because it can't be read electronically. This ensures proof of ownership is established only by reading the RN when physically accessing the device. The RN may also be obtained during the purchase transaction and is recorded in Microsoft inventory systems.

## Create public key certificates

This section provides specifications for creating the certificates needed to manage ports for Surface Dock 2 or Surface Thunderbolt 4 Dock.

### Prerequisites

This article assumes that you either obtain certificates from a third-party provider or already have expertise in PKI certificate services and know how to create your own. You should be familiar with and follow the general recommendations for creating certificates as described in [Get started with Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation, with one exception. The certificates required to configure Surface Docks with SEMM require expiration terms of 30 years for the **Dock Certificate Authority** and 20 years for the **Host Authentication Certificate**.

If you already have the appropriate certificates, proceed to the next section. Otherwise, carefully review the guidance in [Appendix: Root and host certificate requirements](#appendix-root-and-host-certificate-requirements).

### Create a dock provisioning package

When you've obtained or created the certificates, you can build the .msi provisioning package that will be applied to target devices.

1. Open Surface IT Toolkit and select **Configure Surface Dock**.

    :::image type="content" source="images/ueficonfig-dock-start.png" alt-text="Screenshot that shows Surface Dock component in the Surface IT Toolkit.":::

2. Choose Dock Type and select a provisioning method.

- **Organizational Unit**, designed for corporate-wide use.
- **Departmental Unit**, designed for more granular settings configuration; for example, a department handling highly sensitive information.

3. Import your certificate authority and certificate files and enter the password for each file. Select **Next**. This example shows organizational provisioning.

    :::image type="content" source="images/ueficonfig-dock-provisioning.png" alt-text="Screenshot that shows import of required certificates.":::

4. Add the Surface Dock ID numbers associated with the docks you intend to manage. For multiple docks, enter the numbers in a .csv file without a header, meaning the first line of the file should not contain column names or descriptions.

    :::image type="content" source="images/ueficonfig-dock-add-rn-numbers.png" alt-text="Screenshot that shows addition of RN numbers.":::

5. You can specify policy settings for USB data, Ethernet, and Audio ports. UEFI Configurator lets you configure policy settings for authenticated users (Authenticated Policy) and unauthenticated users (Unauthenticated Policy).

   - **Authenticated Policy** refers to a Surface Device with the appropriate certificates installed, as configured in the .msi configuration package you applied to target devices.
   - **Unauthenticated Policy** refers to any other device.

6. Choose which components you want to activate or deactivate and select **Next**. The following figure shows port access turned on for authenticated devices and turned off for unauthenticated devices.

    :::image type="content" source="images/ueficonfig-dock-configure3.png" alt-text="Screenshot that shows ports turned off for unauthenticated devices.":::

7. If you have devices you want to configure for Dynamic USB-C Disablement, select the checkbox as shown in the following figure. Add the required certificate and select **Next**. To learn more, see [Scenarios for securing Surface Dock ports](#scenarios-for-securing-surface-dock-ports) on this page.

    :::image type="content" source="images/ueficonfig-dock-configure-usb-c.png" alt-text="Screenshot that selection of devices to configure USB-C Dynamic Disablement.":::

7. Complete a final review of your configured settings, choose a folder to save the Package and select **Create**.

    :::image type="content" source="images/ueficonfig-dock-create-package.png" alt-text="Screenshot that shows page to create provisioning package.":::

### Apply the provisioning package to a Surface Dock

1. Take the .msi file that the Surface UEFI Configurator generated and install it on a Surface host device such as Surface Laptop 6 or Surface Pro 10.
2. Connect the host device to Surface Dock 2 or Surface Thunderbolt 4 Dock. When you connect the dock, UEFI policy settings are applied.

## Scenarios for securing Surface Dock ports

Restricting Surface Dock 2 or Surface Thunderbolt 4 Dock to authorized persons signed into a corporate host device provides another layer of data protection. This ability to lock down Surface Docks is critical for specific customers in highly secure environments who want the functionality and productivity benefits of the dock while maintaining compliance with strict security protocols. SEMM used with Surface Dock 2 or Surface Thunderbolt 4 Dock is helpful in open offices and shared spaces, especially for customers who want to lock USB ports for security reasons.

- **Granular USB-C Disablement.** Managing USB-C ports with their support for DisplayPort and USB Power Delivery provides more options beyond turning off all functionality. For example, you can prevent data connectivity to stop users from copying data from USB storage but retain the ability to extend displays and charge the device via a USB-C dock. Beginning with Surface Pro 8, Surface Laptop Studio, and Surface Go 3, these options are now available via the SEMM PowerShell scripts.

- **Dynamic USB-C Disablement.** Dynamic USB-C Disablement enables customers operating in highly secure work environments to prevent USB theft of confidential data and provide more control to organizations. When paired with the Surface Thunderbolt 4 Dock, IT admins can lock down USB-C ports whenever an eligible Surface device is undocked or connected to an unauthorized dock.

> [!TIP]
> This feature is available on Surface Pro 10, Surface Laptop 6, and Surface Laptop Studio 2.

With Dynamic USB-C Disablement when users are connected to an authorized dock in the office, the USB-C ports will have full functionality over their devices. However, when they go off-site, they can still connect to a dock to use accessories or a monitor but cannot use the USB ports to transfer data.

Managing USB-C ports for these scenarios involves the following tasks:  

- Provision your host devices, such as Surface Pro 10 or Surface Laptop 6, and provision Surface dock into SEMM via an .msi package generated by UEFI Configurator, as described earlier on this page. 
- Create a separate .msi package containing the UEFI policy settings for "Authenticated" and "Unauthenticated" devices.
- Configure Granular USB-C Disablement or Dynamic USB-C Disablement.

To learn more, see [Manage USB ports on Surface devices](manage-usb-ports-on-surface.md).

## Verify managed state using the Surface App

Once you've applied the configuration package, you can quickly verify the resultant policy state of the dock directly from the Surface App, installed by default on all Surface devices. If the Surface App isn't on the device, you can download and install it from the Microsoft Store.

### Test scenario

Objective: Configure policy settings to allow port access by authenticated users only.

1. As described earlier, turn on all ports for authenticated users and turn them off for unauthenticated users.

    :::image type="content" source="images/ueficonfig-dock-configure3.png" alt-text="Screenshot that shows ports turned off for unauthenticated devices.":::

2. Apply the configuration package to your target device and connect the dock.

3. Open **Surface App** and select **Surface Dock** to view the resultant policy state of your Surface Dock. If the policy settings are applied, Surface App (shown here for Surface Thunderbolt 4 Dock and Surface Dock 2) indicates that ports are available.

   ![Screenshot that shows surface app shows all ports are available for authenticated users on Surface Dock 2.](images/surface-thunderbolt-4-dock-unmanaged.png)

   ![Screenshot that shows surface app shows all ports are available for authenticated users on Surface Thunderbolt 4 Dock.](images/secure-surface-dock-ports-semm-5.png)

4. Now, you need to verify that the policy settings have successfully turned off all ports for unauthenticated users. Connect Surface Dock 2 or Surface Thunderbolt 4 Dock to an unmanaged device, for example, any Surface device outside the scope of management for the configuration package you created.

5. Open **Surface App** and select **Surface Dock**. The resultant policy state (shown here for Surface Thunderbolt 4 Dock and Surface Dock 2) indicates that ports are turned off.

   ![Screenshot that shows surface app showing ports turned off for unauthenticated users on Surface Thunderbolt 4 Dock.](images/surface-thunderbolt-4-dock-managed.png)

   ![Screenshot that shows surface app showing ports turned off for unauthenticated users on Surface Dock 2.](images/secure-surface-dock-ports-semm-6.png)

>[!TIP]
>If you want to keep ownership of the device but allow all users full access, you can make a new package with everything turned on. If you wish to completely remove the restrictions and ownership of the device (make it unmanaged), select **Reset** in Surface UEFI Configurator to create a package to apply to target devices.

Congratulations. You have successfully managed Surface Dock ports on targeted host devices.

## Appendix: Root and host certificate requirements

Before creating the configuration package, you need to prepare public key certificates that authenticate ownership of Surface Dock 2 or Surface Thunderbolt 4 Dock and facilitate any subsequent changes in ownership during the device lifecycle. The host and provisioning certificates require entering EKU IDs, otherwise known as **Client Authentication Enhanced Key Usage (EKU) object identifiers (OIDs)**.

The required EKU values are listed in Table 1 and Table 2.

> [!CAUTION]
> Keep certificates in a safe location and ensure they're properly backed up. Without them it's impossible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.

#### Table 1. Root and Dock Certificate requirements

|Certificate|Algorithm|Description|Expiration|EKU OID|
|---|---|---|---|---|
|Root Certificate Authority|ECDSA_P384|- Root certificate with 384-bit prime Elliptic Curve Digital Signature Algorithm (ECDSA)<br>- Secure Hash Algorithm (SHA) 256 Key Usage:<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>- CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30 years|N/A
|Dock Certificate Authority|ECC P256 curve|- Host certificate with 256-bit Elliptic Curve Cryptography (ECC)<br>- SHA 256 Key Usage:<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>- Path Length Constraint = 0|20 years|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >The dock CA must be exported as a .p7b file.

### Provisioning Administration Certificate requirements

Each host device must have the doc CA and two certificates, as shown in Table 2.

#### Table 2. Provisioning administration certificate requirements

|Certificate|Algorithm|Description|EKU OID|
|---|---|---|---|
|Host authentication certificate|ECC P256<br>SHA 256|Proves the identity of the host device.|1.3.6.1.4.1.311.76.9.21.2|
|Provisioning administration certificate|ECC P256<br>SHA256|Enables you to change dock ownership or policy settings by allowing you to replace the current CA installed on the dock.|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >The host authentication and provisioning certificates must be exported as .pfx files.

For more information, see [Certificate Services Architecture](/windows/win32/seccrypto/certificate-services-architecture) documentation and review the appropriate chapters in [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277), or [Windows Server 2008 PKI and Certificate Security](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) available from Microsoft Press.

## Learn more

- [Manage USB ports on Surface devices](manage-usb-ports-on-surface.md)
- [Surface Enterprise Management Mode (SEMM) documentation](surface-enterprise-management-mode.md)
- [Certificate Services Architecture](/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Windows Server 2008 PKI and Certificate Security](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
