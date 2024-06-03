---
title: Run command-line app console with Surface Diagnostic Toolkit for Business
description: How to run Surface Diagnostic Toolkit in a command console.
ms.service: surface
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.reviewer: chauncel
manager: frankbu
ms.localizationpriority: medium
ms.date: 05/21/2024
appliesto:
- Windows 10
- Windows 11
---

# Run command-line app console with Surface Diagnostic Toolkit for Business

Running the Surface Diagnostic Toolkit (SDT) at a command prompt requires downloading the **Surface IT Toolkit** and saving a copy of the **Diagnostics App Console**. You can run SDT at a command prompt on the target Surface device via the Windows command console (cmd.exe) or Windows PowerShell. For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).

>[!NOTE]
>To run SDT using commands, you must be signed in to the Administrator account or signed in to an account that is a member of the Administrator group on your Surface device.

## Run SDT app console

1. Download the [Surface IT Toolkit](https://www.microsoft.com/download/details.aspx?id=46703) and install it on the PC you use to manage devices in your organization.
2. Open [Surface IT Toolkit](surface-it-toolkit.md). Select **Tool Library** > **Diagnostics App Console** > **Save a copy** and choose **ARM64** or **X64**.

    :::image type="content" source="images/diagnostics-app-console.png" alt-text="Screenshot of Diagnostics App Console download.":::

3. Use the Windows command prompt (cmd.exe) or Windows PowerShell to:

- Collect all log files
- Run health diagnostics using Best Practice Analyzer (BPA)
- Check for missing firmware or driver updates

>[!NOTE]
>In this release, the SDT app console supports single commands only. Running multiple command-line options requires running the console exe separately for each command.

By default, output files are saved in the same location as the console app. Refer to the following table for a complete list of commands.

Command | Notes
--- | ---
-DataCollector "output file" | Collects system details into a zip file. "output file" is the file path to create the system details zip file.<br><br>**Example**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "output file" | Checks several settings and health indicators in the device. "output file" is the file path to create the HTML report.<br><br>**Example**:<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | Checks Windows Update online servers for missing firmware or driver updates.<br><br>**Example**:<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-warranty "output file" | Checks warranty information on the device (valid or invalid). The optional "output file" is the file path to create the XML file.<br><br>**Example**:<br>Microsoft.Surface.Diagnostics.App.Console.exe –warranty "warranty.xml"

>[!NOTE]
>To run the SDT app console remotely on target devices, use a configuration management tool such as Microsoft Endpoint Configuration Manager. Alternatively, you can create a .zip file containing the console app and appropriate console commands and deploy per your organization’s software distribution processes.

## Run Best Practice Analyzer

You can run BPA tests across key components such as BitLocker, Secure Boot, and Trusted Platform Module (TPM) and then output the results to a shareable file. The tool generates a series of tables with color-coded headings and condition descriptors along with guidance about how to resolve the issue.

- Green indicates the component is running in an optimal condition (optimal).
- Orange indicates the component isn't running in an optimal condition (not optimal).
- Red indicates the component is in an abnormal state.

## Sample BPA results output

### BitLocker

- **Description**: Checks if BitLocker is enabled on the system drive.
- **Value**: Protection On
- **Condition**: Optimal
- **Guidance**: It's highly recommended to enable BitLocker to protect your data.

### Secure Boot

- **Description**: Checks if Secure Boot is enabled.
- **Value**: True
- **Condition**: Optimal
- **Guidance**: It's highly recommended to enable Secure Boot to protect your PC.

### Trusted Platform Module

- **Description**: Ensures that the TPM is functional.
- **Value**: True
- **Condition**: Optimal
- **Guidance**: Without a functional TPM, security-based functions such as BitLocker might not work properly.

### Connected Standby

- **Description**: Checks if Connected Standby is enabled.
- **Value**: True
- **Condition**: Optimal
- **Guidance**: Connected Standby allows a Surface device to receive updates and notifications while not being used. For the best experience, Connected Standby should be enabled.

### Bluetooth

- **Description**: Checks if Bluetooth is enabled.
- **Value**: Enabled
- **Condition**: Optimal
- **Guidance**: N/A

### Debug Mode

- **Description**: Checks if the operating system is in Debug mode.
- **Value**: Normal
- **Condition**: Optimal
- **Guidance**: The debug boot option enables or disables kernel debugging of the Windows operating system. Enabling this option can cause system instability and can prevent DRM (digital rights management) protected media from playing.

### Test Signing

- **Description**: Checks if Test Signing is enabled.
- **Value**: Normal
- **Condition**: Optimal
- **Guidance**: Test Signing is a Windows startup setting that should only be used to test prerelease drivers.

### Active Power Plan

- **Description**: Checks that the correct power plan is active.
- **Value**: Balanced
- **Condition**: Optimal
- **Guidance**: It's highly recommended to use the "Balanced" power plan to maximize productivity and battery life.

### Windows Update

- **Description**: Checks if the device is up to date with Windows updates.
- **Value**: Microsoft Silverlight (KB4023307), Definition Update for Windows Defender Antivirus - KB2267602 (Definition 1.279.1433.0)
- **Condition**: Not Optimal
- **Guidance**: Updating to the latest Windows ensures you are on the latest firmware and drivers. It's recommended to always keep your device up to date.

### Free Hard Drive Space

- **Description**: Checks for low free hard drive space.
- **Value**: 66%
- **Condition**: Optimal
- **Guidance**: For best performance, your hard drive should have at least 10% of its capacity as free space.

### Non-Functioning Devices

- **Description**: List of nonfunctioning devices in Device Manager.
- **Value**: [Not provided in the screenshot]
- **Condition**: Optimal
- **Guidance**: Nonfunctioning devices in Device Manager might cause unpredictable problems with Surface devices, such as, but not limited to, no power savings for the respective hardware component.

### External Monitor

- **Description**: Checks for an external monitor that might have compatibility issues.
- **Value**: N/A
- **Condition**: Optimal
- **Guidance**: Check with the original equipment manufacturer for compatibility with your Surface device.

### Version history

v2.218.139.0, released October 24, 2023. Included in [Surface IT Toolkit Library](surface-it-toolkit-library.md), April 25, 2024.
