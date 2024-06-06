---
title: Surface Support Portal overview
description: This article describes how Surface Support Portal provides a centralized solution for Microsoft 365 Business customers to get help with a Surface device issue including requests to replace or repair your device, look up current warranty and protection plans, and register devices for Windows Autopilot enrollment.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 06/05/2024
ms.reviewer: cchauvet
manager: frankbu
appliesto:
- Windows 10
- Windows 11
ms.collection: essentials-manage
---

# Surface Support Portal overview

The Microsoft 365 Surface Support Portal provides a self-serve, centralized solution to get help if you're experiencing an issue with your Surface device. You can also submit requests to replace or repair your device, look up current warranty and protection plans, and register devices for Windows Autopilot enrollment. 

:::image type="content" source="images/surface-support-portal.png" alt-text="Screenshot of Surface Support Portal.":::

- [Create a support request](#create-a-support-request)
- [Create a service request for device replacement or repair](#create-a-service-request-for-device-replacement-or-repair)
- [Register devices](#register-devices)

## Create a support request

1. Select **Create support request** and choose a Support provider. Your Microsoft 365 account is purchased through a partner. You can choose to get support from Microsoft or contact your purchase partner. If you don't see your partner listed, go to the [Microsoft Partner Center](https://partner.microsoft.com/dashboard/v2/home). 

    :::image type="content" source="images/surface-support-request.png" alt-text="Screenshot of entering a support request.":::

2. For Microsoft support, enter details of the issue you're experiencing. More detailed descriptions can lead to quicker resolutions.
3. Select **Contact me**  to submit your support request.

Your support request is listed under "Support requests" where you can track the status and manage any open or closed requests.

## Create a service request for device replacement or repair

1. Select **Create service request** and follow the instructions. Provide a detailed description of the problem or issue you're experiencing with the device or accessory.

    :::image type="content" source="images/service-request.png" alt-text="Screenshot of entering a service request for device replacement or repair.":::

2. Select **Submit** to send your service request.

## Register devices 

The Surface Support Portal enables IT admins to register devices, allowing you to associate devices with your tenant. This facilitates  Windows Autopilot enrollment, allowing for seamless device management and integration into your organization's IT infrastructure. Follow these steps to register your devices:

:::image type="content" source="images/autopilot-registration.png" alt-text="Screenshot of registering devices for Windows Autopilot enrollment. ":::

1. **Begin new device registration:**
   - Select **Register devices**. You'll see options to either begin a new device registration or request support.

2. **Add devices:**
   - **Add a single device:**
     - Enter the device serial number and PO (Purchase Order) number in the provided fields.
     - Select **Add** to register the device.
   - **Add devices in bulk:**
     - Prepare a CSV file with two columns, **Device Serial Number** and **PO Number.** Ensure all serial numbers include leading zeros.
     - Select **Import CSV** to upload your file, or download a sample CSV template for reference.

3. **Submit a registration request:**
   - Provide the required information, including contact email, tenant ID, and domain name.
   - These details should be prepopulated from your logged-in account.

4. **Proof of ownership:**
   - Attach purchase receipts or invoices that include your company name and all device serial numbers listed.
   - Supported file types include jpg, png, and pdf. The maximum file size is 5 MB.
   - Drag and drop your files into the designated area or browse to select the files.

5. **Finalize registration:**
   - Verify all details are correct, then submit your registration request.
   - Your registered devices are listed under **Date & Time,** **Request number,** and **State** for tracking and management.

## Learn more

- [What is Microsoft Surface Management Portal?](/mem/intune/fundamentals/surface-management-portal?)
- [Microsoft Mechanics](https://youtu.be/_MmutkqNudk)
- [Surface IT Pro Blog post: Surface Management Portal](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-management-portal/ba-p/1419017)
