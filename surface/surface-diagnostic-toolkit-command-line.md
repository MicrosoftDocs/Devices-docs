---
title: Run command-line app console with Surface Diagnostic Toolkit for Business
description: How to run Surface Diagnostic Toolkit in a command console
ms.prod: surface


author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.reviewer: hachidan
manager: frankbu
ms.localizationpriority: medium
ms.
appliesto:
- Windows 10
- Windows 11
---

# Run command-line app console with Surface Diagnostic Toolkit for Business

Running the Surface Diagnostic Toolkit (SDT) at a command prompt requires downloading the SDT app console. After it's installed, you can run SDT at a command prompt via the Windows command console (cmd.exe) or using Windows PowerShell, including PowerShell Integrated Scripting Environment (ISE), which provides support for autocompletion of commands, copy/paste, and other features.  For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>To run SDT using commands, you must be signed in to the Administrator account or signed in to an account that is a member of the Administrator group on your Surface device.

## Running SDT app console

1. Download and install SDT app console from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703).

- For Intel/AMD devices, download: **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0.exe**
- For ARM devices, download: **Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0_x86.exe**

2. Use the Windows command prompt (cmd.exe) or Windows PowerShell to:

- Collect all log files
- Run health diagnostics using Best Practice Analyzer
- Check update for missing firmware or driver updates

>[!NOTE]
>In this release, the SDT app console supports single commands only. Running multiple command line options requires running the console exe separately for each command.

By default, output files are saved in the same location as the console app. Refer to the following table for a complete list of commands.

Command | Notes
--- | ---
-DataCollector "output file" | Collects system details into a zip file. "output file" is the file path to create system details zip file.<br><br>**Example**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "output file" | Checks several settings and health indicators in the device. “output file" is the file path to create the HTML report.<br><br>**Example**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Checks Windows Update online servers for missing firmware and/or driver updates.<br><br>**Example**:<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-warranty "output file" | Checks warranty information on the device (valid or invalid). The optional “output file” is the file path to create the xml file. <br><br>**Example**: <br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty “warranty.xml”

>[!NOTE]
>To run the SDT app console remotely on target devices, you can use a configuration management tool such as Microsoft Endpoint Configuration Manager. Alternatively, you can create a .zip file containing the console app and appropriate console commands and deploy per your organization’s software distribution processes.

## Running Best Practice Analyzer

You can run BPA tests across key components such as BitLocker, Secure Boot, and Trusted Platform Module (TPM) and then output the results to a shareable file. The tool generates a series of tables with color-coded headings and condition descriptors along with guidance about how to approach resolving the issue.

- Green indicates the component is running in an optimal condition (optimal).
- Orange indicates the component is not running in an optimal condition (not optimal).
- Red indicates the component is in an abnormal state.

### Sample BPA results output

<table>
<tr><th colspan="2">BitLocker</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks if BitLocker is enabled on the system drive.</td></tr>
<tr><td><strong>Value:</strong></td><td>Protection On</td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>It is highly recommended to enable BitLocker to protect your data.</td></tr>
</table>

<table>
<tr><th colspan="2">Secure Boot</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks if Secure Boot is enabled.</td></tr>
<tr><td><strong>Value:</strong></td><td>True</td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>It is highly recommended to enable Secure Boot to protect your PC.</td></tr>
</table>

<table>
<tr><th colspan="2">Trusted Platform Module</th></tr>
<tr><td><strong>Description:</strong></td><td>Ensures that the TPM is functional.</td></tr>
<tr><td><strong>Value:</strong></td><td>True</td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>Without a functional TPM, security-based functions such as BitLocker may not work properly.</td></tr>
</table>

<table>
<tr><th colspan="2">Connected Standby</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks if Connected Standby is enabled.</td></tr>
<tr><td><strong>Value:</strong></td><td>True</td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>Connected Standby allows a Surface device to receive updates and notifications while not being used. For best experience, Connected Standby should be enabled.</td></tr>
</table>

<table>
<tr><th colspan="2">Bluetooth</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks if Bluetooth is enabled.</td></tr>
<tr><td><strong>Value:</strong></td><td>Enabled</td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2">Debug Mode</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks if the operating system is in Debug mode.</td></tr>
<tr><td><strong>Value:</strong></td><td>Normal</td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>The debug boot option enables or disables kernel debugging of the Windows operating system. Enabling this option can cause system instability and can prevent DRM (digital rights managemend) protected media from playing.</td></tr>
</table>

<table>
<tr><th colspan="2">Test Signing</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks if Test Signing is enabled.</td></tr>
<tr><td><strong>Value:</strong></td><td>Normal</td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>Test Signing is a Windows startup setting that should only be used to test pre-release drivers.</td></tr>
</table>

<table>
<tr><th colspan="2">Active Power Plan</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks that the correct power plan is active.</td></tr>
<tr><td><strong>Value:</strong></td><td>Balanced</td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>It is highly recommended to use the "Balanced" power plan to maximize productivity and battery life.</td></tr>
</table>

<table>
<tr><th colspan="2">Windows Update</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks if the device is up to date with Windows updates.</td></tr>
<tr><td><strong>Value:</strong></td><td>Microsoft Silverlight (KB4023307), Definition Update for Windows Defender Antivirus - KB2267602 (Definition 1.279.1433.0)</td></tr>
<tr><td><strong>Condition:</strong></td><td>Not Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>Updating to the latest windows makes sure you are on the latest firmware and drivers. It is recommended to always keep your device up to date</td></tr>
</table>

<table>
<tr><th colspan="2">Free Hard Drive Space</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks for low free hard drive space.</td></tr>
<tr><td><strong>Value:</strong></td><td>66%</td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>For best performance, your hard drive should have at least 10% of its capacity as free space.</td></tr>
</table>

<table>
<tr><th colspan="2">Non-Functioning Devices</th></tr>
<tr><td><strong>Description:</strong></td><td>List of non-functioning devices in Device Manager.</td></tr>
<tr><td><strong>Value:</strong></td><td></td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>Non-functioning devices in Device Manager may cause unpredictable problems with Surface devices such as, but not limited to, no power savings for the respective hardware component.</td></tr>
</table>

<table>
<tr><th colspan="2">External Monitor</th></tr>
<tr><td><strong>Description:</strong></td><td>Checks for an external monitor that may have compatibility issues.</td></tr>
<tr><td><strong>Value:</strong></td><td></td></tr>
<tr><td><strong>Condition:</strong></td><td>Optimal</td></tr>
<tr><td><strong>Guidance:</strong></td><td>Check with the original equipment manufacturer for compatibility with your Surface device.</td></tr>
</table>
