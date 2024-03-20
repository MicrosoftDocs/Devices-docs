---
title: NFC support in Surface Pro 10 for Business
description: This article provides an overview and FAQ about NFC support in Surface Pro 10 for Business devices.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 03/21/2024
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 11
---

# NFC support in Surface Pro 10 for Business

Near Field Communication (NFC) in Surface Pro 10<sup>1</sup> is designed to enhance security and convenience for users. It facilitates Microsoft Entra ID (formerly Azure AD) and Microsoft Account (MSA) authentication via FIDO 2.0 standards, enabling secure access and sign-in. Additionally, Surface Pro 10 is capable of reading and writing NFC tags.

Although it can read information stored on the magnetic stripe of a bank card, NFC on Surface Pro 10 doesn't support payment transactions. 

We engineered NFC in Surface Pro 10 for enterprise customers where the primary applications of NFC technology extend to authentication, access control, and the exchange of information. These use cases are fundamental in environments that demand heightened security and streamlined operations, such as workplaces and educational institutions.

## Authenticate with NFC

The NFC reader is located in the upper left bezel of the device, under the display.

- To authenticate, align your NFC security key with the center of the Power button where the antenna is located.

:::image type="content" source="images/surface-pro-nfc-tap.png" alt-text="Screenshot of NFC reader location on Surface Pro 10 for Business.":::

## Supported end-user experiences

### Basic authentication

- **Device authentication:** You can log into a device by tapping an NFC-enabled badge or key against its NFC reader. This method is compatible with devices that support NFC for authentication, including Windows Security Key sign-in and various apps that offer single sign-on (SSO) capabilities.
- **App authentication:** You can also log into both native and web apps in the same way, by tapping an NFC-enabled badge or key against the NFC reader. This functionality is available for apps that use NFC for authentication, such as apps integrating with Microsoft Entra ID and MSA.
- **Multi-factor authentication (MFA):** For extra security, you can use your NFC-enabled badge or key as a multifactor authentication token. Just tap it against the NFC reader to securely access services and apps that support NFC keys, including Microsoft Entra ID, MSA, and NFC-compatible apps.

### Asset tracking

- **Tag writing:** You have the ability to write to an NFC tag by tapping it on the NFC reader of the device, using software apps that support this feature.
- **Tag reading:** You can read from an NFC tag by tapping it on the NFC reader of the device. While no other applications are necessary to read the data from an NFC tag, there are third-party solutions that might enhance this experience.

### ID Verification

