---
title: Troubleshoot Surface Hub not Updating
description: Information on how to troubleshoot a Surface Hub that isn't automatically installing Windows Updates.
ms.assetid: 8BB80FA3-D364-4A90-B72B-65F0F0FC1F0D
ms.reviewer: 
manager: peterdem
ms.prod: surface-hub
ms.sitesec: library
author: ryanbwold
ms.author: rwold
ms.topic: article
ms.date: 06/27/2023
ms.localizationpriority: medium
---

# Troubleshoot Surface Hub not Updating ##

If your Surface Hub isn't automatically installing Windows Updates, follow the troubleshooting steps on this page.
 
## Verify current Surface Hub build number ##
First, determine the OS build number the Surface Hub is currently running. You can do this in-person via **Settings > Surface Hub > About**.

:::image type="content" source="images/surface-hub-os-build.png" alt-text="Image showing where to find current Surface Hub OS build number.":::
 
If the Surface Hub is Microsoft Entra joined, you can verify the OS build number by navigating to the [Azure portal](https://portal.azure.com/), Select **Devices > All Devices** and locate the Surface Hub.
 
:::image type="content" source="images/intune-os-version.png" alt-text="Image showing how to find OS build number of a device in Azure.":::

Compare the OS build number the Surface Hub is running with the [Surface Hub update history](/surface-hub/surface-hub-update-history) page to see which updates are missing. The current Surface Hub OS version is [Windows 10 Team 2022 Update](/surface-hub/surface-hub-2022-update) (22H2 / 19045). More details on how to do this are covered in the [verify a Surface Hub is fully updated](https://www.youtube.com/watch?v=rxL5cUS_3TA) video.

## Network requirements and troubleshooting ##
If your organization uses a proxy or firewall, ensure the necessary [connection endpoints for Windows 10 Enterprise](/windows/privacy/manage-windows-21h2-endpoints) and [Windows Updates endpoints](/troubleshoot/windows-client/deployment/windows-update-issues-troubleshooting#device-cant-access-update-files) are accessible by the Surface Hub.

### Proxy server ###
If you have a proxy server configured and Windows updates either don't download or remain stuck at 1% progress, it can be caused by the following:
- SSL inspection
- Cache updates from Windows Update
- Block support for partial file download (HTTP range headers)

Windows update uses dynamically created temporary file names that differ for each computer that downloads updates. This eliminates any benefit that might be gained from caching. Windows update also uses the Background Intelligent Transfer Service (BITS) as a client, which can request partial files, an operation the proxy may not support.

To resolve this issue, ensure the proxy doesn't perform any of the above operations on Windows Update traffic. More requirements and information can be found in [Windows Update issues troubleshooting](/troubleshoot/windows-client/deployment/windows-update-issues-troubleshooting).

If you're using a Bluecoat proxy, you can find more details at [Microsoft Windows updates fail to install](https://knowledge.broadcom.com/external/article/166719/microsoft-windows-updates-fail-to-instal.html).

> **Third-party information disclaimer**
>
> Microsoft provides third-party contact information to help you find technical support. This contact information may change without notice. Microsoft does not guarantee the accuracy of this third-party contact information.

### Test with open network ###
For troubleshooting purposes you can test connecting the Surface Hub to an open network to see if the device is able to download Windows updates. This will help confirm if the internal network isn't meeting the necessary network requirements for Windows update. To test with an open network do the following:

- If a proxy is configured, unconfigure it on the Surface Hub. **Settings > Network & internet > Proxy**
- Disconnect the Surface Hub from the network and connect it to a mobile Wi-Fi hotspot. **Settings > Network & internet > Wi-Fi**
- Navigate to **Settings > Update & security** and check for updates. If updates are still not found reboot the device and try again.

### Mirror network port ###
Port mirroring is a technique used on a network switch or router to send a copy of network packets seen on the specified ports (source ports) to other specified ports (destination ports). After enabling port mirroring on the Surface Hub port, the packets can be monitored and analyzed by an administrator to determine if any Microsoft endpoints are unaccessible. 

## Windows Update for Business deferral policy ##
[Windows Update for Business](/surface-hub/manage-windows-updates-for-surface-hub#windows-update-for-business) is a feature that allows IT administrators to manage when Windows devices receive updates. Administrators can defer or pause updates, allowing time to validate them before installing them on all devices. Feature updates can be deferred up to 365 days and quality updates can be deferred up to 30 days. Deferring means the device won't receive the update until it has been released for at least the number of deferral days you specified (offer date = release date + deferral date).
 
If your Surface Hub isn't updating, confirm if a [Windows Update deferral policy](/surface-hub/manage-windows-updates-for-surface-hub#group-surface-hub-into-deployment-rings) is applied. The specific policies are:

- [Update/DeferFeatureUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#deferfeatureupdatesperiodindays)
- [Update/DeferQualityUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#deferqualityupdatesperiodindays)

## Surface Hub v1 devices not updating past Windows 10 Team version 1703 (15063) ##
In some environments, Surface Hub v1 devices fail to install updates past OS build number 15063. If you have a Surface Hub experiencing this, the device needs to be reimaged using the [Surface Hub Recovery Tool](/surface-hub/surface-hub-recovery-tool).

## Confirm WSUS isn't configured ##
The Surface Hub no longer supports [Windows Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus) (WSUS). If the Surface Hub is configured to use WSUS, Windows Updates won't be received. Confirm WSUS isn't configured on the device by going to **Settings > Update & security > Windows Updates > Advanced options > Configure Windows Server Update Service (WSUS) server**.
 
Ensure "Use WSUS server to check for updates" is **unchecked**.
 
:::image type="content" source="images/surface-hub-configure-wsus.png" alt-text="Image showing where to find Surface Hub WSUS configuration setting.":::

## Surface Hub not performing nightly maintenance ##
The Surface Hub automatically installs Windows Updates during the nightly [maintenance window](/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window). The default maintenance window is set to begin at 2:00 AM for two hours. If the Surface Hub is unable to perform maintenance, it can result in the device not installing Windows updates. Common reasons for this include:

- The device is unplugged or powered off
- Surface Hub is reserved for a 24 hour interval meeting
- Device is in use during the maintenance window

We recommend you refrain from using or reserving the Surface Hub during the scheduled maintenance period. You can adjust the maintenance window timeframe by opening **Settings > Update & security > Windows Update > Advanced options**. Selecting "Change" allows you to adjust the maintenance hours. A maintenance window of at least 2 hours should be reserved for update.

:::image type="content" source="images/surface-hub-maintenance-hours.png" alt-text="Image showing where to configure the Surface Hub Maintenance hours.":::

## Windows event logs ##
You can view the Windows Event logs on the Surface Hub to see if any errors are present.
 
On the Surface Hub navigate to **Settings > Update & security > Logs > Event Viewer > Open.** 

Windows Update event logs can be found under **Applications and Services Logs > Microsoft > Windows > WindowsUpdateClient > Operational.**
 
:::image type="content" source="images/surface-hub-windows-update-event-viewer.png" alt-text="Image showing the Windows Update Event Viewer files on the Surface Hub.":::

## Reimage Surface Hub ##
If the troubleshooting steps in this article don't resolve the Surface Hub updating issue, the local Windows Update cache on the device may be corrupt. The device needs to be reset to resolve this issue. Detailed instructions on resetting the device can be found in the articles for [Surface Hub v1](/surface-hub/device-reset-surface-hub) and [Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset).
