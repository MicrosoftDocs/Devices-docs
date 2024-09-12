---
title: Surface Management Portal  
description: Manage, monitor, and maintain Surface devices efficiently with the Surface Management Portal in Microsoft Intune Admin Center. 
ms.service: surface  
ms.localizationpriority: medium  
author: coveminer  
ms.author: chauncel  
ms.topic: how-to  
ms.date: 09/06/2024  
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
- Automatically access comprehensive info from your Intune-enrolled Surface devices. When users sign in for the first time, information from these Surface devices automatically flows into the Surface Management Portal, providing a unified view for Surface-specific device admin activities.

## Access Surface Management Portal

### If you don't have an Intune subscription

1. To sign up for Intune, go to the [Intune product page](https://www.microsoft.com/security/business/endpoint-management/microsoft-intune) to learn more about the service.
2. Select **Start a free trial** to initiate the sign-up process, as described in [Try Microsoft Intune for free](/mem/intune/fundamentals/free-trial-sign-up).
3. Follow the prompts to create an account and choose a [subscription plan](https://www.microsoft.com/security/business/microsoft-intune-pricing) that fits your organization's needs.
4. Follow the setup wizard to configure your Intune environment. Add users, set up device policies, and configure security settings as needed.
5. You can manage a wide range of OEM (Original Equipment Manufacturer) devices with Intune but need to [enroll at least one Surface device](/mem/intune/user-help/enroll-windows-10-device) in order to access the Surface Management Portal.
6. Once you subscribe to Intune and [enroll](/mem/intune/user-help/enroll-windows-10-device) at least one Surface device, proceed to the next section.

### If you have an Intune subscription

- Sign in to [Microsoft Intune Admin Center](https://endpoint.microsoft.com), select **All services** > **Surface Management Portal**.

   :::image type="content" source="images/surface-management-portal/surface-management-portal-start.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-start.png" alt-text="Start Surface Management Portal":::

<a name='azure-ad-roles-for-surface-management-portal'></a>

## IT tasks in Surface Management Portal

Managing a fleet of Surface devices efficiently is crucial for IT admins. The Surface Management Portal offers a range of tools to monitor device health, manage warranties, and handle support requests. This section includes key tasks you can perform using the portal to ensure your Surface devices remain compliant, up-to-date, and fully functional.

### Monitor Surface devices

1. Select **Monitor** to display insights for all your Surface devices, including:

- Devices out of compliance, which could mean users can’t access information requiring Microsoft Entra sign-in.
- Devices that aren’t registered.
- Devices with critically low storage available on disk, a leading indicator of potential user experience issues.
- Devices requiring updates.
- Devices without drive encryption enabled.
- Devices that are currently inactive.

2. Select **View report** to see details on each insights category, giving you diagnostic information that you can customize and export.

    :::image type="content" source="images/surface-management-portal/surface-management-portal-view-report.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-view-report.png" alt-text="Get Surface device insights and view report":::

> [!TIP]
> The portal shows device information for your top four registered devices with all others listed under **Other**. Select **View report** to see all your devices.

### Device warranty and coverage

If you manage hundreds or thousands of devices, having direct access to the warranty status of each device is especially useful, letting you quickly see the following information:

- Devices within the warranty period
- Devices expiring
- Devices out of warranty
- Devices eligible for optional coverage

## Submit devices for repair

1. Select **Create service request** from the service orders screen.

2. **Choose the device or accessory for repair**:
   - In the "What do you want to replace or repair?" section, select whether the item is a **Serialized Device/Accessory** (e.g., Type covers, Dock) or a **Non-serialized Accessory** (e.g., Mouse, Power Supply).

3. **Add Service request details**:
   - Enter the required details about the device or accessory.
   - Choose the appropriate product or model from the drop-down menu.
   - If necessary, select multiple devices by choosing **+ Select devices**, then click **Done** after your selection.

4. **Describe the issue**:
   - Provide a detailed description of the issue you are experiencing with the device.
   - Attach any relevant files that might help diagnose or explain the issue.

5. **Provide contact information**:
   - Enter your contact details and specify your preferred method of communication for updates regarding the request.

6. **Review and submit the request**:
   - Carefully review all entered information, ensuring it is accurate and complete.
   - Once verified, click **Submit** to finalize the service request.


### Tracking your repair request

After submitting, you can track the status of your request under the **Service order** section. The status will update as the request progresses through different stages, such as device return, replacement in transit, and completed deliveries.

### Support requests

The Surface Management Portal gives complete visibility into support activity along with the status of each request.

:::image type="content" source="images/surface-management-portal/surface-management-portal-support.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-support.png" alt-text="Get information about support activity along with the status of each request.":::

#### Create Support Requests

You can create and submit new requests for one or more devices.

1. Select **New support request**.
2. Select the Product (Device) from the drop-down list and pick the device model.
3. Choose + **Select devices**, select devices needing support, and select **Done**.
4. Provide details and supporting information about the issue.
5. Provide your contact information and a contact preference.
6. Review and submit the request.  

   :::image type="content" source="images/surface-management-portal/smp-submit-support-request.png"  alt-text="Submit support request.":::

> [!TIP]
> Track request status using the current insights and detailed views.

### Extend functionality with the Surface API Management Service

The Surface API Management Service is an extension of the Surface Management Portal, providing IT admins with direct access to Microsoft coverage and entitlement information for their Surface devices through API endpoints. This service simplifies device and asset management by offering seamless integration, allowing admins or users to quickly retrieve critical warranty and device details. Access requires an active Surface Management Portal account and a customer validation check.

- To learn more, see [Introducing the Surface API Management Service](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-the-surface-api-management-service/ba-p/4107282)

### Microsoft Entra roles

The following admin roles apply to the Surface Management Portal:

| Role                                             | Permissions                                                                                                                                                 |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Microsoft Hardware Warranty Administrator<sup>1</sup> | - View all service requests<br>- Create/manage device replacement requests<br>- Add/edit/delete ship-to addresses<br>- Read-only access to the Microsoft 365 tenant outside of the Surface Support Portal |
| Microsoft Hardware Warranty Specialist<sup>1</sup>     | - View own service requests<br>- Create/manage device replacement requests<br>- Read-only access to the Microsoft 365 tenant outside of the Surface Support Portal   |
| Global Admin                                     | - View service requests<br>- Create/manage device replacement requests<br>- Add/edit/delete ship-to addresses<br>- Create/manage users and their roles             |
| Service Support Admin                            | - View service requests<br>- Create/manage device replacement requests                                                                                              |
| Billing Admin                                    | - View service requests<br>- Create/manage device replacement requests<br>- Add/edit/delete ship-to addresses                                                     |
| Global Reader                                    | - View all administrative settings and configurations across Microsoft Entra<br>- Read-only access to Microsoft 365 tenant and associated services                                                            |

1. *Requires **Global Reader** role for access*.

> [!IMPORTANT]
> Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. **Global Administrator** is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

## Try Surface Management Portal for free

Surface Management Portal is available to customers who use Microsoft Intune Admin Center and enroll at least one Surface device through Intune. If you’re new to Intune, set up your Intune tenant today by visiting [Try Microsoft Intune for free](/mem/intune/fundamentals/free-trial-sign-up).

## Learn more

- [(Re)Introducing Surface portals - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/re-introducing-the-surface-management-and-support-suite/ba-p/4109526)
- [Introducing the Surface API Management Service - Microsoft Community Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-the-surface-api-management-service/ba-p/4107282)
- [Surface portals overview](surface-portals.md)
- [Surface Support Portal](surface-support-portal.md)
- [Surface IT Toolkit](surface-it-toolkit.md)
