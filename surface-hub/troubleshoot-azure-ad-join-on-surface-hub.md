---
title: Troubleshoot Microsoft Entra join issues on Surface Hub
description: This page explains recommended troubleshooting steps if you're unable to Microsoft Entra join a Surface Hub during the out of box experience.
ms.reviewer: 
manager: frankbu
keywords: Troubleshoot common problems, setup issues, azure ad join
ms.service: surface-hub
ms.sitesec: library
author: ryanbwold 
ms.author: rwold
ms.topic: troubleshooting
ms.date: 02/24/2023
ms.localizationpriority: medium
---

# Troubleshoot Microsoft Entra join on Surface Hub

If you can't join Surface Hub to Microsoft Entra ID during the first run Out of Box Experience (OOBE), follow the troubleshooting guidance on this page.

<a name='azure-ad-permissions'></a>

## Microsoft Entra permissions

A common reason a user cannot join a device to Microsoft Entra ID is related to Microsoft Entra permissions. To confirm which users can join devices to Microsoft Entra ID:

- Go to the [Microsoft Entra admin center](https://portal.azure.com/#view/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/%7E/Overview) and select **Devices > Device settings**. Ensure "Users may join devices to Microsoft Entra ID" is set to **All** or **Selected**. For Selected users, confirm the account used to join Microsoft Entra ID is included in the assigned group.

![Showing Azure device settings page where users can be scoped to join devices to Microsoft Entra ID](images/troubleshoot-azure-ad-join-1.png)

## Maximum number of devices

Errors can also occur if the user exceeds the maximum number of devices allowed to join to Microsoft Entra ID. If a user reaches this limit, they can't add more devices until one or more existing devices are removed. The default value is 50 devices and can be increased to 100 within [Microsoft Entra ID](/azure/active-directory/devices/device-management-azure-portal#configure-device-settings).

<a name='unable-to-reach-azure-ad'></a>

## Unable to reach Microsoft Entra ID

If error OOBEAADV10 is shown, the Surface Hub cannot reach the necessary Microsoft 365 endpoints. If encountered, follow the below troubleshooting steps in order.

![Image showing an error of "something went wrong" with error code OOBEAADV10](images/troubleshoot-azure-ad-join-2.png)

| **Step** | **Troubleshooting Step**                                                                                                                  | **Purpose**                                                                                                                                                  | **Additional Information**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| -------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1        | If your organization uses a proxy, ensure the proxy settings and required certificates are installed on the Surface Hub.          | Allows Surface Hub to reach necessary Microsoft endpoints to Microsoft Entra join the device.                                                                       | To configure proxy settings on a Surface Hub during OOBE, a [provisioning package](/surface-hub/provisioning-packages-for-surface-hub) needs to be created and [installed](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub). If a certificate is required, refer to the instructions included in [Create provisioning packages for Surface Hub](/surface-hub/provisioning-packages-for-surface-hub#add-a-certificate-to-your-package). |
| 2        | Connect Surface Hub to a less restrictive network, such as a different VLAN, guest network or mobile Wi-Fi hotspot.                       | Using a less restrictive network may resolve the connectivity issue.                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 3        | Mirror network port the Surface Hub is using to capture and log network traffic. Analyze logs to determine if something is being blocked. | Third-party network packet capture software can't be installed natively on the Surface Hub. Mirroring the network port allows for this data to be captured. | Visit [Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges) for a detailed list of Microsoft endpoints that should be reachable.                                                                                                                                                                                                                                                                                                                                                                                           |
