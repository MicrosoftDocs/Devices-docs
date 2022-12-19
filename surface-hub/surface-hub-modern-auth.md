---
title: "Modern authentication on Surface Hub"
description: "This page describes use of Modern authentication on Surface Hub in contrast to legacy basic authentication."
keywords: separate values with commas
ms.prod: surface-hub

author: coveminer
ms.author: hachidan
manager: frankbu
audience: Admin
ms.topic: how-to
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
---

# Modern authentication on Surface Hub

The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios. Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online. With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and OAuth-based authentication when syncing the device account with Exchange Online.

For new cloud-based accounts, the Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply adding the device account to the Surface Hub using the format [alias@contoso.com](mailto:alias@contoso.com). Do not use the legacy format – Contoso\alias, which is not supported for modern authentication. For more information, see [create and test a device account](create-and-test-a-device-account-surface-hub.md).

> [!NOTE]
> Modern authentication is not supported for on-premises Surface Hub accounts. For full modern auth functionality, the accounts must use [cloud authentication in Azure AD](/azure/active-directory/hybrid/choose-ad-authn#cloud-authentication). If [federated authentication](/azure/active-directory/hybrid/choose-ad-authn#federated-authentication) is used, the account authentication with the federated identity provider will still use legacy protocols.
