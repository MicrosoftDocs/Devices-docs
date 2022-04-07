---
title: Manage Windows updates on Surface Hub
description: Describes best practices for managing updates on Microsoft Surface Hub or Surface Hub 2S.
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: 
manager: laurawi
keywords: manage Windows updates, Surface Hub, Windows Server Update Services
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
---

# Manage Windows updates on Surface Hub

New releases of the Surface Hub operating system are published through Windows Update, just like releases of Windows 10. This page explains best practices for managing updates for Surface Hub devices. 

## Windows Update for Business

Windows Update for Business is a set of features designed to provide enterprises additional control over how and when Windows Update installs releases, while reducing device management costs. Using this method, Surface Hubs are directly connected to Microsoft’s Windows Update service.

- Receive updates directly from Microsoft's Windows Update service, with no additional infrastructure required. 
- Defer updates to provide additional time for testing and evaluation. 
- Deploy updates to select groups of devices. 
- Define maintenance windows for installing updates. 

> [!TIP]
> Use peer-to-peer content sharing to reduce bandwidth issues during updates. See [Optimize update delivery for Windows 10 updates](https://technet.microsoft.com/itpro/windows/manage/waas-optimize-windows-10-updates) for details.

> [!NOTE]
> Surface Hub does not currently support rolling back updates.


## Surface Hub servicing model

Surface Hub uses the Windows 10 servicing model, referred to as [Windows as a Service (WaaS)](https://docs.microsoft.com/windows/deployment/update/waas-overview). Traditionally, new features were added only in new versions of Windows that were released every few years. Each new version required lengthy and expensive processes to deploy in an organization. As a result, end users and organizations don't frequently enjoy the benefits of new innovation. The goal of Windows as a Service is to continually provide new capabilities while maintaining a high level of quality.

Microsoft publishes two types of Surface Hub releases broadly on an ongoing basis:
- **Feature updates** - Updates that install the latest new features, experiences, and capabilities. Microsoft expects to publish two new feature updates per year.
- **Quality updates** - Updates that focus on the installation of security fixes, drivers, and other servicing updates. Microsoft expects to publish one cumulative quality update per month.

In order to improve release quality and simplify deployments, all new releases that Microsoft publishes for Windows 10, including Surface Hub, will be cumulative. This means new feature updates and quality updates will contain the payloads of all previous releases (in an optimized form to reduce storage and networking requirements), and installing the release on a device will bring it completely up to date. Also, unlike earlier versions of Windows, you cannot install a subset of the contents of a Windows 10 quality update. For example, if a quality update contains fixes for three security vulnerabilities and one reliability issue, deploying the update will result in the installation of all four fixes.

The Surface Hub operating system receives updates on the [Semi-Annual Channel](https://docs.microsoft.com/windows/deployment/update/waas-overview#naming-changes). Like other editions of Windows 10, the servicing lifetime is finite. You must install new feature updates on machines running these branches in order to continue receiving quality updates.

For more information on Windows as a Service, see [Overview of Windows as a service](https://technet.microsoft.com/itpro/windows/manage/waas-overview).


## Use Windows Update for Business

Surface Hubs, like all Windows 10 devices, include **Windows Update for Business (WUfB)** to enable you to control how your devices are being updated. Windows Update for Business helps reduce device management costs, provide controls over update deployment, offer quicker access to security updates, as well as provide access to the latest innovations from Microsoft on an ongoing basis. For more information, see [Manage updates using Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

> [!IMPORTANT]
> Microsoft generally releases one mandatory Windows security update per month (released on the 2nd Tuesday and ofter referred to as a "B" release). Together with out-of-band security updates, these are the only updates made available to devices using WUfB. However, Surface Hub improvements are generally delivered through optional non-security updates on the 3rd Tuesday of each month ("C" release). As a result, customers using Windows Update for Business with their Surface Hubs will have wait until the following month's "B" release to see the latest improvements on these devices.

**To set up Windows Update for Business:**
1. [Group Surface Hub into deployment rings](#group-surface-hub-into-deployment-rings)
2. [Configure when Surface Hub receives updates](#configure-when-surface-hub-receives-updates).

> [!NOTE]
> You can use Microsoft Intune, Microsoft Endpoint Configuration Manager, or a supported third-party MDM provider to set up WUfB. [Walkthrough: use Microsoft Intune to configure Windows Update for Business.](https://docs.microsoft.com/windows/deployment/update/waas-wufb-intune)


### Group Surface Hub into deployment rings

Use deployment rings to control when updates roll out to your Surface Hubs, giving you time to validate them. For example, you can update a small pool of devices first to verify quality before a broader roll-out to your organization. Depending on who manages Surface Hub in your organization, consider incorporating Surface Hub into the deployment rings that you've built for your other Windows 10 devices. For more information about deployment rings, see [Build deployment rings for Windows 10 updates](https://technet.microsoft.com/itpro/windows/manage/waas-deployment-rings-windows-10-updates).

See the following table for examples of deployment rings.

| Deployment ring | Ring size | Servicing branch | Deferral for feature updates | Deferral for quality updates (security fixes, drivers, and other updates) | Validation step |
| --------- | --------- | --------- | --------- | --------- | --------- |
| Preview (e.g. non-critical or test devices) | Small | Windows Insider Preview | None.  | None.  | Manually test and evaluate new functionality. Pause updates if there are issues. |
| Release (e.g. devices used by select teams) | Medium | Semi-annual channel  | None. | None.  | Monitor device usage and user feedback. Pause updates if there are issues. |
| Broad deployment (e.g. most of the devices in your organization) | Large | Semi-annual channel |  120 days after release. | 7-14 days after release. | Monitor device usage and user feedback. Pause updates if there are issues. |
| Mission critical (e.g. devices in executive boardrooms) | Small | Semi-annual channel |  180 days after release (maximum deferral for feature updates). | 30 days after release (maximum deferral for quality updates). | Monitor device usage and user feedback. |


### Configure when Surface Hub receives updates

Once you've determined deployment rings for your Surface Hubs, configure update deferral policies for each ring:
- To defer feature updates, set an appropriate [Update/DeferFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) policy for each ring.
- To defer quality updates, set an appropriate [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) policy for each ring.

> [!NOTE]
> If you encounter issues during the update rollout, you can pause updates using [Update/PauseFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) and [Update/PauseQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates).

**If you use a proxy server or other method to block URLs**

Add the following Windows update trusted site URLs to the “allow list”:
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

Once the Windows 10 Team Anniversary Update is installed, you can remove these addresses to return your Surface Hub to its previous state.

## Maintenance window

To ensure the device is always available for use during business hours, Surface Hub performs its administrative functions during a specified maintenance window. During the maintenance window, the Surface Hub automatically installs updates through Windows Update and reboots the device 20 minutes before the end of the window.

Surface Hub follows these guidelines to apply updates:
- Install the update during the next maintenance window. If a meeting is scheduled to start during a maintenance window, or the Surface Hub sensors detect that the device is being used, the pending update will be postponed to the following maintenance window.
- If the next maintenance window is past the update’s prescribed grace period, the device will calculate the next available slot during business hours using the estimated install time from the update’s metadata. It will continue to postpone the update if a meeting is scheduled, or the Surface Hub sensors detect that the device is being used.
- If the next maintenance window is **not** past the update's grace period, the Surface Hub will continue to postpone the update.
- If a reboot is needed, the Surface Hub will automatically reboot during the next maintenance window.

> [!NOTE]
> Allow time for updates when you first setup your Surface Hub. For example, a backlog of virus definitions may be available, which should be immediately installed.

A default maintenance window is set for all new Surface Hubs:
-   **Start time:** 2:00 AM
-   **Duration:** 2 hours

**To manually change the maintenance window:**
1.  Open **Settings** on your Surface Hub.
2.  Navigate to **Update & security** > **Windows Update** > **Advanced options**.
3.  Under **Maintenance hours**, select **Change**.

To change the maintenance window using MDM, set the **MaintenanceHoursSimple** node in the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx). See [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md) for more details.


## More information

- [Blog post: Servicing, Flighting, and Managing updates for Surface Hub (With Intune, of course!)](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## Related topics

[Manage Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub administrator's guide](surface-hub-administrators-guide.md)

