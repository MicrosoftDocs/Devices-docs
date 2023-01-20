---
title: Surface Management Portal 
description: This article describes how the new Surface Management Portal provides a centralized solution to self-serve, manage and monitor Surface devices at scale. 
ms.prod: surface
ms.localizationpriority: medium
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 06/29/2022
ms.reviewer: hachinda
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---
# Surface Management Portal overview

Built into Microsoft Endpoint Manager, the new Surface Management Portal provides a centralized solution to self-serve, manage and monitor Surface devices at scale.

## Introduction

As a single environment for the end-to-end visibility of corporate or user-owned Surface devices, the Surface Management Portal lets you quickly see any issues that need prompt attention before they hit your help desk.

Get insights into device compliance, support activity, and warranty coverage. Quickly see the status of each device, which ones are still in warranty or expiring soon, and the status of active support requests with your hardware providers.

When your Surface devices are enrolled for cloud management and users log in for the first time, information from these Surface devices automatically flows into the Surface Management Portal, giving you a single pane of glass for Surface-specific device admin activities.

## Get started

Sign in to Microsoft Endpoint Manager, select **All services** > **Surface Management Portal**.

   :::image type="content" source="images/surface-management-portal/surface-management-portal-start.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-start.png" alt-text="Start Surface Management Portal":::

## Monitor Surface devices

Select **Monitor** to display insights for all your Surface devices, including:

- Devices out of compliance, which could mean users can’t access information requiring Azure AD login.
- Devices that aren’t registered.
- Devices with critically low storage available on disk, a leading indicator of potential user experience issues.
- Devices requiring updates.
- Devices without drive encryption enabled.
- Devices that are currently inactive.

Select **View report** to see details on each insights category, giving you diagnostic information that you can customize and export.

:::image type="content" source="images/surface-management-portal/surface-management-portal-view-report.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-view-report.png" alt-text="Get Surface device insights and view report":::

## Device warranty and coverage

If you manage hundreds or thousands of devices, having direct access to the warranty status of each device is especially useful, letting you quickly see the following information:

- Devices within the warranty period
- Devices expiring
- Devices out of warranty
- Devices eligible for optional coverage

## Support requests

The Surface Management Portal gives complete visibility into support activity along with the status of each request.

:::image type="content" source="images/surface-management-portal/surface-management-portal-support.png" lightbox="/surface/images/surface-management-portal/surface-management-portal-support.png" alt-text="Get information about support activity along with the status of each request.":::

### Create Support Requests

Newly added to the portal is the ability to create and submit new requests for one device or many.

1. Select **Create support request**.
2. Select the Product (Device) from the drop-down list.
3. Based on the Product selected, pick the device model.
4. Select the device or devices based on the serial number (SN).
5. Provide details and supporting information about the issue.
6. Provide your contact information and a contact preference.
7. Review and submit the request.  

   :::image type="content" source="images/surface-management-portal/smp-submit-support-request.png"  alt-text="Submit support request.":::

> [!TIP]
> Track request status using the current insights and detailed views.

## Try for free

Surface Management Portal is available to customers who use Microsoft Endpoint Manager and have enrolled Surface devices through Intune. If you’re new to Intune, set up your Intune tenant today by visiting [Quickstart: Try Microsoft Intune for free](/mem/intune/fundamentals/free-trial-sign-up).

## Learn more

- [What is Microsoft Surface Management Portal?](/mem/intune/fundamentals/surface-management-portal?)
- [Microsoft Mechanics](https://youtu.be/_MmutkqNudk)
- [Surface IT Pro Blog post: Surface Management Portal](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-management-portal/ba-p/1419017)
