---
title: Microsoft Surface Dock 1 Firmware Update
description: This article explains how to use Microsoft Surface Dock Firmware Update to install and manage firmware on the original Surface Dock 1. When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.
ms.localizationpriority: medium
ms.prod: surface
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.reviewer: scottmca
manager: frankbu
ms.date: 10/25/2021
appliesto:
- Windows 10
- Windows 11
---
# Surface Dock 1 Firmware Update

This article explains how to use Microsoft Surface Dock 1 Firmware Update to install and manage firmware on the original Surface Dock 1. When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.

> [!NOTE]
> This article does not apply to [Surface Dock 2](surface-dock-whats-new.md), which receives updates automatically via Windows Update or by using Microsoft Endpoint Configuration Manager or other MSI deployment tools.

This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT. The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.

> [!IMPORTANT]
> This article contains technical instructions for IT administrators. If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site. The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.

## Supported devices

Surface Dock 1 Firmware Update is supported on the following devices:

- Surface Pro 3 and later
- Surface Pro X (all generations)
- Surface 3
- Surface Book (all generations)
- Surface Laptop Studio
- Surface Studio (all generations)
- Surface Laptop (all generations)
- Surface Laptop Go (all generations)
- Surface Go (all generations)

### Minimum OS requirement

- Windows 10, version 1803 or later

## Install Surface Dock 1 Firmware Update

This section describes how to manually install the firmware update on Surface Dock 1.

> [!TIP]
> Microsoft periodically releases new versions of Surface Dock 1 Firmware Update. The MSI file is not self-updating. If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.

1. Go to [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) and download and install the .msi file named **Surface_Dock_FwUpdate..**, followed by the appropriate version. If you're running Surface Pro X, download the **.arm64** build. For all other devices, use the **.amd64** build.  

    - The update requires a Surface device running Windows 10, version 1803 or later.
    - Installing the MSI file might prompt you to restart Surface. However, restarting is not required to perform the update.

