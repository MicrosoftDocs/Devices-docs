---
title: Collect Surface Hub log files
description: This page shows how admins can collect log files for use when troubleshooting Surface Hub. 
ms.reviewer: 
manager: laurawi
keywords: troubleshoot, log files, Event Viewer
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/29/2022
ms.localizationpriority: medium
appliesto:
- Surface Hub 
- Surface Hub 2S
---

# Collect Surface Hub log files

You can access log files directly from your Surface Hub or remotely via Teams Admin Center.

## Access logs from Surface Hub

1. Insert a USB flash drive into the Surface. 
2. Sign in to Surface Hub with Admin credentials and go to **Settings** > **Update & Security** > **Logs** > **Collect Logs**. This process saves the log files to the root of the USB drive, a process that can take up to 5 minutes.
  
    :::image type="content" source="images/hub-logs-fig1.png" alt-text="Access logs from Surface Hub":::

## Access logs remotely from Teams Admin Center

1. Sign in to [Teams Admin Center](https://admin.teams.microsoft.com/) and select **Teams devices** > **Surface Hubs**.
2. Locate your Surface Hub and select its **Display name**.

    :::image type="content" source="images/hub-logs-fig2.png" alt-text="Select your Surface Hub Display name":::

3. Press **Download device logs**.
    :::image type="content" source="images/hub-logs-fig3.png" alt-text="Press Download device logs":::

4. Press **Got it** to prepare the device logs for download.

    :::image type="content" source="images/hub-logs-fig4.png" alt-text="Prepare  device logs for download.":::

5. Select the **History** tab to view the status of the log collection process and download the logs when they're available.
6. When the logs are ready, press **Download**. This process saves the log files to the Downloads folder on your PC.

    :::image type="content" source="images/hub-logs-fig5.png" alt-text="Download Surface Hub logs from Teams Admin Center":::

## Learn more

- [What's new in Windows 10 Team 2020 updates](surface-hub-2020-update-whats-new.md)
- [Windows Event Viewer](/host-integration-server/core/windows-event-viewer1)