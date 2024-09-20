---
title: Surface Management Portal  
description: Manage, monitor, and maintain Surface devices efficiently with the Surface Management Portal in Microsoft Intune Admin Center. 
ms.service: surface  
ms.localizationpriority: medium  
author: coveminer  
ms.author: chauncel  
ms.topic: how-to  
ms.date: 09/16/2024  
ms.reviewer: rohitmannan  
manager: frankbu  
appliesto:  
- Windows 10  
- Windows 11  
ms.collection: essentials-manage  
---

# Surface Management Portal overview

The Surface Management Portal, integrated into the Microsoft Intune Admin Center, provides a centralized platform to manage and monitor Surface devices at scale. It offers end-to-end visibility, allowing you to address issues before they escalate.

With the Surface Management Portal, you can:

- Gain insights into device compliance, support activity, and warranty coverage.
- Monitor the status of each device, including warranty expirations and active support requests.
- Centralize Surface-specific device administration in a single environment.
- Automatically access comprehensive information from your Intune-enrolled Surface devices, which flows into the Surface Management Portal when users sign in for the first time.

## Access Surface Management Portal

### If you don't have an Intune subscription

1. Visit the [Intune product page](https://www.microsoft.com/security/business/endpoint-management/microsoft-intune) to learn more about the service.
2. Select **Start a free trial** to begin the sign-up process, as described in [Try Microsoft Intune for free](/mem/intune/fundamentals/free-trial-sign-up).
3. Follow the prompts to create an account and choose a [subscription plan](https://www.microsoft.com/security/business/microsoft-intune-pricing) that fits your organization's needs.
4. Complete the setup wizard to configure your Intune environment, adding users and setting up device policies as needed.
5. While Intune supports a wide range of devices, you must [enroll at least one Surface device](/mem/intune/user-help/enroll-windows-10-device) to access the Surface Management Portal.
6. After subscribing to Intune and enrolling at least one Surface device, proceed to the next section.

### If you have an Intune subscription

- Sign in to the [Microsoft Intune Admin Center](https://endpoint.microsoft.com), and select **All services** > **Surface Management Portal**.

   :::image type="content" source="images/surface-management-portal/surface-management-portal-start.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-start.png" alt-text="Screenshot that shows the Surface Management Portal on the Intune admin center home page.":::

## Prerequisites

Before proceeding, you first need to configure at least one admin role. To learn more see:

- [Assign admin roles for Surface portals](surface-portal-admin-roles.md)
- [Add an admin](/microsoft-365/admin/add-users/assign-admin-roles#steps-add-an-admin)

## IT tasks in Surface Management Portal

This section includes key tasks to ensure your Surface devices remain compliant, up-to-date, and fully functional:

- [Manage Surface device warranty and coverage](#manage-surface-device-warranty-and-coverage)
- [Create and track support requests](#create-and-track-support-requests)
- [Create and track service requests for device replacement or repair](#create-and-track-service-requests-for-device-replacement-or-repair)
- [Get insights to proactively monitor and manage Surface devices](#get-insights-to-proactively-monitor-and-manage-surface-devices)
- [View related Surface IT Tools](#view-related-surface-it-tools)
- [Extend functionality with the Surface API Management Service](#extend-functionality-with-the-surface-api-management-service)
- [View carbon emissions for Surface devices](#view-carbon-emissions-for-surface-devices)
- [Review administrator roles](#review-administrator-roles)

### Manage Surface device warranty and coverage

Managing the warranty status of each device helps you stay on top of expiring warranties and out-of-coverage devices. The portal lets you quickly view:

- Devices within the warranty period.
- Devices expiring soon.
- Devices out of warranty.
- Devices eligible for optional coverage.

### Create and track support requests

The Surface Management Portal provides visibility into support activity and the status of each request.

:::image type="content" source="images/surface-management-portal/surface-management-portal-support.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-support.png" alt-text="Screenshot that shows where to submit a new support request on the Surface Management Portal.":::

To create and submit new requests for one or more devices:

1. Go to the **Support** tab and select **New support request**.
2. **Select the device**: Choose the product from the drop-down list.
3. **Describe the issue**: Provide detailed information about the issue.
4. **Enter contact details**: Provide your contact information and preferred communication method.
5. **Review and submit**: Verify all information, then select **Submit**.
6. **Track support requests**: Go to the Surface Management Portal home page and select **View all support requests**. 


### Create and track service requests for device replacement or repair

1. Select **Create service request** from the service orders screen.
2. **Choose the device or accessory for repair**: Select whether it's a **Serialized Device/Accessory** (for example, Type covers, Dock) or a **Non-serialized Accessory** (for example, Mouse, Power Supply).
3. **Add Service request details**: Enter the necessary details and select the product from the drop-down menu. You can also select multiple devices by choosing **+ Select devices**.
4. **Describe the issue**: Provide a detailed description of the issue and attach any relevant files.
5. **Provide contact information**: Enter your contact details and specify your preferred communication method.
6. **Review and submit the request**: Once verified, select **Submit**.
7. **Track repair requests**: Go to the Surface Management Portal home page and select **View all service orders.**

### Get insights to proactively monitor and manage Surface devices

The **Insights** tab allows you to monitor the health, compliance, and properties of all managed Surface devices. The dashboard displays various insights, each represented by a card. You can pin, rearrange, or expand these cards to view more details.

#### Available insights

- **Devices not compliant**: Displays the number of devices that aren't compliant with your organization’s policies, such as missing updates or failing security requirements.
- **Devices inactive 30+ days**: Lists devices that have been inactive for over 30 days.
- **Devices not registered**: Shows devices that haven't been registered in the system.
- **Devices covered**: Displays the number of devices currently covered by warranty or support programs.
- **Devices expiring within 60 days**: Identifies devices whose warranty or support coverage expires within 60 days.
- **Devices eligible for optional coverage**: Displays devices that qualify for optional coverage plans but haven't been enrolled.
- **Devices expired**: Lists devices whose warranty or support coverage has expired.
- **Devices not encrypted**: Shows devices without drive encryption enabled, which could pose a security risk.
- **Devices with less than 10% storage**: Displays devices running low on disk space.
- **Devices eligible for Windows 11 update**: Lists devices eligible for an upgrade to Windows 11 but not yet updated.

#### Customize insights dashboard

- **Manage insights**: Select **Manage insights** to add or remove insights from your dashboard. You can drag and drop insight cards to reorder them based on your priorities.
- **View details**: Select the title of any insight card to see more details, such as device names, dates, and available actions.

#### Recommended insights

- **Proactive monitoring**: Regularly review insights such as "Devices not compliant" and "Devices not encrypted" to maintain security and compliance.
- **Warranty management**: Use insights like "Devices expiring within 60 days" and "Devices expired" to avoid lapses in service.

### View related Surface IT Tools

The **Surface IT Tools** section provides information and links to various tools designed to help you manage and support Surface devices.

### Surface IT Toolkit

Provides device management tools in a downloadable application to centralize and improve device administration for IT teams.

#### Tool Library installers (available in Surface IT Toolkit)

- **Asset Tag**: A command-line interface (CLI tool to view, assign, and modify an asset tag stored in the Surface device's UEFI.
- **UEFI Assemblies**: A lightweight installer to apply UEFI management assemblies via PowerShell.
- **Diagnostics App Console**: A tool for remote diagnostics and log capturing.
- **Brightness Control**: A tool to optimize power management by adjusting brightness settings for kiosk or "always-on" scenarios.

#### Extend functionality with the Surface API Management Service

The Surface API Management Service provides direct access to Microsoft coverage and entitlement information for Surface devices through API endpoints. This service integrates with your systems to streamline device and asset management.

To learn more, see [Introducing the Surface API Management Service](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-the-surface-api-management-service/ba-p/4107282).

### View carbon emissions for Surface devices

The **Carbon emissions** tab helps you track and potentially reduce the environmental impact of your Surface devices by providing insights into emissions across the product lifecycle.

- **Product Age Selection**: Filter carbon emission data by the age of your Surface devices.
- **Total Emissions Estimate**: View estimated emissions from production and usage.

#### Emissions lifecycle

- **Production (86.10%)**: Most emissions come from materials and production.
- **Transportation (0.03%)**: Minimal emissions from transporting devices.
- **Usage (13.88%)**: Energy consumption during device usage.
- **End of Life (0.00%)**: Estimated emissions from device disposal.

### Review administrator roles

- For details about all available admin roles, see [Assign admin roles for Surface portals](surface-portal-admin-roles.md).

- To learn more about configuring roles, see [Add an admin](/microsoft-365/admin/add-users/assign-admin-roles#steps-add-an-admin).

## Try Surface Management Portal for free

Surface Management Portal is available to customers who use Microsoft Intune Admin Center and enroll at least one Surface device through Intune. If you’re new to Intune, set up your Intune tenant today by visiting [Try Microsoft Intune for free](/mem/intune/fundamentals/free-trial-sign-up).

## Learn more

- [(Re)Introducing Surface portals - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/re-introducing-the-surface-management-and-support-suite/ba-p/4109526)
- [Introducing the Surface API Management Service - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-the-surface-api-management-service/ba-p/4107282)
- [Assign admin roles for Surface portals](surface-portal-admin-roles.md)
- [Surface portals overview](surface-portals.md)
- [Surface Support Portal overview](surface-support-portal.md)
- [Surface IT Toolkit](surface-it-toolkit.md)