- **Bank card reading:** You can tap your NFC-enabled bank card against the device to read information from it. This functionality requires specific software capable of reading from bank cards; specifically, a line of business application. (As indicated earlier, NFC on Surface Pro 10 can't process financial transactions.)

### NFC wayfinding support

NFC wayfinding takes advantage of the simplicity and convenience of NFC technology to improve how individuals  navigate through physical spaces. This functionality makes it a valuable tool to enhance user experience, engagement, and accessibility. Common benefits of wayfinding include the following scenarios:

- **Navigation assistance:** NFC tags can be placed at key points within a building or outdoor area. For example, tapping your device against an NFC tag, can display a map, directions, or information about your location. This functionality can help you navigate complex spaces like hospitals, museums, universities, or shopping centers.
- **Accessibility:** NFC wayfinding can improve accessibility for individuals with disabilities by providing audio directions, descriptive content, or tailored assistance based on the user's needs when they interact with NFC tags.
- **Information access:** Beyond just directions, NFC wayfinding can offer detailed information about products in a store enhancing the visitor experience without the need for guided tours or physical brochures.

#### Custom lock-screen image

To help end users find the NFC reader on the device, a custom lock screen image will be available to download and deploy to devices in your organization. See the following figure for an example.

:::image type="content" source="images/nfc-lockscreen-example.png" alt-text="Screenshot showing an example of a custom lock screen image for Surface Pro 10 for Business.":::

## Supported NFC tag types & standards

### Supported standards

Our NFC solution is compatible with a broad range of standards, ensuring it can meet various operational needs:

- **ISO/IEC 14443 A/B compliance:** Enables reading and writing to NFC Type 1, 2, and 4 tags, covering a wide array of use cases from access control to payment systems.
- **JIS X 6319-4 compliance:** Supports Type 3 Tags, facilitating integration with devices and systems utilizing this standard.
- **ISO/IEC 15693 compliance:** Extends capabilities to include Type 5 Tags, allowing for interactions with a broader range of tags including tags that store iClass UID information, commonly used in identification badges.
- **MIFARE compatibility:** Our solution also works seamlessly with the MIFARE encryption method, ensuring secure reading and coding for systems using MIFARE.

### Supported tag types for secure authentication

NFC on Surface Pro 10 supports the use of FIDO2.0 keys, for secure authentication across various platforms, including Windows, Microsoft Entra ID, and MSA. For passwordless sign-in options, we use Microsoft Entra's passwordless sign-in capabilities. To learn more about FIDO key integration with Microsoft Entra, see [Microsoft Entra passwordless sign-in.](/entra/identity/authentication/concept-authentication-passwordless#fido2-security-keys)

The following FIDO2.0 keys are supported and recommended for use:

- **YubiKey**: Offers a portfolio of NFC security keys that support a broad set of security protocols. 
- **Identiv**: Offers a range of security solutions, including FIDO2 security keys.
- **Thetis**: Provides FIDO2 certified security keys designed for secure access.
- **Token2 Card:** A compact and portable security key option.
- **AuthenTrend Card:** Known for their biometric and card-style FIDO2 security keys.

> [!TIP]
> These keys provide a robust layer of security for authentication processes, ensuring a secure and user-friendly experience for IT admins and decision-makers.

## Non-FIDO NFC Keys

The following table includes supported non-FIDO NFC keys, listing various types of NFC tags along with supported technology standards. These keys aren't aligned with the FIDO (Fast Identity Online) Alliance standards but offer a range of functionality including reading and writing tags.

| Name                 | Tag type | Compatible standards                           |
| ------------------------ | ------------ | -------------------------------------------------- |
| Sony Felica Lite RC-S966 | F/3          | JIS X 6319-4                                       |
| NXP ICODE SLI            | v/5          | ISO15693                                           |
| NXP ICODE SLIX           | v/5          | ISO15693                                           |
| NXP NTAG210              | A/2          | ISO 14443                                          |
| NXP NTAG 203             | A/2          | ISO 14443                                          |
| NXP NTAG213              | A/2          | ISO 14443                                          |
| MIFARE Ultralight        | A/2          | ISO 14443-2/ISO 14443-3                            |
| MiFare DESFire           | A/4          | ISO 14443-4/ISO 14443-3/ISO 14443-2/ISO-IEC 7816-4 |
| MIFARE DESFire EV1       | A/4          | ISO 14443-4/ISO 14443-3/ISO 14443-2/ISO-IEC 7816-4 |
| MiFare Classic           | A            | ISO 14443-2/ISO 14443-3/ Mifare Classic            |
| Broadcomm Topaz 512      | A/1          | ISO 14443                                          |
| Infineon Tech AG         | A/4          | ISO 7816, ISO 14443                                |
| Samsung Java card        | A/4          | ISO 7816, ISO 14443                                |

## Manage NFC 

### Disable NFC via device settings

End users can directly disable NFC via device settings.

1. Go to **Settings** > **Network & Internet** > **Airplane modoe** and select **NFC**.
2. Adjust the Toggle switch to turn it off.

### Disable NFC via firmware

For a managed approach, IT admins can disable NFC using SEMM (Surface Enterprise Management Mode). SEMM allows IT admins to manage hardware features at the firmware level. With SEMM, you can enforce policies that disable NFC functionality, making it inaccessible regardless of software settings. To learn more, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md).

### FAQ

**What is the operational range of the NFC reader?**

- The NFC reader is designed to function within a range of up to 15 millimeters along the z-axis. This close proximity ensures secure communication between the reader and NFC-enabled devices or tags.

**Can the NFC reader operate independently of a keyboard?**

- Yes, the NFC reader is designed to work seamlessly both with and without a keyboard across all supported operating systems and modes. This flexibility allows for a wide range of use cases and device configurations.

**Does the NFC feature support waking up the device from sleep mode?**

- No, the current NFC technology doesn't support waking up the device from sleep mode. Surface Pro 10 must be awake and active for NFC interactions to occur.

**Do all Surface Pro devices support reading NFC?**

- No, currently NFC reader is only in Surface Pro 10 for Business and on Surface Go for Business devices.

**Is the NFC functionality different on Surface Pro 10 than Surface Go?**

- NFC functionality on Surface Pro 10 includes support for more cards and tag types. To learn more, see [NFC support in Surface Go for Business](surface-go-nfc-support.md).

### References

1. NFC is only available on Wi-Fi configurations of Surface Pro 10.
