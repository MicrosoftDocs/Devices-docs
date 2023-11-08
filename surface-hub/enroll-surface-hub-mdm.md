---
title: Enroll Surface Hub to MDM provider
description: This page explains how to enroll Surface Hub to MDM provider
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 01/27/2023
ms.localizationpriority: medium
appliesto:
- Surface Hub 2S
- Surface Hub
---

# Enroll Surface Hub into MDM management

You can enroll Surface into Microsoft Intune or other MDM provider via manual or auto enrollment.

## Manual enrollment

1. Open the **Settings** app and sign in as a local administrator. Select **Surface Hub** > **Device management** and then select **+Device management**.
2. You will be prompted to sign in with the account to use for your MDM provider. After authenticating, the device automatically enrolls with your MDM provider.

> [!TIP]
> If you’re using Intune and the server address is not detected, enter **manage.microsoft.com**.

> [!NOTE]
> MDM enrollment uses the account details provided for authentication. The account must have permissions to enroll a Windows device as well as an Intune license (or the equivalent enrollment promissions configured in your third-party MDM provider).

<a name='auto-enrollment--azure-ad-affiliated'></a>

## Auto Enrollment — Microsoft Entra affiliated

During the [initial setup process](/surface-hub/first-run-program-surface-hub#microsoft-azure-active-directory), when affiliating Surface Hub with a Microsoft Entra tenant that has Intune auto enrollment enabled, the device will automatically enroll with Intune. To learn more, refer to [Intune enrollment methods for Windows devices](/intune/enrollment/windows-enrollment-methods). Microsoft Entra affiliation and Intune auto enrollment are required for the Surface Hub to be a "compliant device" in Intune.

## Manage Surface Hub via MDM

- See [Manage Surface Hub with an MDM provider](manage-settings-with-mdm-for-surface-hub.md)
