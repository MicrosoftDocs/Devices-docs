---
title: Surface portals overview
description: Explore centralized solutions for IT admins to manage Surface devices at scale. Learn about the Surface Management Portal and Surface Support Portal, designed for efficient device monitoring, warranty management, and support requests.
ms.service: windows-11
ms.localizationpriority: medium
author: coveminer
ms.author: rbrooker
ms.topic: how-to
ms.date: 09/15/2023
ms.reviewer: rbrooker
manager: frankbu
appliesto:
- Windows 11
- Windows 10
ms.collection: essentials-manage
---

# Surface portals overview

Surface portals offer IT admins a centralized solution for managing and monitoring Surface devices across an organization. These tools help streamline support and warranty processes, making device management more efficient.

With Surface portals, you can:

- Centralize management of device warranties and support requests. Initiate single or bulk warranty claims.
- Gain insights into your warranty status and claims—in a single view.
- Monitor the health of all your Surface devices and get notifications about any unusual device status, which can help reduce IT costs.
- Access a unified interface for Surface device management tasks.

## Choose your portal

| Solution                                                                                                                              | Best for                                                                          | Requirements                                                                                             | Notes                                             |
| ----------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| [Surface Management Portal](#surface-management-portal)                          | Customers who already use Microsoft Intune to manage multiple devices at scale | - [Microsoft Intune Admin Center](https://endpoint.microsoft.com/)<br>- [Intune subscription](https://www.microsoft.com/security/business/microsoft-intune-pricing)     | -  Manage warranty & claims <br>- Manage support requests<br>- Get Device insights & Device Health <br><br> - **Automatic enrollment:** Surface devices are automatically enrolled       |
| [Surface Support Portal](#surface-support-portal) | Customers looking to streamline support for their employees & users            | - [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/)<br>- [Microsoft 365 subscription](/microsoft-365/commerce/try-or-buy-microsoft-365) | - Manage warranty & claims <br>- Manage support requests <br><br>- **Manual enrollment:** Customers need to manually add Surface devices 

## Surface Management Portal

Commercial customers can use the [Surface Management Portal](surface-management-portal.md) to self-serve their Surface devices’ service requests within the Microsoft Intune admin center.

1. Sign in to the [Microsoft Intune admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **All services** > **Surface Management Portal**.
2. To submit a device repair or replacement request, select **Create service request**. For eligible devices and regional availability, see [Microsoft in-region repair](microsoft-in-region-same-unit-repair.md).

    :::image type="content" source="images/surface-service-repair/smp-repair-request.png" alt-text="Screenshot of Surface Management Portal showing New repair request feature.":::
3. 

## Surface Support Portal

Microsoft 365 Business customers are eligible to use the Surface Support Portal to self-serve their Surface devices’ service requests within the Microsoft 365 Admin Center.

1. Sign in to the [Microsoft Surface support - Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/support/microsoftsurfacesupport).
2. Select **Create service request**. For eligible devices and regional availability, see [Microsoft in-region repair](microsoft-in-region-same-unit-repair.md).

:::image type="content" source="images/surface-service-repair/m365-admincenter-repair-request.png" alt-text="Screenshot of Microsoft 365 admin center showing New repair request feature.":::

The Surface Support Portal allows you to:

- Add one or multiple devices simultaneously to view current warranty and protection plans.
- Select one or multiple devices to create service requests.
- Track the real-time status of device repairs and transit times.

When you add a Microsoft 365 tenant to the tool, Admin roles are granted more permissions, as shown in the following table.

### Compare portals




### Microsoft Entra roles for Surface portals

The following admin roles apply to the Surface Management Portal and the Surface Support Portal.

| Role                                      | Permissions                                                                                                                                                                                 |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Microsoft Hardware Warranty Administrator<sup>1</sup> | View all service requests<br>Create/manage device replacement requests<br>Add/edit/delete ship-to addresses<br>Read-only access to the Microsoft 365 tenant outside of the Surface Support Portal |
| Microsoft Hardware Warranty Specialist<sup>1</sup>     | View own service requests<br>Create/manage device replacement requests<br>Read-only access to the Microsoft 365 tenant outside of the Surface Support Portal                                        |
| Service Support Admin                     | View service requests<br>Create/manage device replacement requests                                                                                                                          |
| Billing Admin                             | View service requests<br>Create/manage device replacement requests<br>Add/edit/delete ship-to addresses                                                                                   |

1. *Requires **Read Only Operator** role for access*.

## Learn more

- [(Re)Introducing Surface portals - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/re-introducing-the-surface-management-and-support-suite/ba-p/4109526)
- [Surface Management Portal](surface-management-portal.md)
- [Microsoft Surface Support Portal](surface-support-portal.md)
- [Surface IT Toolkit](surface-it-toolkit.md)
