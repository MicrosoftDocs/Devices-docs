---
title: Surface Asset Tag Tool
description: This topic explains how to use the Surface Asset Tag Tool.
ms.prod: surface
ms.localizationpriority: medium
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.reviewer: carlol
ms.date: 06/29/2021
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---

# Surface Asset Tag Tool

Surface Asset Tag is a command line interface (CLI) utility
that allows you to view, assign, and modify an assigned asset tag value for Surface devices.

## System requirements

- Surface Pro 3 or later and all newer Surface devices.

- UEFI firmware version 3.9.150.0 or later

## Using Surface Asset Tag

To run Surface Asset Tag:

1. On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download
    Center](https://www.microsoft.com/download/details.aspx?id=46703),
    extract the zip file, and save AssetTag.exe in desired folder (in
    this example, `C:\assets`).

    > [!NOTE]
    > For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.

2. Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool. (See examples in the "Asset Tag tool commands" section below.)
   
4. Restart Surface.

    > [!NOTE]
    > After setting the asset tag, a second reboot is required before it appears in WMI.

---

### Asset Tag tool commands

In the previous steps, we downloaded the Asset Tag tool and extracted it to `C:\assets\AssetTag.exe`. We will use that full file path in the following examples to interact with the Asset Tag Tool CLI. 

- _**Note:** If you extracted `AssetTag.exe` to a different folder, you will need to adjust the full file path accordingly._

To get the proposed asset tag, run **AssetTag -g**:

```console
C:\assets\AssetTag.exe -g
```

To clear the proposed asset tag, run **AssetTag -s**:

```console
C:\assets\AssetTag.exe -s
```

To set the proposed asset tag, run **AssetTag -s testassettag12**:

```console
C:\assets\AssetTag.exe -s testassettag12
```

If you're using PowerShell, the commands look a little different:

```powershell
# Retrieve the proposed asset tag
Start-Process -FilePath "C:\assets\AssetTag.exe" -ArgumentList "-g" -Wait

# Clear the proposed asset tag
Start-Process -FilePath "C:\assets\AssetTag.exe" -ArgumentList "-s" -Wait

# Set the proposed asset tag
Start-Process -FilePath "C:\assets\AssetTag.exe" -ArgumentList "-s", "testassettag12" -Wait
```

>[!TIP]
>The asset tag value must contain between 1 and 36 characters. Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).

---

## Managing Asset Tags

You can view the existing asset tag in the UEFI settings under Device
Information.
- **Windows 10:** Control Panel → Recovery → Advanced Startup → Restart now
- **Windows 11:** Settings → System → Recovery → Advanced Startup → Restart now

The figure below shows the results of running the Asset Tag Tool on
Surface Go.

![Results of running Surface Asset Tag tool on Surface Go.](images/assettag-fig1.png)

> **Figure 1.** Results of running Surface Asset Tag tool on Surface Go

---

## Alternate Methods

In the event you do not have access to the Asset Tag Tool CLI, or you prefer an alternative approach, the additional methods listed below may be a better fit for your use-case.

### Using WMI/CIM Queries

You can use WMI, or CIM, to query the existing asset tag on a device.

**PowerShell:**
```powershell
# Using 'Get-WmiObject' 
Get-WmiObject -query "Select SMBIOSAssetTag from Win32_SystemEnclosure"

# Using CIM Commands (newer)
Get-CimInstance -ClassName Win32_SystemEnclosure | Select-Object -ExpandProperty SMBIOSAssetTag
```

**CMD:**
```console
wmic SystemEnclosure get SMBIOSAssetTag
```

### Full Code Example

The following example displays a fully-functional (and tested!) PowerShell script that can be ran on any Windows-based device to return the Asset Tag.

> _**Note:** This script will work, and function identically, in both Windows PowerShell and PowerShell 7._

```powershell
# Define Behavior(s)
$ProgressPreference = 'SilentlyContinue'
$ErrorActionPreference = 'Stop'

# Initialize the script
Write-Host "Retrieving the Asset Tag for $env:COMPUTERNAME, please wait... " -NoNewline
$assetTag = Get-CimInstance -ClassName Win32_SystemEnclosure | Select-Object -ExpandProperty SMBIOSAssetTag
Write-Host "Done!" -ForegroundColor Green

# If the response is blank (an empty string), the Asset Tag has not yet been configured
if ([string]::IsNullOrEmpty($assetTag) -or $assetTag.ToLower() -eq "default string") { $assetTag = "Not configured." }

# Display the Results
Write-Host "Asset Tag: $($assetTag.Trim())"
```

Here's what running that script looks like on a computer where the `Asset Tag` has not been configured:
![WindowsTerminal-DisplayingScriptResults-AssetTagIsUndefined](https://i.imgur.com/DVeZ0Zi.png)
