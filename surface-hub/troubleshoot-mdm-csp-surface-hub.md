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

- First, ensure that Surface Hub is enrolled in a mobile device management (MDM) provider--without errors and is syncing correctly. To verify, sign in to Surface Hub with an admin account, and go to **Settings** > **Surface Hub** > **Device management**. If you see a tenant with an email address, as indicated in the following figure, the device is enrolled in MDM.

    :::image type="content" source="images/hub-csp-fig1.png" alt-text="Screenshot of Device management settings on Surface Hub. ":::

- To check the sync status or any sync errors, select the email address and choose Info to display the device sync status.

    :::image type="content" source="images/hub-csp-fig2.png" alt-text="Screenshot of Device sync status on Surface Hub. ":::

## Troubleshoot MDM issues

1. Refer to the following documentation to verify that your CSP is supported on Surface Hub.
    - [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)
    - [CSPs supported in Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-support#csps-supported-in-microsoft-surface-hub)
    - [Policies in Policy CSP supported by Microsoft Surface Hub](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)

2. Upon confirmation that your CSP is supported on Surface Hub, sign in to the [Endpoint Manager Admin Center](https://endpoint.microsoft.com/). Choose **Devices** > **Configuration profiles** and select your CSP.
3. On the CSP page, ensure the **Configuration profile** is applied to a **Device group** (not a user group or device account), as indicated in the following figure. Note how in this example, the **Hub Devices** group is listed as an included group for the CSP and, in the subsequent figure, the Surface Hub is also a member of the group.

    :::image type="content" source="images/hub-csp-fig3.png" alt-text="Screenshot that shows the Hub Devices group is listed as an included group for the CSP.":::

    :::image type="content" source="images/hub-csp-fig4.png" alt-text="Screenshot that shows Surface Hub is a member of the group. ":::

4. Ensure your CSP is successfully deployed to your Surface Hub. In Endpoint Manager, select **Devices** > **All devices** > and choose your Surface Hub. Select **Device configuration** and check that the CSP is deployed successfully, as shown in the following figure.

    :::image type="content" source="images/hub-csp-fig5.png" alt-text="Screenshot that shows the CSP is successfully deployed to Surfasce Hub.":::

5. Ensure the appropriate [Intune URLs/IP ranges](/mem/intune/fundamentals/intune-endpoints) are allowed through the proxy/firewall.
