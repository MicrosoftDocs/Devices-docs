---
title: Prepare your environment to manage Surface Portals
description: Guide to assigning roles for managing Surface devices in Microsoft 365 Admin Center, ensuring secure and efficient operations. 
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 09/16/2024
ms.reviewer: rohitmannan  
manager: frankbu
appliesto:
- Windows 11
- Windows 10
---

# Prepare your environment to manage Surface portals

Microsoft provides a range of built-in administrator roles designed for managing Surface devices through the [Surface Management Portal](surface-management-portal.md) and the [Surface Support Portal](surface-support-portal.md). These roles are tailored to facilitate efficient management and maintenance of Surface hardware within your organization.

## Before you begin

Before starting the setup, you must assign at least one administrative role to manage the portals effectively.

### Recommended role: Microsoft Hardware Warranty Administrator

The Microsoft Hardware Warranty Administrator role is ideally suited for those responsible for overseeing the comprehensive management of Surface devices, ensuring that all aspects of service requests, warranty claims, and operational efficiencies are handled effectively.

- **Comprehensive access:** This role grants full capabilities to view all service requests, manage device replacements, and read and update shipping addresses, which are crucial for overseeing the entire lifecycle of Surface device management.
- **Specific Surface Support:** Tailored specifically for managing Microsoft-manufactured hardware like Surface and HoloLens, ensuring specialized support.
- **Operational efficiency:** Enables administrators to efficiently handle warranty claims and support tickets, central to managing operational continuity.

### Assign admin roles for Surface portals

1. Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com) and sign in using your administrator credentials.
2. Select **Roles** > **Role assignments** to view all the available roles.
3. Use the search bar or scroll to find the appropriate role; for example, **Microsoft Hardware Warranty Administrator**.
4. Select the role to open its details. In the **Assigned** tab, select **Add users**. Search for users by name or email address.
5. After selecting the users, review the list to ensure accuracy. To confirm the assignment, select **Save**.
6. Document the changes for internal tracking and compliance purposes. Inform the assigned users about their new roles and any actions they might need to take or changes they should be aware of.

### Roles and permissions

Here's a comprehensive table of the available roles with their permissions and descriptions:

| Role                                  | Permissions                                                                                                                                                 | Description                                                   |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| **Microsoft Hardware Warranty Administrator**<sup>1</sup> | - View all service requests<br>- Create/manage device replacement requests<br>- Add/edit/delete ship-to addresses<br>- Read-only access to the Microsoft 365 tenant outside of the Surface Support Portal | Best suited for managing comprehensive warranty-related tasks and service requests for Surface devices. |
| **Microsoft Hardware Warranty Specialist**     | - View own service requests<br>- Create/manage device replacement requests<br>- Read-only access to the Microsoft 365 tenant outside of the Surface Support Portal | Ideal for specialists handling specific service requests and device management tasks. |
| **Global Admin**                         | - View service requests<br>- Create/manage device replacement requests<br>- Add/edit/delete ship-to addresses<br>- Create/manage users and their roles             | Provides broad administrative control over Surface devices, but use is discouraged for specific Surface management tasks to minimize security risks. |
| **Service Support Admin**                | - View service requests<br>- Create/manage device replacement requests                                                                                              | Focused role for managing service requests and device replacements without broader system access. |
| **Billing Admin**                        | - View service requests<br>- Create/manage device replacement requests<br>- Add/edit/delete ship-to addresses                                                     | Manages billing and shipping address aspects of device replacements and service requests. |
| **Global Reader**                        | - View all administrative settings and configurations across Microsoft Entra<br>- Read-only access to Microsoft 365 tenant and associated services             | Perfect for audit, compliance, and oversight roles requiring view-only access to configurations and settings.|

1. *On Surface Management Portal only, the Microsoft Hardware Warranty Administrator role also requires assigning the **Global Reader** role.*

> [!IMPORTANT]
> Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Admin is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

Implementing one or more of these roles ensures your team is equipped with the necessary permissions to manage Surface devices efficiently and securely. To learn more, see: 

- [Add an admin](/microsoft-365/admin/add-users/assign-admin-roles#steps-add-an-admin)
- [Surface portals overview](surface-portals.md)
- [Surface Management Portal](surface-management-portal.md)
- [Surface Support Portal overview](surface-support-portal.md)
