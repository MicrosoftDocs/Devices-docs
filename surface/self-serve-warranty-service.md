---
title: Surface Self Serve Warranty and Service
description: Microsoft 365 Business customers may be eligible to use the beta Surface Self Serve Warranty and Service node in the Microsoft Admin Center to create and manage service orders. 
ms.prod: w10
ms.mktglfcycl: support
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/07/2021
ms.reviewer: louannh 
manager: laurawi
audience: itpro
---

# Surface Self Serve Warranty and Service

Microsoft 365 Business customers may be eligible to use the beta Surface Self Serve Warranty and Service node in the Microsoft Admin Center to create and manage service orders. This new feature allows Global Admins to designate permissions to individuals within their company responsible for supporting warranty and service claims including:

- Uploading serial numbers for the devices requiring service
- Adding multiple shipping addresses
- Creating a single service order for one or many devices and type covers
- Seeing real-time service order status
- Shipping to and receiving Advance Exchange shipments in bulk if devices are covered by an extended warranty or Advanced Exchange was included as part of the device purchase

Contact your Microsoft Customer Success Account Manager or Customer Success Manager to learn more about the experience and how to participate in the beta program.

## Role-based Permissions

The Surface Self-Serve Warranty and Service allows a Microsoft 365 Global Admin the ability to grant different permissions for creating and managing service orders by assigning roles to users.

When a Microsoft 365 tenant is onboarded to the beta, the following roles have additional permissions available to them

| Role                  | Permissions                                                                                                                         |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Global Admin          | View Repair Requests<br>Create/Manage Repair Requests<br>Add/Edit/Delete Ship to Address(es)<br>Create/Manage users and their roles |
| Service Support Admin | View Repair Requests<br>Create/Manage Repair Requests                                                                               |
| Billing Admin         | View Repair Requests<br>Create/Manage Repair Requests<br>Add/Edit/Delete Ship to address(es)                                        |

For more information about users and permissions, see [Microsoft Admin Center Overview](/microsoft-365/admin/admin-overview/about-the-admin-center)

## Create and manage a service order

1. Go to Microsoft 365 Admin Center  and sign in with your owner account (the account that has administrative permissions).
2. Click **Surface device repairs** > **Create repair request**.
3. Select **Submit 1 device** and click **Next.**
4. Confirm shipping address. To associate a new email address for notifications for this repair request, choose **Add new address** and enter the email as appropriate.

### Submit multiple devices

1. Create a .csv file in the following format:

- placeholder

### Submit single device

1. Input the device serial number and confirm it's correct.
2. Click **Add Device**.
3. Repeat to add up to 20 devices to the request.

### Finalize request

1. Review your order. If any information is incorrect, choose **Back** to correct any errors.
2. Accept the terms and conditions.
3. Your repair request is summarized. If correct, choose **Submit your request.**

## Frequently asked questions

### Why am I getting error code 400 “Generic client service error”, 401 “Unauthorized service error” or error 403 “Forbidden service error”?

There may be an issue with the Microsoft 365 account or the user does not have permissions to access the content. Reach out to your Microsoft 365 Global Admin for assistance.

### When I enter my shipping address and I get an error message that no shipping offers are available?

The Surface Self-Serve Warranty and Service Beta has limited availability at this time. Offers will only be available if the address is located in one of the following countries:

Austria, Bahrain, Belgium, Bulgaria, Croatia, Cyprus, Czech Republic, Denmark, Estonia, Finland, France, Germany, Greece, Hungary, Ireland, Italy, Kuwait, Latvia, Lithuania, Luxembourg, Malta, Netherlands, Oman, Poland, Portugal, Romania, Slovakia, Slovenia, South Africa, Spain, Sweden and the United Kingdom (excluding Northern Ireland).

### Where can I see orders that I have placed through the Microsoft 365 portal?

Go to [Microsoft 365 admin center - Service requests](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/support/devicerepairs) and sign in with your Microsoft 365 credentials.

Orders created through Microsoft Customer Support will not be visible in the Self-Serve Warranty and Service Management module.

### Why am I unable to add, edit or delete a shipping address?

The ability to add, edit, or delete a shipping address can only be done by your Microsoft 365 Global or Billing Admin. Reach out to them for assistance.  

### How can I Contact Microsoft Support for the Surface Self-Serve Warranty and Service beta?

You can contact support directly through the Surface Support module in the Microsoft Admin Center.

1. Sign in to the Microsoft Admin Center using your Microsoft 365 credentials.
2. Select **Support** > **Surface Device Repairs > Need help?** and describe the issue.
3. If the results don't help, select **Contact support**, and enter a description of your issue. Confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.
