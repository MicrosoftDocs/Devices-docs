---
title: NFC support in Surface Pro
description: Discover NFC support in Surface Pro 10 & 11th Edition for enhanced security, FIDO2 authentication, and more, ideal for enterprise use.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 09/04/2024
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 11
---

# NFC support in Surface Pro

Near Field Communication (NFC) in commercial versions of Surface Pro 10 and Surface Pro (11th Edition)[<sup>1</sup>](#references) is designed to enhance security and convenience for users. It facilitates Microsoft Entra ID (formerly Azure AD) and Microsoft Account (MSA) authentication via FIDO 2.0 standards, enabling secure access and sign-in. Additionally, these devices are capable of reading and writing NFC tags.

Although NFC can read information stored on the magnetic stripe of a bank card, it doesn't support payment transactions on Surface Pro 10 or Surface Pro (11th Edition).

We engineered NFC in Surface Pro 10 and Surface Pro (11th Edition) for enterprise customers where the primary applications of NFC technology extend to authentication, access control, and the exchange of information. These use cases are fundamental in environments that demand heightened security and streamlined operations, such as workplaces and educational institutions.

## Authenticate with NFC

The NFC reader is located in the upper left bezel of the device, under the display.

- To authenticate, align your NFC security key with the center of the Power button where the antenna is located.

:::image type="content" source="images/surface-pro-nfc-tap-example.png" alt-text="Screenshot of NFC reader location on Surface Pro 10 and Surface Pro (11th Edition) for Business.":::

## Supported end-user experiences

### Basic authentication

- **Device authentication:** You can log into a device by tapping an NFC-enabled badge or key against its NFC reader. This method is compatible with devices that support NFC for authentication, including Windows Security Key sign-in and various apps that offer single sign-on (SSO) capabilities.
- **App authentication:** You can also log into both native and web apps in the same way, by tapping an NFC-enabled badge or key against the NFC reader. This functionality is available for apps that use NFC for authentication, such as apps integrating with Microsoft Entra ID and MSA.
- **Multi-factor authentication (MFA):** For extra security, you can use your NFC-enabled badge or key as a multifactor authentication token. Just tap it against the NFC reader to securely access services and apps that support NFC keys, including Microsoft Entra ID, MSA, and NFC-compatible apps.

### Asset tracking

- **Tag writing:** You have the ability to write to an NFC tag by tapping it on the NFC reader of the device, using software apps that support this feature.
- **Tag reading:** You can read from an NFC tag by tapping it on the NFC reader of the device. While no other applications are necessary to read the data from an NFC tag, there are third-party solutions that might enhance this experience.

### ID Verification

- **Bank card reading:** You can tap your NFC-enabled bank card against the device to read information from it. This functionality requires specific software capable of reading from bank cards; specifically, a line of business application. (As indicated earlier, NFC on Surface Pro 10 and Surface Pro (11th Edition) can't process financial transactions.)

### NFC wayfinding support

NFC wayfinding takes advantage of the simplicity and convenience of NFC technology to improve how individuals navigate through physical spaces. This functionality makes it a valuable tool to enhance user experience, engagement, and accessibility. Common benefits of wayfinding include the following scenarios:

- **Navigation assistance:** NFC tags can be placed at key points within a building or outdoor area. For example, tapping your device against an NFC tag, can display a map, directions, or information about your location. This functionality can help you navigate complex spaces like hospitals, museums, universities, or shopping centers.
- **Accessibility:** NFC wayfinding can improve accessibility for individuals with disabilities by providing audio directions, descriptive content, or tailored assistance based on the user's needs when they interact with NFC tags.
- **Information access:** Beyond just directions, NFC wayfinding can offer detailed information about products in a store, enhancing the visitor experience without the need for guided tours or physical brochures.

#### Custom lock-screen image

To help end users find the NFC reader on the device, a custom lock screen image is available to download and deploy to devices in your organization. See [Download NFC Lock Screens](#download-nfc-lock-screens) on this page.

:::image type="content" source="images/nfc-lockscreen-example.png" alt-text="Screenshot showing an example of a custom lock screen image for Surface Pro 10 and Surface Pro (11th Edition) for Business.":::

## Supported NFC tag types & standards

### Supported standards

Our NFC solution is compatible with a broad range of standards, ensuring it can meet various operational needs:

- **ISO/IEC 14443 A/B compliance:** Enables reading and writing to NFC Type 1, 2, and 4 tags, covering a wide array of use cases from access control to payment systems.
- **JIS X 6319-4 compliance:** Supports Type 3 Tags, facilitating integration with devices and systems utilizing this standard.
- **ISO/IEC 15693 compliance:** Extends capabilities to include Type 5 Tags, allowing for interactions with a broader range of tags including tags that store iClass UID information, commonly used in identification badges.
- **MIFARE compatibility:** Our solution also works seamlessly with the MIFARE encryption method, ensuring secure reading and coding for systems using MIFARE.

### Supported tag types for secure authentication

NFC on Surface Pro 10 and Surface Pro (11th Edition) supports the use of FIDO2.0 keys, for secure authentication across various platforms, including Windows, Microsoft Entra ID, and MSA. For passwordless sign-in options, we use Microsoft Entra's passwordless sign-in capabilities. To learn more about FIDO key integration with Microsoft Entra, see [Microsoft Entra passwordless sign-in.](/entra/identity/authentication/concept-authentication-passwordless#fido2-security-keys)

The following FIDO2.0 keys are supported and recommended for use:

- **YubiKey**: Offers a portfolio of NFC security keys that support a broad set of security protocols.
- **Identiv**: Offers a range of security solutions, including FIDO2 security keys.
- **Thetis**: Provides FIDO2 certified security keys designed for secure access.
- **Token2 Card:** A compact and portable security key option.
- **AuthenTrend Card:** Known for their biometric and card-style FIDO2 security keys.
- **FEITIAN ePass:** Provides a range of NFC-enabled FIDO2 security keys, including options with USB-A and USB-C interfaces for MFA and PIV credential support.

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

1. Go to **Settings** > **Network & Internet** > **Airplane mode** and select **NFC**.
2. Adjust the Toggle switch to turn it off.

### Disable NFC via firmware

For a managed approach, IT admins can disable NFC using SEMM (Surface Enterprise Management Mode). SEMM allows IT admins to manage hardware features at the firmware level. With SEMM, you can enforce policies that disable NFC functionality, making it inaccessible regardless of software settings. To learn more, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md).

### FAQ

**What is the operational range of the NFC reader?**

- The NFC reader is designed to function within a range of up to 15 millimeters along the z-axis. This close proximity ensures secure communication between the reader and NFC-enabled devices or tags.

**Can the NFC reader operate independently of a keyboard?**

- Yes, the NFC reader is designed to work seamlessly both with and without a keyboard across all supported operating systems and modes. This flexibility allows for a wide range of use cases and device configurations.

**Does the NFC feature support waking up the device from sleep mode?**

- No, the current NFC technology doesn't support waking up the device from sleep mode. Surface Pro 10 and Surface Pro (11th Edition) must be awake and active for NFC interactions to occur.

**Do all Surface Pro devices support reading NFC?**

- No, currently NFC reader is only in Surface Pro 10 and Surface Pro (11th Edition) for Business and on Surface Go for Business devices.

**Is the NFC functionality different on Surface Pro 10 than Surface Go?**

- NFC functionality on Surface Pro 10 and Surface Pro (11th Edition) includes support for more cards and tag types. To learn more, see [NFC support in Surface Go for Business](surface-go-nfc-support.md).

### References

1. NFC is only available on Wi-Fi configurations of Surface Pro 10 and Surface Pro (11th Edition).

## Download NFC Lock Screens 

To help end users find the NFC reader on the device, a custom lock screen image is available to download and deploy to devices in your organization.

For the best user experience, we recommend modifying the following settings on Surface Pro 10 and Surface Pro (11th Edition):

1. Navigate to **Settings** > **Personalization** > **Colors**.

    - Toggle **Transparency effects** to **Off**.
  
2. Navigate to **Settings** > **Personalization** > **Lock screen**.

    - Toggle **Make the lock screen image react when I move my PC** to **Off**.
  
These settings can be managed when deploying the lock screen via Microsoft Intune or with Administrative Templates in Windows Group Policy. To learn more, see [Group Policy Settings Reference](https://www.microsoft.com/download/details.aspx?id=105668).

### NFC Lock Screen downloads

As shown in the following figure, available downloads include:

- A default lock screen with a user-friendly interface: NFC Lock Screen - with background.
- Separate black and white icons for customization.

:::image type="content" source="images/nfc-lockscreen-example-assets.png" alt-text="Screenshot that shows available downloads of NFC Lock Screen for Surface Pro 10.":::

Select your desired language to download.

### NFC Lock Screen - with background

- [English](https://download.microsoft.com/download/b/e/a/bea85adb-3f99-4054-b106-3b88afdf9a7b/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Arabic](https://download.microsoft.com/download/b/8/4/b842e46a-c816-4cee-a046-d60499509c71/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Bulgarian](https://download.microsoft.com/download/c/4/1/c41701b7-c98c-4fbd-a622-c728812b9103/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Chinese (Simplified)](https://download.microsoft.com/download/2/a/6/2a6ab796-b234-4306-9a47-02c1f4d7cc1b/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Chinese (Traditional)](https://download.microsoft.com/download/6/6/7/667b3b1b-1eb4-4aee-adae-a175da8287a9/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Czech](https://download.microsoft.com/download/a/c/d/acdf29d9-0238-4e62-9d26-07e9b0525f63/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Danish](https://download.microsoft.com/download/f/f/b/ffbde9ed-c30b-4f15-8a6c-5318bd044e5c/NFC%20Lock%20Screen%20-%20with%20background.png)
- [German](https://download.microsoft.com/download/b/8/4/b842e46a-c816-4cee-a046-d60499509c71/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Greek](https://download.microsoft.com/download/9/3/4/934ef991-c95a-4858-bbd2-92270e560774/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Spanish](https://download.microsoft.com/download/f/c/0/fc0569bb-e745-49a9-8618-34debd9195b3/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Estonian](https://download.microsoft.com/download/8/d/1/8d1214fe-1e36-46a3-92d8-d4b37a7e9109/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Finnish](https://download.microsoft.com/download/9/a/4/9a4131ca-c334-4154-8743-54862444e775/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Filipino](https://download.microsoft.com/download/e/f/c/efcf5205-4469-4572-9142-482840e29321/NFC%20Lock%20Screen%20-%20with%20background.png)
- [French](https://download.microsoft.com/download/e/d/a/edaecd0a-bd14-431f-b166-8acf79cea894/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Hindi](https://download.microsoft.com/download/3/3/a/33a45003-d84f-48fb-933d-4f45d035cc28/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Croatian](https://download.microsoft.com/download/5/d/1/5d1681b2-2879-4aeb-bacd-ea6a85257dff/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Hungarian](https://download.microsoft.com/download/b/1/2/b1228e77-5d54-4ce6-a6db-52440ae20b9a/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Italian](https://download.microsoft.com/download/7/3/0/73050d91-9152-4672-9701-7ccb506ac013/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Japanese](https://download.microsoft.com/download/4/5/d/45d0d036-0f27-4c76-bcaf-0e4a09ed1d91/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Korean](https://download.microsoft.com/download/e/2/2/e221c55b-b5a7-49f2-a630-44830571ff81/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Lithuanian](https://download.microsoft.com/download/e/4/1/e41f3e3c-5908-4163-afb4-1123dcf54ff8/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Latvian](https://download.microsoft.com/download/e/f/6/ef6ccf8a-b4c3-44e6-828d-084aca1ba106/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Malay](https://download.microsoft.com/download/6/9/5/6950b266-22f9-4ac8-81c4-4865343bde5e/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Norwegian](https://download.microsoft.com/download/4/f/e/4febcd28-b910-48be-b079-4dbc3e979384/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Dutch](https://download.microsoft.com/download/8/0/e/80e1d664-5041-4213-a573-78da7a055da5/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Polish](https://download.microsoft.com/download/f/6/a/f6a62aa4-f4cc-402e-ab3a-b8b1202dbfc8/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Portuguese](https://download.microsoft.com/download/1/9/7/1974fe09-9682-48e5-9904-38edd2f5a894/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Romanian](https://download.microsoft.com/download/0/4/1/0414aec5-db5c-43a0-9b2a-e75d5bba85d4/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Slovak](https://download.microsoft.com/download/8/5/3/85374894-8e47-4af3-9eb5-e26f87a21138/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Slovenian](https://download.microsoft.com/download/f/7/0/f70ab363-dc18-4457-b166-470e3b634531/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Swedish](https://download.microsoft.com/download/a/9/6/a9600986-0636-4f65-848d-a99acdfc063d/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Thai](https://download.microsoft.com/download/a/2/a/a2abe89c-b2ba-41f4-9b0c-f76616ef1a85/NFC%20Lock%20Screen%20-%20with%20background.png)
- [Vietnamese](https://download.microsoft.com/download/5/8/7/5870cb3f-3ab9-43b8-85df-e8c039aa1fe4/NFC%20Lock%20Screen%20-%20with%20background.png)

### NFC Lock Screen - transparent black icon

- [English](https://download.microsoft.com/download/b/e/a/bea85adb-3f99-4054-b106-3b88afdf9a7b/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Arabic](https://download.microsoft.com/download/b/8/4/b842e46a-c816-4cee-a046-d60499509c71/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Bulgarian](https://download.microsoft.com/download/c/4/1/c41701b7-c98c-4fbd-a622-c728812b9103/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Chinese (Simplified)](https://download.microsoft.com/download/2/a/6/2a6ab796-b234-4306-9a47-02c1f4d7cc1b/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Chinese (Traditional)](https://download.microsoft.com/download/6/6/7/667b3b1b-1eb4-4aee-adae-a175da8287a9/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Czech](https://download.microsoft.com/download/a/c/d/acdf29d9-0238-4e62-9d26-07e9b0525f63/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Danish](https://download.microsoft.com/download/f/f/b/ffbde9ed-c30b-4f15-8a6c-5318bd044e5c/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [German](https://download.microsoft.com/download/5/b/c/5bcf07e8-68f5-4c91-936b-7acd723de938/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Greek](https://download.microsoft.com/download/9/3/4/934ef991-c95a-4858-bbd2-92270e560774/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Spanish](https://download.microsoft.com/download/f/c/0/fc0569bb-e745-49a9-8618-34debd9195b3/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Estonian](https://download.microsoft.com/download/8/d/1/8d1214fe-1e36-46a3-92d8-d4b37a7e9109/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Finnish](https://download.microsoft.com/download/9/a/4/9a4131ca-c334-4154-8743-54862444e775/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Filipino](https://download.microsoft.com/download/e/f/c/efcf5205-4469-4572-9142-482840e29321/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [French](https://download.microsoft.com/download/e/d/a/edaecd0a-bd14-431f-b166-8acf79cea894/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Hindi](https://download.microsoft.com/download/3/3/a/33a45003-d84f-48fb-933d-4f45d035cc28/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Croatian](https://download.microsoft.com/download/5/d/1/5d1681b2-2879-4aeb-bacd-ea6a85257dff/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Hungarian](https://download.microsoft.com/download/b/1/2/b1228e77-5d54-4ce6-a6db-52440ae20b9a/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Italian](https://download.microsoft.com/download/7/3/0/73050d91-9152-4672-9701-7ccb506ac013/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Japanese](https://download.microsoft.com/download/4/5/d/45d0d036-0f27-4c76-bcaf-0e4a09ed1d91/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Korean](https://download.microsoft.com/download/e/2/2/e221c55b-b5a7-49f2-a630-44830571ff81/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Lithuanian](https://download.microsoft.com/download/e/4/1/e41f3e3c-5908-4163-afb4-1123dcf54ff8/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Latvian](https://download.microsoft.com/download/e/f/6/ef6ccf8a-b4c3-44e6-828d-084aca1ba106/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Malay](https://download.microsoft.com/download/6/9/5/6950b266-22f9-4ac8-81c4-4865343bde5e/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Norwegian](https://download.microsoft.com/download/4/f/e/4febcd28-b910-48be-b079-4dbc3e979384/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Dutch](https://download.microsoft.com/download/8/0/e/80e1d664-5041-4213-a573-78da7a055da5/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Polish](https://download.microsoft.com/download/f/6/a/f6a62aa4-f4cc-402e-ab3a-b8b1202dbfc8/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Portuguese](https://download.microsoft.com/download/1/9/7/1974fe09-9682-48e5-9904-38edd2f5a894/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Romanian](https://download.microsoft.com/download/0/4/1/0414aec5-db5c-43a0-9b2a-e75d5bba85d4/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Slovak](https://download.microsoft.com/download/8/5/3/85374894-8e47-4af3-9eb5-e26f87a21138/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Slovenian](https://download.microsoft.com/download/f/7/0/f70ab363-dc18-4457-b166-470e3b634531/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Swedish](https://download.microsoft.com/download/a/9/6/a9600986-0636-4f65-848d-a99acdfc063d/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Thai](https://download.microsoft.com/download/a/2/a/a2abe89c-b2ba-41f4-9b0c-f76616ef1a85/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)
- [Vietnamese](https://download.microsoft.com/download/5/8/7/5870cb3f-3ab9-43b8-85df-e8c039aa1fe4/NFC%20Lock%20Screen%20-%20transparent%20black%20icon.png)

### NFC Lock Screen - transparent white icon

- [English](https://download.microsoft.com/download/b/e/a/bea85adb-3f99-4054-b106-3b88afdf9a7b/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Arabic](https://download.microsoft.com/download/b/8/4/b842e46a-c816-4cee-a046-d60499509c71/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Bulgarian](https://download.microsoft.com/download/c/4/1/c41701b7-c98c-4fbd-a622-c728812b9103/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Chinese (Simplified)](https://download.microsoft.com/download/2/a/6/2a6ab796-b234-4306-9a47-02c1f4d7cc1b/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Chinese (Traditional)](https://download.microsoft.com/download/6/6/7/667b3b1b-1eb4-4aee-adae-a175da8287a9/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Czech](https://download.microsoft.com/download/a/c/d/acdf29d9-0238-4e62-9d26-07e9b0525f63/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Danish](https://download.microsoft.com/download/f/f/b/ffbde9ed-c30b-4f15-8a6c-5318bd044e5c/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [German](https://download.microsoft.com/download/5/b/c/5bcf07e8-68f5-4c91-936b-7acd723de938/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Greek](https://download.microsoft.com/download/9/3/4/934ef991-c95a-4858-bbd2-92270e560774/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Spanish](https://download.microsoft.com/download/f/c/0/fc0569bb-e745-49a9-8618-34debd9195b3/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Estonian](https://download.microsoft.com/download/8/d/1/8d1214fe-1e36-46a3-92d8-d4b37a7e9109/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Finnish](https://download.microsoft.com/download/9/a/4/9a4131ca-c334-4154-8743-54862444e775/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Filipino](https://download.microsoft.com/download/e/f/c/efcf5205-4469-4572-9142-482840e29321/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [French](https://download.microsoft.com/download/e/d/a/edaecd0a-bd14-431f-b166-8acf79cea894/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Hindi](https://download.microsoft.com/download/3/3/a/33a45003-d84f-48fb-933d-4f45d035cc28/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Croatian](https://download.microsoft.com/download/5/d/1/5d1681b2-2879-4aeb-bacd-ea6a85257dff/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Hungarian](https://download.microsoft.com/download/b/1/2/b1228e77-5d54-4ce6-a6db-52440ae20b9a/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Italian](https://download.microsoft.com/download/7/3/0/73050d91-9152-4672-9701-7ccb506ac013/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Japanese](https://download.microsoft.com/download/4/5/d/45d0d036-0f27-4c76-bcaf-0e4a09ed1d91/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Korean](https://download.microsoft.com/download/e/2/2/e221c55b-b5a7-49f2-a630-44830571ff81/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Lithuanian](https://download.microsoft.com/download/e/4/1/e41f3e3c-5908-4163-afb4-1123dcf54ff8/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Latvian](https://download.microsoft.com/download/e/f/6/ef6ccf8a-b4c3-44e6-828d-084aca1ba106/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Malay](https://download.microsoft.com/download/6/9/5/6950b266-22f9-4ac8-81c4-4865343bde5e/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Norwegian](https://download.microsoft.com/download/4/f/e/4febcd28-b910-48be-b079-4dbc3e979384/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Dutch](https://download.microsoft.com/download/8/0/e/80e1d664-5041-4213-a573-78da7a055da5/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Polish](https://download.microsoft.com/download/f/6/a/f6a62aa4-f4cc-402e-ab3a-b8b1202dbfc8/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Portuguese](https://download.microsoft.com/download/1/9/7/1974fe09-9682-48e5-9904-38edd2f5a894/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Romanian](https://download.microsoft.com/download/0/4/1/0414aec5-db5c-43a0-9b2a-e75d5bba85d4/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Slovak](https://download.microsoft.com/download/8/5/3/85374894-8e47-4af3-9eb5-e26f87a21138/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Slovenian](https://download.microsoft.com/download/f/7/0/f70ab363-dc18-4457-b166-470e3b634531/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Swedish](https://download.microsoft.com/download/a/9/6/a9600986-0636-4f65-848d-a99acdfc063d/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Thai](https://download.microsoft.com/download/a/2/a/a2abe89c-b2ba-41f4-9b0c-f76616ef1a85/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
- [Vietnamese](https://download.microsoft.com/download/5/8/7/5870cb3f-3ab9-43b8-85df-e8c039aa1fe4/NFC%20Lock%20Screen%20-%20transparent%20white%20icon.png)
