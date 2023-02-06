---
title: Troubleshoot configuration service provider policy settings for Surface Hub
description: Configuration service providers (CSPs) provide a rich set of options for deploying policy settings to Surface Hub. This page explains the most troubleshooting common steps if your CSP policy settings are not showing up on your Surface Hub.
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: troubleshooting
ms.date: 02/03/2023
ms.localizationpriority: medium
---
# Troubleshoot configuration service provider policy settings for Surface Hub

[Configuration service providers](/surface-hub/manage-settings-with-mdm-for-surface-hub#manage-surface-hub-windows-10-team-settings-with-intune) (CSPs) enable a rich set of options for deploying policy settings to Surface Hub. Try these common troubleshooting steps if your CSP settings are not working on your Surface Hub. 

1. First, ensure that Surface Hub is enrolled in a mobile device management (MDM) provider--without errors and is syncing correctly. To verify, sign in to Surface Hub with an admin account, and go to **Settings** > **Surface Hub** > **Device management**. If you see a tenant with an email address, the device is enrolled in MDM.

2. To check the sync status or any sync errors, select the email address and choose Info to display the device sync status.

## Troubleshoot MDM issues

1. Refer to the following documentation to verify that your CSP is supported on Surface Hub.
    - [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)
    - [CSPs supported in Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-support#csps-supported-in-microsoft-surface-hub)
    - [Policies in Policy CSP supported by Microsoft Surface Hub](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)

2. Upon confirmation that your CSP is supported on Surface Hub, sign in to the [Endpoint Manager Admin Center](https://endpoint.microsoft.com/). Choose **Devices** > **Configuration profiles** and select your CSP.
3. On the CSP page, ensure the **Configuration profile** is applied to a **Device group** (not a user group or device account).
4. Ensure your CSP is successfully deployed to your Surface Hub. In Endpoint Manager, select **Devices** > **All devices** > and choose your Surface Hub. 
5. Select **Device configuration** and check that the CSP is deployed successfully.
6. Ensure the appropriate [Intune URLs/IP ranges](/mem/intune/fundamentals/intune-endpoints) are allowed through the proxy/firewall.
