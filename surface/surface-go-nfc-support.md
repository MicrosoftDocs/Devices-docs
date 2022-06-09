---
title: NFC support in Surface Go for Business
description: This article provides an overview and FAQ about NFC support in Surface Go for Business devices
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/07/2022
ms.reviewer: oayakta
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
---

# NFC support in Surface Go for Business

Surface Go for Business devices are equipped with support for near field communication (NFC), allowing users to take advantage of several common scenarios with the exception of NFC card payments. Applicable scenarios include:

- **Passwordless authentication.** Azure AD supports FIDO2 security keys as an authentication method for signing into operating systems, applications, and services. To learn more, see the following blog post: [More NFC card reading accessories released for Surface Go](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/more-nfc-card-reading-accessories-released-for-surface-go/ba-p/2203298).
- **Proximity-based apps.** Applications that take advantage of proximity and location by using the RFID capability in Surface Go and a proximity sensor in Windows 10 and Windows 11.
- **Consumer apps.**  RFID-enabled apps capable of directing consumers to target websites. For example,  users can swipe an RFID-enabled prescription container that opens relevant product information.

:::image type="content" source="images/nfc-go.png" alt-text="NFC sensor inside Surface Go for Businesss" :::

## NFC FAQ: Surface Go for Business

**Is NFC available on all Surface Go devices?**

- NFC is only available on commercial versions of Surface Go: Surface Go for Business, Surface Go 2 for Business, and Surface Go 3 for Business devices.

**Does NFC support digital wallet or point of sale payments?**

- No. The NFC component doesn't include a secured element, and the interface isn't HID but a simple I2C.

**Can NFC be disabled through UEFI or DFCI?**

- Not at this time.

**Is multifactor authentication on Surface Go for Business compliant with FIDO 2.0 standards?**

- Yes, when combined with compliant authentication solutions and servers, such as using AuthenTrend Key Card, Windows Hello and Azure AD.

**Can I access and use NFC from the front of the device?**

- Yes, but only if the card has an independent power source like AuthenTrend. Passive cards can only be read from the back of the device--at close proximity of approximately 10 mm.

**How can I troubleshoot multiple failed read attempts?**

- Recall the location of the effective read area on the device.
- Remove any other NFC tags or NFC-enabled cards in the vicinity. Limited NFC support is available for ISO/IEC 14443-A tag types 1 and 2 with antenna diameters between 15 mm to 17 mm.
- We recommend using the Mifare Classic 1 K card type.
- Try keeping your badge in a nylon sleeve rather than a hard plastic case.

**Can I use NFC while the device is in a protective case?**

- Our Designed for Surface partners have created protective cases with a built-in NFC range extender designed for a variety of industries. These solutions include:

  - [aXtion Pro MPA/NFC](https://licensedhardware.azurewebsites.net/surface/product/dc426547-655b-eb11-8fed-00155dd3d394/axtion-pro-mpanfc-for-surface-go--go-2--go-3)
  - [aXtion Extreme MP NFC](https://licensedhardware.azurewebsites.net/surface/product/d1548288-82a1-ec11-b820-00155dd3dff8/axtion-extreme-mp-nfc-for-ms-surface-go-3-c1d2)
  - [aXtion Extreme MP NFC (ATEX Zone 2)](https://licensedhardware.azurewebsites.net/surface/product/6c85a536-debc-ec11-bea1-00155dd3d776/axtion-extreme-mp-nfc-for-ms-surface-go-3-atex-zone-2)

## Learn more

- [More NFC card reading accessories released for Surface Go](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/more-nfc-card-reading-accessories-released-for-surface-go/ba-p/2203298).
- [Surface Go 3: Lightweight Business Laptop - Microsoft Surface for Business](https://www.microsoft.com/surface/business/surface-go-3)
- [Find and connect with a Surface reseller in your market](https://www.microsoft.com/surface/business/where-to-buy-microsoft-surface)
- [Springcard](https://www.springcard.com/en/download/find/file/sq13163) tool for troubleshooting
