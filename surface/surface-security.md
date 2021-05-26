---
title: Surface security overview
description: This article provides an overview of Surface device security
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 05/28/2021
ms.reviewer: brrecord
manager: laurawi
audience: itpro
---

# Surface security overview

|                  | Protect with hardware root of trust                                                                                                                                                            | Defend against firmware level attack                                                                                                                                                                                          | Prevent access to unverified code                                                                                                                                                                                      | Protect identities from external threats                                                                                                                                        |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface devices**  | Surface’s Root of Trust checks signatures and measurements at each stage to tightly ensure each stage is secure and authentic before allowing the next phase of boot to proceed.               | Microsoft builds its own firmware from the ground up, rather than relying on 3rd party source code. This allows Microsoft to continuously provides updates, down to the firmware level to protect against the latest threats. | With Hypervisor Code Integrity (HVCI), Windows 10 devices are protected from running any unverified code. Code running within the trusted computing base runs with integrity and is not subject to exploits or attacks | Protect Identities from external threats with Windows Hello2. Credential Guard ensures that identity and domain credentials are isolated and protected in a secure environment. |
| **Secured core PCs** | Partnering with leading PC manufacturers and silicon vendors, secured-core PCs use industry standard hardware root of trust coupled with security capabilities built into today’s modern CPUs. | Secured-core PCs use hardware rooted security in the modern CPU to launch the system into a trusted state, preventing advanced malware from tampering with the system and attacking at the firmware level.                    |                                                                                                                                                                                                                        |                                                                                                                                                                                 |


## placeholder topic

