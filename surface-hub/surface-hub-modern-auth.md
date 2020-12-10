---
title: "Modern authentication on Surface Hub"
description: "This page describes use of Modern authentication on Surface Hub in contrast to legacy basic authentication."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
---

# Modern authentication on Surface Hub

Support for modern authentication of cloud-based accounts is fully integrated in [Windows 10 Team 2020 Update](surface-hub-2020-update.md). Once you install the 2020 update, you can migrate from legacy basic authentication and use the latest security improvements from Microsoft Azure and Exchange Online. With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.

For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com). Do not use the legacy format – Contoso\alias, which is not supported for modern authentication. For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).

> [!NOTE]
> Surface Hub does not support modern authentication for on-premises accounts. The accounts must be created in the cloud.

