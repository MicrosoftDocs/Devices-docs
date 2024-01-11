---
title: Surface Diagnostic Toolkit for Business
description: This topic explains how to deploy and use the Surface Diagnostic Toolkit for Business, which enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 10/25/2021
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 10
- Windows 11
---

# Surface Diagnostic Toolkit for Business

If your Surface isn’t working correctly, the Microsoft Surface Diagnostic Toolkit (SDT) for Business can help you or your administrator find and solve problems.  SDT for Business lets you quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices — across your network.

> [!NOTE]
> Surface Diagnostic Toolkit for Business is built for commercial devices. If your device is a personal device and not managed by your work or school run the [Surface Diagnostic Toolkit](https://support.microsoft.com/help/4037239/surface-fix-common-surface-problems-using-surface-diagnostic-toolkit) instead.

Specifically, SDT for Business enables you to:

- [Customize the package.](#preparing-the-sdt-package-for-distribution)
- [Run the app using commands.](surface-diagnostic-toolkit-command-line.md)
- [Run multiple hardware tests to troubleshoot issues.](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [Generate logs for analyzing issues.](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [Obtain a detailed report comparing device vs. optimal configuration.](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)

## Primary scenarios and download resources

To run Surface Diagnostic Toolkit for Business, download the components listed in the following table.

Mode | Primary scenarios | Download | Learn more
--- | --- | --- | ---
Desktop mode | Assist users in running SDT on their Surface devices to troubleshoot issues.<br>Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze. | SDT distributable MSI package:<br>Microsoft Surface Diagnostic Toolkit for Business Installer<br>[Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) | [Use Surface Diagnostic Toolkit in desktop mode](surface-diagnostic-toolkit-desktop-mode.md)
Command line | Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager. It includes the following commands:<br>`-DataCollector` collects all log files<br>`-bpa` runs health diagnostics using Best Practice Analyzer.<br>`-windowsupdate` checks Windows Update for missing firmware or driver updates.<br>`-warranty` checks warranty information. <br><br>| SDT console app:<br>Microsoft Surface Diagnostics App Console<br>[Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) | [Run command-line app console with Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-command-line.md)

## Supported devices

SDT for Business is supported on Surface 3 and later devices (except for devices configured in S mode):

- Surface Book - all generations
- Surface Laptop Studio - all generations
- Surface Go - all generations
- Surface Laptop - all generations
- Surface Laptop Go - all generations
- Surface Pro 3 and later
- Surface Pro X - all generations
- Surface Studio - all generations
- Surface 3 LTE
- Surface 3

## Installing Surface Diagnostic Toolkit for Business

To create an SDT package that you can distribute to users in your organization:

1. Sign in to your Surface device using the Administrator account.

2. Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703).

    - For Intel/AMD devices, download: **Surface_Diagnostic_Toolkit_for_Business_v2.193.139.0.msi**.
    - For ARM devices, download: **Surface_Diagnostic_Toolkit_for_Business_v2.193.139.0_x86.msi**.

3. Copy the .msi file to a preferred location on your Surface device, such as Desktop.The SDT setup wizard appears, as shown in Figure 1. Click **Next**.

    >[!NOTE]
    >If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.

    ![Screenshot that shows the start of the Surface Diagnostic Toolkit setup wizard.](images/sdt-1.png)<br/>
    *Figure 1. Surface Diagnostic Toolkit setup wizard*

4. When the SDT setup wizard appears, click **Next**, and accept the End User License Agreement (EULA).

5. On the Install Options screen, change the default install location if desired.

6. Under Setup Type, select **Advanced**.

    >[!NOTE]
    >The standard option allows users to run the diagnostic tool directly on their Surface device, provided they are signed into their device using an Administrator account.

    ![Screenshot that shows selection of Install Options: Advanced.](images/sdt-install.png)

7. Click **Next** and then click **Install**.

## Installing using the command line

If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode. SDT contains the following install option flags:

- `SENDTELEMETRY` sends telemetry data to Microsoft. The flag accepts `0` for disabled or `1` for enabled. The default value is `1` to send telemetry.
- `ADMINMODE` configures the tool to be installed in admin mode. The flag accepts `0` for client mode or `1` for IT Administrator mode. The default value is `0`.

### To install SDT from the command line

1. Open a command prompt and enter:

    ```console
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```

    **Example:**

    ```console
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## Locating SDT on your Surface device

Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.

In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in Figure 2.

:::image type="content" alt-text="Screenshot that shows list of  installed files in File Explorer." source="images/sdt-2.png":::<br/>
*Figure 2. Files installed by SDT*

## Preparing the SDT package for distribution

Creating a custom package allows you to target the tool to specific known issues.

1. Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.

2. When the tool opens, click **Create Custom Package**, as shown in Figure 3.

    ![Create custom package option.](images/sdt-3.png)<br/>
    *Figure 3. Create custom package*

### Language and telemetry settings

  When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft. By default, SDT sends telemetry to Microsoft to improve the application per the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement). If you wish to decline, clear the check box when creating a custom package, as shown below. Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.

>[!NOTE]
>This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.

![Select language and telemetry settings.](images/sdt-4.png)<br/>
*Figure 4. Select language and telemetry settings*

### Windows Update page

Select the option appropriate for your organization. Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in Figure 5. If using local Windows Update packages or WSUS, enter the path as appropriate.

![Select Windows Update option.](images/sdt-5.png)<br/>
*Figure 5. Windows Update option*

### Software repair page

This allows you to select or remove the option to run software repair updates.

![Select software repair option.](images/sdt-6.png)<br/>
*Figure 6. Software repair option*

### Collecting logs and saving package page

You can select to run a wide range of logs across applications, drivers, hardware, and the operating system. Click the appropriate area and select from the menu of available logs. You can then save the package to a software distribution point or equivalent location that users can access.

![Select log options.](images/sdt-7.png)<br/>
*Figure 7. Log option and save package*

## Next steps

- [Use Surface Diagnostic Toolkit for Business in desktop mode](surface-diagnostic-toolkit-desktop-mode.md)
- [Run command-line app console with Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-command-line.md)

## Changes and updates

### Version 2.193.139.0

This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Surface Pro 9
- Surface Laptop 5
- Surface Studio 2+

### Version 2.168.139.0

This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Surface Pro 8
- Surface Laptop Studio
- Surface Go 3

### Version 2.131.139.0

This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Surface Pro 7+
- Seamless support experience on Surface Pro X
- Security improvements
- Inclusive user experience improvements

### Version 2.124.139.0

This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Seamless integrated support
- Save all test results
- Check if the image is custom created
- Include warnings from device manager
- Dock firmware version
- Flag drives as potential failures in storage test
- Remove store link

### Version 2.121.139

*Release date: July 31, 2020*<br>
This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Seamless support experience
- Bug fixes

### Version 2.94.139.0

*Release date: May 11, 2020*<br>
This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Ability to skip Windows Update to perform hardware check
- Ability to receive notifications about the latest version update
- Surface Go 2
- Surface Book 3
- Show progress indicator

### Version 2.43.139.0

*Release date: October 21, 2019*<br>
This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Surface Pro 7
- Surface Laptop 3

### Version 2.42.139.0

*Release date: September 24, 2019*<br>
This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Ability to download hardware reports
- Ability to contact Microsoft Support directly from the tool

### Version 2.41.139.0

*Release date: June 24, 2019*<br>
This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Driver version information included in logs and reports
- Ability to provide feedback about the app

### Version 2.36.139.0

*Release date: April 26, 2019*<br>
This version of Surface Diagnostic Toolkit for Business adds support for the following:

- Advanced Setup option to unlock admin capabilities through the installer UI without requiring command line configuration
- Accessibility improvements
- Surface brightness control settings included in logs
- External monitor compatibility support link in report generator
