---
title: Use Microsoft Endpoint Configuration Manager to manage devices with SEMM 
description: Learn how to manage Microsoft Surface Enterprise Management Mode (SEMM) with Endpoint Configuration Manager.
ms.prod: surface
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.reviewer: dashap
manager: frankbu
ms.localizationpriority: medium
ms.date: 03/02/2023
appliesto:
- Windows 10
- Windows 11
---

# Use Microsoft Endpoint Configuration Manager to manage devices with SEMM

The Microsoft Surface Enterprise Management Mode (SEMM) feature of Surface UEFI devices lets administrators manage and help secure the configuration of Surface UEFI settings. For most organizations, this process is accomplished by creating Windows Installer (.msi) packages with the Microsoft Surface UEFI Configurator tool. These packages are then run or deployed to the client Surface devices to enroll the devices in SEMM and to update the Surface UEFI settings configuration.

For organizations with Microsoft Endpoint Configuration Manager, there's an alternative to using the Microsoft Surface UEFI Configurator .msi process to deploy and administer SEMM. Microsoft Surface UEFI Manager is a lightweight installer that makes required assemblies for SEMM management available on a device. When you install these assemblies with Microsoft Surface UEFI Manager on a managed client, you can manage SEMM via Configuration Manager with PowerShell scripts, deployed as applications. Doing so eliminates the need for the external Microsoft Surface UEFI Configurator tool.

> [!NOTE]
> Although the process described in this article may work with earlier versions of Endpoint Configuration Manager or with other third-party management solutions, management of SEMM with Microsoft Surface UEFI Manager and PowerShell is supported only with the Current Branch of Endpoint Configuration Manager.

## Prerequisites

Before you begin the process outlined in this article, familiarize yourself with the following technologies and tools:

* [Surface UEFI](manage-surface-uefi-settings.md)
* [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md)
* [PowerShell scripting](/powershell)
* [Deploy applications with Configuration Manager](/mem/configmgr/apps/deploy-use/deploy-applications)