> [!NOTE]
> All current software, firmware, and drivers for the Surface Dock 2 can be found [here](https://www.microsoft.com/en-us/download/details.aspx?id=101317)

2. Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect. The Surface Dock 1 Firmware Update will update the dock silently in background. The process can take a few minutes to complete and will continue even if interrupted.

## Monitor the Surface Dock 1 Firmware Update

This section is optional and provides an overview of how to monitor installation of the firmware update.

To monitor the update:

1. Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.

2. Type the following command at an elevated command prompt:

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```

3. Install the update as described in the [next section](#install-surface-dock-1-firmware-update) of this article.

4. Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.

   If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**. Additionally, the version reported in the Windows Registry will not be current.

5. When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool. See the [Versions reference](#versions-reference) section in this article for details. For example:

    - Component10CurrentFwVersion 0x04ac3970 (78395760)
    - Component20CurrentFwVersion 0x04915a70 (76634736)

>[!TIP]
>If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.

Also see the following sections in this article:

- [How to verify completion of firmware update](#how-to-verify-completion-of-the-firmware-update)
  - [Event logging](#event-logging)
  - [Troubleshooting tips](#troubleshooting-tips)
  - [Versions reference](#versions-reference)

## Network deployment

You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock 1 Firmware Update to multiple devices across your network. When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:

- **Msiexec.exe /i \<path to msi file\> /quiet /norestart**

For example:

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> A log file is not created by default. In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"

For more information, refer to [Command line options](/windows/win32/msi/command-line-options) documentation.

> [!IMPORTANT]
> If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.

## Intune deployment

You can use Intune to distribute Surface Dock 1 Firmware Update to your devices. First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](/intune/apps/apps-win32-app-management).

Use the following command:

- **msiexec /i \<path to msi file\> /quiet /q**

## How to verify completion of the firmware update

Surface dock firmware consists of two components:

- **Component10:** Micro controller unit (MCU) firmware
- **Component20:** Display port (DP) firmware.

Successful completion of Surface Dock 1 Firmware Update results in new registry key values for these firmware components.

### To verify updates

1. Open Regedit and navigate to the following registry path:

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.

   ![Surface Dock 1 Firmware Update installation process.](images/regeditDock.png)

3. Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document. If the values match, the firmware was updated successfully.

4. If unable to verify, review Event logging and Troubleshooting tips in the next section.

## Event logging

### Table 1. Log files for Surface Dock 1 Firmware Update

| Log                              | Location                               | Notes                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Dock 1 Firmware Update log | Path needs to be specified (see note) | Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.                                                                                                  |
| Windows Device Install log       | %windir%\inf\setupapi.dev.log           | For more information about using Device Install Log, refer to [SetupAPI Logging](/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation. |

### Table 2. Event log IDs for Surface Dock 1 Firmware Update

Events are logged in the Application Event Log.  Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.

| Event ID | Event type                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | Dock firmware update has started.                                    |
| 2002     | Dock firmware update skipped because dock is known to be up to date. |
| 2003     | Dock firmware update failed to get firmware version.                 |
| 2004     | Querying the firmware version.                                       |
| 2005     | Dock firmware failed to start update.                                |
| 2006     | Failed to send offer/payload pairs.                                  |
| 2007     | Firmware update finished.                                            |
| 2008     | BEGIN dock telemetry.                                                |
| 2011     | END dock telemetry.                                                  |

## Troubleshooting tips

- Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.
- Disconnect all peripherals except for the Surface Dock.
- Uninstall any current Surface Dock 1 Firmware Update and then install the latest version.
- Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock. Wait until the LED stops blinking before you unplug Surface Dock from power.
- Connect the Surface Dock to a different device to see if it is able to update the dock.

## Versions reference

>[!NOTE]
>The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.

### Version 1.53.139.0

#### Release Date: August 4, 2020

This version of Surface Dock 1 Firmware Update includes bug fixes and support for:

- Updating Surface Dock 1 using Surface Pro X.

#### Registry key values

The registry values that indicate the status of firmware updates are unchanged from the previous version of this tool:

- Component10CurrentFwVersion updated to **4ac3970**.
- Component20CurrentFwVersion updated to **4a1d570**.

### Version 1.42.139

#### Release Date: September 18 2019

This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.

#### Updated registry key values

- Component10CurrentFwVersion updated to **4ac3970**.
- Component20CurrentFwVersion updated to **4a1d570**.

It adds support for Surface Pro 7 and Surface Laptop 3.

## Legacy versions

### Version 2.23.139.0

#### Release Date: 10 October 2018

This version of Surface Dock Updater adds support for the following:

- Add support for Surface Pro 6
- Add support for Surface Laptop 2

### Version 2.22.139.0

#### Release Date: 26 July 2018

This version of Surface Dock Updater adds support for the following:

- Increase update reliability
- Add support for Surface Go

### Version 2.12.136.0

#### Release Date: 29 January 2018

This version of Surface Dock Updater adds support for the following:

- Update for Surface Dock Main Chipset Firmware

- Update for Surface Dock DisplayPort Firmware

- Improved display stability for external displays when used with Surface Book or Surface Book 2

Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:

- Update for Surface Book Base Firmware

- Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices

### Version 2.9.136.0

#### Release date: November 3, 2017

This version of Surface Dock Updater adds support for the following:

- Update for Surface Dock DisplayPort Firmware

- Resolves an issue with audio over passive display port adapters

### Version 2.1.15.0

#### Release date: June 19, 2017

This version of Surface Dock Updater adds support for the following:

- Surface Laptop

- Surface Pro

### Version 2.1.6.0

#### Release date: April 7, 2017

This version of Surface Dock Updater adds support for the following:

- Update for Surface Dock DisplayPort firmware

- Requires Windows 10

### Version 2.0.22.0

#### Release date: October 21, 2016

This version of Surface Dock Updater adds support for the following:

- Update for Surface Dock USB firmware

- Improved reliability of Ethernet, audio, and USB ports

### Version 1.0.8.0

#### Release date: April 26, 2016

This version of Surface Dock Updater adds support for the following:

- Update for Surface Dock Main Chipset firmware

- Update for Surface Dock DisplayPort firmware
