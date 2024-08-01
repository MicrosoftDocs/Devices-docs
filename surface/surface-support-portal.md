---
title: Surface Support Portal overview
description: This article describes how Surface Support Portal provides a centralized solution for commercial customers to get help with a Surface device issue including requests to replace or repair your device, look up current warranty and protection plans, and register devices for Windows Autopilot enrollment.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 06/07/2024
ms.reviewer: cchauvet
manager: frankbu
appliesto:
- Windows 10
- Windows 11
ms.collection: essentials-manage
---

# Surface Support Portal overview

The [Surface Support Portal](https://admin.microsoft.com/AdminPortal#/support/microsoftsurfacesupport) provides a self-serve, centralized solution to get help if you're experiencing an issue with your Surface device. You can also submit requests to replace or repair your device, look up current warranty and protection plans, and register devices for Windows Autopilot enrollment.

:::image type="content" source="images/surface-service-repair/m365-admincenter-repair-request.png" alt-text="Screenshot of Surface Support Portal.":::

>[!TIP]
>To learn more about accessing the Surface Support Portal or the Microsoft Intune-based [Surface Management Portal](surface-management-portal.md), see [Streamline access to Surface Portals for commercial customers](streamline-access-surface-portals.md).

- [Create a service request for device replacement or repair](#create-a-service-request-for-device-replacement-or-repair)
- [Create a support request](#create-a-support-request)
- [Register devices](#register-devices)
- [View coverage and manage warranty requests](#manage-warranty)

## Create a service request for device replacement or repair

1. Select **Create service request** and follow the instructions. Provide a detailed description of the problem or issue you're experiencing with the device or accessory.

    :::image type="content" source="images/service-request.png" alt-text="Screenshot of entering a service request for device replacement or repair.":::

2. Select **Submit** to send your service request.

## Create a support request

1. Select **Create support request**  and enter details of the issue you're experiencing. More detailed descriptions can lead to quicker resolutions.

    :::image type="content" source="images/surface-support-request.png" alt-text="Screenshot of entering a support request.":::

2. Select **Contact me**  to submit your support request.

Your support request is listed under "Support requests" where you can track the status and manage any open or closed requests.

## Register devices

The Surface Support Portal enables IT admins to register devices, allowing you to associate devices with your tenant. This facilitates  Windows Autopilot enrollment, allowing for seamless device management and integration into your organization's IT infrastructure. To register your devices, follow these steps

1. **Begin new device registration:**
   - Select **Register devices**. There are options to either begin a new device registration or request support.

2. **Add a single device:**
   - Enter the device serial number and PO (Purchase Order) number in the provided fields.
   - Select **Add** to register the device.

    :::image type="content" source="images/autopilot-registration.png" alt-text="Screenshot of registering devices for Windows Autopilot enrollment. ":::

3. **Add devices in bulk:**
     - Prepare a CSV file with two columns, **Device Serial Number** and **PO Number.** Ensure all serial numbers include leading zeros.
     - Select **Import CSV** to upload your file, or download a sample CSV template for reference.

4. **Confirm tenant details:**
   - Provide the required information, including contact email, tenant ID, and domain name.
   - These details are prepopulated from your signed-in account.

5. **Provide proof of ownership:**
   - Attach purchase receipts or invoices that include your company name and all device serial numbers listed.

6. **Finalize registration:**
   - Verify all details are correct and select **Request registration**.
   - Your registered devices are listed under **Date & Time,** **Request number,** and **State** for tracking and management.

   :::image type="content" source="images/finalize-registration.png" alt-text="Screenshot of submitting registration request.":::

## Manage warranty

- Select **Coverage** to view devices covered under warranty, the time remaining for each device under warranty, and related details.
- Select **Warranty & service** to view the status of service orders and related details.
- To learn more, see [Manage your Surface warranty & service requests](self-serve-warranty-service.md)

## View information about IT tools

- Select **Surface IT Tools** to access details about the latest tools, including the [Surface IT Toolkit](surface-it-toolkit.md), [Surface Diagnostics Toolkit for Business](surface-diagnostic-toolkit-business.md), and [Surface API Management Service](https://github.com/microsoft/SurfaceApiManagementService).

## Learn more

- [Surface Management Portal](surface-management-portal.md)
- [Manage your Surface warranty & service requests](self-serve-warranty-service.md)
- [Streamline access to Surface Portals for commercial customers](streamline-access-surface-portals.md)
- [Surface IT Toolkit](surface-it-toolkit.md)