> [!IMPORTANT]
> You will also need access to the certificate that you intend to use to secure SEMM. For details about the requirements for this certificate, see [Surface Enterprise Management Mode certificate requirements](surface-enterprise-management-mode.md#surface-enterprise-management-mode-certificate-requirements).
>
> It is very important that this certificate be kept in a safe location and properly backed up. If this certificate becomes lost or unusable, it is not possible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.

### Download Microsoft Surface UEFI Manager

Management of SEMM with Configuration Manager requires the installation of Microsoft Surface UEFI Manager on each client Surface device. You can download Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center.

#### Download SEMM scripts for Configuration Manager

After Microsoft Surface UEFI Manager is installed on the client Surface device, SEMM can be deployed and managed with PowerShell scripts. Get  samples of [SEMM management scripts](https://www.microsoft.com/download/details.aspx?id=46703) by downloading SEMM_PowerShell.zip from Surface Tools for IT.

## Deploy Microsoft Surface UEFI Manager

Deployment of Microsoft Surface UEFI Manager is a typical application deployment. The Microsoft Surface UEFI Manager installer file is a standard Windows Installer file that you can install with the [standard quiet option](https://msdn.microsoft.com/library/windows/desktop/aa367988).

The command to install Microsoft Surface UEFI Manager is as follows.

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

The command to uninstall Microsoft Surface UEFI Manager is as follows.

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

To create a new application and deploy it to a collection that contains your Surface devices, perform the following steps:

1. Open Configuration Manager Console from the **Start** screen or **Start** menu.
2. Select **Software Library** in the bottom left corner of the window.
3. Expand the **Application Management** node of the Software Library, and then select **Applications**.
4. Select the **Create Application** button under the **Home** tab at the top of the window. This starts the Create Application Wizard.
5. The Create Application Wizard presents a series of steps:

   * **General** – The **Automatically detect information about this application from installation files** option is selected by default. In the **Type** field, **Windows Installer (.msi file)** is also selected by default. Select **Browse** to navigate to and select **SurfaceUEFIManagerSetup.msi**, and then select **Next**.

      > [!NOTE]
      > The location of SurfaceUEFIManagerSetup.msi must be on a network share and located in a folder that contains no other files. A local file location cannot be used.

   * **Import Information** – The Create Application Wizard parses the .msi file and read the **Application Name** and **Product Code**. SurfaceUEFIManagerSetup.msi should be listed as the only file under the line **Content Files**, as shown in Figure 1. Select **Next** to proceed.

      ![Information from Surface UEFI Manager setup is automatically parsed.](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *Figure 1. Information from Microsoft Surface UEFI Manager setup is automatically parsed*

   * **General Information** – You can modify the name of the application and information about the publisher and version, or add comments on this page. The installation command for Microsoft Surface UEFI Manager is displayed in the Installation Program field. The default installation behavior of Install for system allows Microsoft Surface UEFI Manager to install the required assemblies for SEMM even if a user isn't logged on to the Surface device. Select **Next** to proceed.
   * **Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page. Select **Next** to confirm your selections and create the application.
   * **Progress** – Displays a progress bar and status as the application is imported and added to the Software Library.
   * **Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete. Select **Close** to finish the Create Application Wizard.

After the application is created in Configuration Manager, you can distribute it to your distribution points and deploy it to the collections including your Surface devices. This application won't install or enable SEMM on the Surface device. It only provides the assemblies required for SEMM to be enabled using the PowerShell script.

If you don't want to install the Microsoft Surface UEFI Manager assemblies on devices that won't be managed with SEMM, you can configure Microsoft Surface UEFI Manager as a dependency of the SEMM Configuration Manager scripts. This scenario is covered in the [Deploy SEMM Configuration Manager Scripts](#deploy-semm-configuration-manager-scripts) section later in this article.

## Create or modify the SEMM Configuration Manager scripts

After the required assemblies have been installed on the devices, the process of enrolling the devices in SEMM and configuring Surface UEFI is done with PowerShell scripts and deployed as a script application with Configuration Manager. These scripts can be modified to fit the needs of your organization and environment. For example, you can create multiple configurations for managed Surface devices in different departments or roles. You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.

There are two primary scripts you'll need in order to perform a SEMM deployment with Configuration Manager:

* **ConfigureSEMM.ps1** – Use this script to create configuration packages for your Surface devices with your desired Surface UEFI settings to apply the specified settings to a Surface device, to enroll the device in SEMM, and to set a registry key used to identify the enrollment of the device in SEMM.
* **ResetSEMM.ps1** – Use this script to reset SEMM on a Surface device, which unenrolls it from SEMM and removes the control over Surface UEFI settings.

The sample scripts include examples of how to set Surface UEFI settings and how to control permissions to those settings. These settings can be modified to secure Surface UEFI and set Surface UEFI settings according to the needs of your environment. The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.

> [!NOTE]
> The SEMM Configuration Manager scripts and the exported SEMM certificate file (.pfx) should be placed in the same folder with no other files before they are added to Configuration Manager.

### Manage USB ports on supported devices

See [Manage USB ports on Surface devices](manage-usb-ports-on-surface.md)

The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.

### Specify certificate and package names

The first region of the script that you need to modify is the portion that specifies and loads the SEMM certificate, and also indicates SurfaceUEFIManager version, and the names for the SEMM configuration package and SEMM reset package. The certificate name and SurfaceUEFIManager version are specified on lines 56 through 73 in the ConfigureSEMM.ps1 script.

  ```powershell
  56	$WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57	$packageRoot = "$WorkingDirPath\Config"
  58	$certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65	if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66	Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67	
  68	$privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69	$ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70	$resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71	
  72	# If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73	$password = "1234" 
  ```

Replace the **FabrikamSEMMSample.pfx** value for the **$certName** variable with the name of your SEMM Certificate file on line 58. The script creates a working directory (named Config) in the folder where your scripts are located, and then copies the certificate file to this working directory.

Owner package and reset package will also be created in the Config directory and hold the configuration for Surface UEFI settings and permissions generated by the script.

On line 73, replace the value of the **$password** variable, from **1234** to the password for your certificate file. If a password isn't required, delete the **1234** text.

> [!NOTE]
> The last two characters of the certificate thumbprint are required to enroll a device in SEMM. This script will display these digits to the user, which allows the user or technician to record these digits before the system reboots to enroll the device in SEMM. The script uses the following code, found on lines 150-155, to accomplish this.

```powershell
150	# Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151	# For convenience we get the thumbprint here and present to the user.
152	$pw = ConvertTo-SecureString $password -AsPlainText -Force
153	$certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154	$certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155	Write-Host "Thumbprint =" $certPrint.Thumbprint
```

Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr. To view the thumbprint with CertMgr, follow this process:

1. Right-click the .pfx file, and then select **Open**.
2. Expand the folder in the navigation pane.
3. Select **Certificates**.
4. Right-click your certificate in the main pane, and then select **Open**.
5. Select the **Details** tab.
6. **All** or **Properties Only** must be selected in the **Show** drop-down menu.
7. Select the field **Thumbprint**.

> [!NOTE]
> The SEMM certificate name and password must also be entered in this section of the ResetSEMM.ps1 script to enable Configuration Manager to remove SEMM from the device with the uninstall action.

### Configure permissions

The first region of the script where you'll specify the configuration for Surface UEFI is the **Configure Permissions** region. This region begins at line 210 in the sample script with the comment **# Configure Permissions** and continues to line 247. The following code fragment first sets permissions to all Surface UEFI settings so that they may be modified by SEMM only, then adds explicit permissions to allow the local user to modify the Surface UEFI password, TPM, and front and rear cameras.

```powershell
210	# Configure Permissions
211	foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217	# Here we define which "identities" will be allowed to modify which settings
218	#   PermissionSignerOwner = The primary SEMM enterprise owner identity
219	#   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220	#   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221	#     Additional user identities created so that the signer owner
222	#     can delegate permission control for some settings.
223	$ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224	$ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225	
226	# Make all permissions owner only by default
227	foreach ($setting IN $uefiV2.Settings.Values) {
228	$setting.ConfiguredPermissionFlags = $ownerOnly
229	}
230	
231 # Allow the local user to change their own password
232	$uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234	Write-Host ""
235	 
236	# Create a unique package name based on family and LSV.
237	# We will choose a name that can be parsed by later scripts.
238	$packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239	$fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240	
241	# Build and sign the Permission package then save it to a file.
242	$permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243	$permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244	$permissionPackageStream.CopyTo($permissionPackage)
245	$permissionPackage.Close()
246	}
247	}
```

Each **$uefiV2** variable identifies a Surface UEFI setting by setting name or ID, and then configures the permissions to one of the following values:

* **$ownerOnly** – Permission to modify this setting is granted only to SEMM.
* **$ownerAndLocalUser** – Permission to modify this setting is granted to a local user booting to Surface UEFI, as well as to SEMM.

You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.

### Configure settings

The second region of the script where you'll specify the configuration for Surface UEFI is the **Configure Settings** region of the ConfigureSEMM.ps1 script, which configures whether each setting is enabled or disabled. The sample script includes instructions to set all settings to their default values. The script then provides explicit instructions to disable IPv6 for PXE Boot and to leave the Surface UEFI Administrator password unchanged. You can find this region beginning with the **# Configure Settings** comment at line 291 through line 335 in the sample script. The region appears as follows.

```powershell
291	# Configure Settings
292	foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298	# In this demo, we will start by setting every setting to the default factory setting.
299	# You may want to start by doing this in your scripts
300	# so that every setting gets set to a known state.
301	foreach ($setting IN $uefiV2.Settings.Values) {
302	$setting.ConfiguredValue = $setting.DefaultValue
303	}
304	
305	$EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309	# here are examples of how to accomplish this.
310	# This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318	# If you want to leave the setting unmodified, set it to $null
319	# PowerShell has issues setting things to $null so ClearConfiguredValue()
320	# is supplied to do this explicitly.
321	# Here is an example of leaving the UEFI administrator password as-is,
322	# even after we initially set it to factory default above.
323	$uefiV2.SettingsById[501].ClearConfiguredValue()
324	
325	# Create a unique package name based on family and LSV.
326	# We will choose a name that can be parsed by later scripts.
327	$packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328	$fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329	
330	# Build and sign the Settings package then save it to a file.
331	$settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332	$settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333	$settingsPackageStream.CopyTo($settingsPackage)
334	$settingsPackage.Close()
335	}
```

Like the permissions set in the **Configure Permissions** section of the script, the configuration of each Surface UEFI setting is performed by defining the **$uefiV2** variable. For each line defining the **$uefiV2** variable, a Surface UEFI setting is identified by setting name or ID and the configured value is set to **Enabled** or **Disabled**.

If you don't want to alter the configuration of a Surface UEFI setting, for example to ensure that the Surface UEFI administrator password isn't cleared by the action of resetting all Surface UEFI settings to their default, you can use **ClearConfiguredValue()** to enforce that this setting won't be altered. In the sample script, this is used on line 323 to prevent the clearing of the Surface UEFI Administrator password, identified in the sample script by its setting ID, **501**.

You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.

### Settings registry key

To identify enrolled systems for Configuration Manager, the ConfigureSEMM.ps1 script writes registry keys that can be used to identify enrolled systems as having been installed with the SEMM configuration script. These keys can be found at the following location.

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

The following code fragment, found on lines 380-477, is used to write these registry keys.

```powershell
380	# For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381	$UTCDate = (Get-Date).ToUniversalTime().ToString()
382	$certIssuer = $certPrint.Issuer
383	$certSubject = $certPrint.Subject
384	
385	$SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386	New-RegKey $SurfaceRegKey
387	$LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388	$DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389	$OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390	$PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391	$SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392	$IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393	$certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394	$certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395	$certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396	
397	
398	If ($LSVRegValue -eq $null)
399	{
400	    New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401	}
402	Else
403	{
404	    Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405	}
406	
407	If ($DateTimeRegValue -eq $null)
408	{
409	    New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410	}
411	Else
412	{
413	    Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414	}
415	
416	If ($OwnershipSessionIdRegValue -eq $null)
417	{
418	    New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419	}
420	Else
421	{
422	    Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423	}
424	
425	If ($PermissionSessionIdRegValue -eq $null)
426	{
427	    New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428	}
429	Else
430	{
431	    Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432	}
433	
434	If ($SettingsSessionIdRegValue -eq $null)
435	{
436	    New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437	}
438	Else
439	{
440	    Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441	}
442	
443	If ($IsResetRegValue -eq $null)
444	{
445	    New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446	}
447	Else
448	{
449	    Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450	}
451	
452	If ($certUsedRegValue -eq $null)
453	{
454	    New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455	}
456	Else
457	{
458	    Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459	}
460	
461	If ($certIssuerRegValue -eq $null)
462	{
463	    New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464	}
465	Else
466	{
467	    Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468	}
469	
470	If ($certSubjectRegValue -eq $null)
471	{
472	    New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473	}
474	Else
475	{
476	    Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477	}
```

### Settings names and IDs

To configure Surface UEFI settings or permissions for Surface UEFI settings, you must refer to each setting by either its setting name or setting ID. With each new update for Surface UEFI, new settings may be added. Running ShowSettingsOptions.ps1 script (from SEMM_Powershell.zip in [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703))provides details of available settings. The computer where ShowSettingsOptions.ps1 is run must have Microsoft Surface UEFI Manager installed, but the script doesn't require a Surface device.

## Deploy SEMM Configuration Manager scripts

After your scripts are prepared to configure and enable SEMM on the client device, the next step is to add these scripts as an application in Configuration Manager. Before you open Configuration Manager, ensure that the following files are in a shared folder that doesn't include other files:

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* Your SEMM certificate (for example SEMMCertificate.pfx)

The SEMM Configuration Manager scripts are added to Configuration Manager as a script application. The command to install SEMM with ConfigureSEMM.ps1 is as follows.

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

The command to uninstall SEMM with ResetSEMM.ps1 is as follows.

`Powershell.exe -file ".\ResetSEMM.ps1"`

To add the SEMM Configuration Manager scripts to Configuration Manager as an application, use the following process:

1. Start the Create Application Wizard using Step 1 through Step 5 from the [Deploy Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) section earlier in this article.

2. Proceed through The Create Application Wizard as follows:

   - **General** – Select **Manually specify the application information**, and then select **Next**.

   - **General Information** – Enter a name for the application (for example SEMM) and any other information you want such as publisher, version, or comments on this page. Select **Next** to proceed.

   - **Application Catalog** – The fields on this page can be left with their default values. Select **Next**.

   - **Deployment Types** – Select **Add** to start the Create Deployment Type Wizard.

   - Proceed through the steps of the Create Deployment Type Wizard, as follows:

     * **General** – Select **Script Installer** from the **Type** drop-down menu. The **Manually specify the deployment type information** option will automatically be selected. Select **Next** to proceed.
     * **General Information** – Enter a name for the deployment type (for example SEMM Configuration Scripts), and then select **Next** to continue.
     * **Content** – Select **Browse** next to the **Content Location** field, and then select the folder where your SEMM Configuration Manager scripts are located. In the **Installation Program** field, type the [installation command](#deploy-semm-configuration-manager-scripts) found earlier in this article. In the **Uninstall Program** field, enter the [uninstallation command](#deploy-semm-configuration-manager-scripts) found earlier in this article (shown in Figure 2). Select **Next** to move to the next page.

     ![Set the SEMM Configuration Manager scripts as the install and uninstall commands.](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *Figure 2. Set the SEMM Configuration Manager scripts as the install and uninstall commands*

     * **Detection Method** – Select **Add Clause** to add the SEMM Configuration Manager script registry key detection rule. The **Detection Rule** window is displayed, as shown in Figure 3. Use the following settings:

       - Select **Registry** from the **Setting Type** drop-down menu.
       - Select **HKEY_LOCAL_MACHINE** from the **Hive** drop-down menu.
       - Enter **SOFTWARE\Microsoft\Surface\SEMM** in the **Key** field.
       - Enter **CertName** in the **Value** field.
       - Select **String** from the **Data Type** drop-down menu.
       - Select the **This registry setting must satisfy the following rule to indicate the presence of this application** button.
       - Enter the name of the certificate you entered in line 58 of the script in the **Value** field.
       - Select **OK** to close the **Detection Rule** window.

     ![Use a registry key to identify devices enrolled in SEMM.](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")

     *Figure 3. Use a registry key to identify devices enrolled in SEMM*

     * Select **Next** to proceed to the next page.

     * **User Experience** – Select **Install for system** from the **Installation Behavior** drop-down menu. If you want your users to record and enter the certificate thumbprint themselves, leave the logon requirement set to **Only when a user is logged on**. If you want your administrators to enter the thumbprint for users and the users don't need to see the thumbprint, select **Whether or not a user is logged on** from the **Logon Requirement** drop-down menu.

     * **Requirements** – The ConfigureSEMM.ps1 script automatically verifies that the device is a Surface device before attempting to enable SEMM. However, if you intend to deploy this script application to a collection with devices other than those to be managed with SEMM, you could add requirements here to ensure this application would run only on Surface devices or devices you intend to manage with SEMM. Select **Next** to continue.

     * **Dependencies** – Select **Add** to open the **Add Dependency** window.

       * Select **Add** to open the **Specify Required Application** window.

          - Enter a name for the SEMM dependencies in the **Dependency Group Name** field (for example, *SEMM Assemblies*).

          - Select **Microsoft Surface UEFI Manager** from the list of **Available Applications** and the MSI deployment type, and then select **OK** to close the **Specify Required Application** window.

         *   Keep the **Auto Install** check box selected if you want Microsoft Surface UEFI Manager installed automatically on devices when you attempt to enable SEMM with the Configuration Manager scripts. Select **OK** to close the **Add Dependency** window.

     * Select **Next** to proceed.

     * **Summary** – The information you've entered throughout the Create Deployment Type wizard is displayed on this page. Select **Next** to confirm your selections.

     * **Progress** – A progress bar and status as the deployment type is added for the SEMM script application is displayed on this page.

     * **Completion** – Confirmation of the deployment type creation is displayed when the process is complete. Select **Close** to finish the Create Deployment Type Wizard.

   - **Summary** – The information that you entered throughout the Create Application Wizard is displayed. Select **Next** to create the application.

   - **Progress** – A progress bar and status as the application is added to the Software Library is displayed on this page.

   - **Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete. Select **Close** to finish the Create Application Wizard.

After the script application is available in the Software Library of Configuration Manager, you can distribute and deploy SEMM using the scripts you prepared to devices or collections. If you've configured the Microsoft Surface UEFI Manager assemblies as a dependency that will be automatically installed, you can deploy SEMM in a single step. If you haven't configured the assemblies as a dependency, they must be installed on the devices you intend to manage before you enable SEMM.

When you deploy SEMM using this script application and with a configuration that is visible to the end user, the PowerShell script starts and the thumbprint for the certificate will be displayed by the PowerShell window. You can have your users record this thumbprint and enter it when prompted by Surface UEFI after the device reboots.

Alternatively, you can configure the application installation to reboot automatically and to install invisibly to the user. In this scenario, a technician is required to enter the thumbprint on each device as it reboots. Any technician with access to the certificate file can read the thumbprint by viewing the certificate with CertMgr. Instructions for viewing the thumbprint with CertMgr are in the [Create or modify the SEMM Configuration Manager scripts](#create-or-modify-the-semm-configuration-manager-scripts) section of this article.

Removal of SEMM from a device deployed with Configuration Manager using these scripts is as easy as uninstalling the application with Configuration Manager. This action starts the ResetSEMM.ps1 script and properly unenrolls the device with the same certificate file that was used during the deployment of SEMM.

> [!NOTE]
> Microsoft Surface recommends that you create reset packages only when you need to unenroll a device. These reset packages are typically valid for only one device, identified by its serial number. You can, however, create a universal reset package that would work for any device enrolled in SEMM with this certificate.
>
> We strongly recommend that you protect your universal reset package as carefully as the certificate you used to enroll devices in SEMM. Please remember that, just like the certificate itself, this universal reset package can be used to unenroll any of your organization’s Surface devices from SEMM.
>
> When you install a reset package, the Lowest Supported Value (LSV) is reset to a value of 1. You can reenroll a device by using an existing configuration package. The device will prompt for the certificate thumbprint before ownership is taken.
>
> For this reason, the reenrollment of a device in SEMM would require a new package to be created and installed on that device. Because this action is a new enrollment and not a change in configuration on a device already enrolled in SEMM, the device will prompt for the certificate thumbprint before ownership is taken.
