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

Surface Go for Business devices have limited near field communication (NFC) support. Common scenarios applicable to Surface Go, Surface Go 2, and Surface Go 3 include:
 
- **Passwordless authentication.** Azure AD supports FIDO2 security keys as an authentication method for signing into operating systems, applications, and services. To learn more, see the following blog post: [More NFC card reading accessories released for Surface Go](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/more-nfc-card-reading-accessories-released-for-surface-go/ba-p/2203298).
- **Proximity-based apps.** Applications that take advantage of proximity and location by using the RFID capability in Surface Go and a proximity sensor in Windows 10.
- **Consumer apps.**  RFID-enabled apps capable of directing consumers to target websites. For example,  users can swipe an RFID-enabled prescription container that opens relevant product information.

## NFC FAQ: Surface Go for Business

**Is NFC available on all Surface Go devices?**

- NFC is only available on commercial versions of Surface Go: Surface Go for Business, Surface Go 2 for Business, and Surface Go 3 for Business devices.

**Does NFC support digital wallet or point of sale payments?**

-  No. The NFC component does not include a secured element, and the interface is not HID but a simple I2C.

**Can NFC be disabled through UEFI or DFCI?**

- Not at this time.

**Is multifactor authentication on Surface Go for Business compliant with FIDO 2.0 standards?**

- Yes, when combined with compliant authentication solutions and servers, such as using AuthenTrend Key Card, Windows Hello and Azure AD.

**Can I access and use NFC from the front of the device?**

- Yes, but only if the card has an independent power source like AuthenTrend. Passive cards can only be read from the back of the device -- at very close proximity of approximately 10 mm.

**How can I troubleshoot multiple failed read attempts?**

- Recall the location of the effective read area on the device.
- Remove any other NFC tags or NFC-enabled cards in the vicinity. Limited NFC support is available for ISO/IEC 14443-A tag types 1 and 2 with antenna diameters between 15mm to 17mm.
- We recommend using the Mifare Classic 1K card type.
- Try keeping your badge in a nylon sleeve rather than a hard plastic case.

## Learn more

- [More NFC card reading accessories released for Surface Go](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/more-nfc-card-reading-accessories-released-for-surface-go/ba-p/2203298).
- [Surface Go 3: Lightweight Business Laptop - Microsoft Surface for Business](https://www.microsoft.com/surface/business/surface-go-3)
- [Find and connect with a Surface reseller in your market](https://www.microsoft.com/surface/business/where-to-buy-microsoft-surface)
- [Springcard](https://www.springcard.com/en/download/find/file/sq13163) tool for troubleshooting

 
 
 

