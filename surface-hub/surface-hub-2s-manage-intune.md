---
title: "Manage Surface Hub with an MDM provider"
description: "Learn how to update and manage Surface Hub using MDM provider."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/23/2021
ms.localizationpriority: Medium
---

# Manage Surface Hub with an MDM provider

Surface Hub allows IT administrators to manage settings and policies using a mobile device management (MDM) provider such as Microsoft Intune. Surface Hub has a built-in management component to communicate with the management server, so there is no need to install additional clients on the device.

## Enrolling Surface Hub

You can enroll Surface into Microsoft Intune or other MDM provider via Manual or Auto enrollment.

### Manual enrollment

1. Open the **Settings** app and sign in as a local administrator. Select **Surface Hub** > **Device management** and then select **+** to add.
2.	You will be prompted to login with the account to use for your MDM provider. After authenticating, the device automatically enrolls into your MDM provider.

> [!TIP]
> If you’re using Intune and the server address is not detected, enter **manage.microsoft.com**.
   
> [!NOTE]
> The account used for authentication will be the MDM provider enrollment account.

### Auto Enrollment — Azure AD affiliated

During the initial setup process, when affiliating a Surface Hub with an Azure Active Directory (AD) tenant that has Intune auto enrollment enabled, the device will automatically enroll with Intune. For more information, refer to [Intune enrollment methods for Windows devices](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods). Azure AD affiliation and Intune auto enrollment is required for the Surface Hub to be a "compliant device" in Intune. 

## Manage Windows 10 Team settings with Intune

The foundational building block of policy settings management in Intune and other MDM providers is the XML-based Open Mobile Alliance - Device Management (OMA-DM) protocol. Windows 10 implements OMA-DM XML via one of many available Configuration service providers (CSPs) with names like AccountManagement CSP, DeviceStatus CSP, Wirednetwork-CSP, and so on. For a complete list, refer to [CSPs supported in Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport).


Microsoft Intune and other MDM providers use CSPs to deliver a UI that enables you to configure policy settings within Configuration profiles. Intune uses the Surface Hub CSP for its built in profile --  **Device restrictions (Windows 10 Team)** -- letting you configure basic settings such as preventing Surface Hub from "waking up" whenever anyone enters the room where it's located. To manage Hub settings and features outside of Intune's built-in profile, you'll need to create a custom profile, which is created similar to a built-in profile, as shown below. 

To summarize, options to configure and manage policy settings within Intune include the following: 
 
- **Create a Device restriction profile.** Use Intune's built in profile and configure settings directly via the Intune UI. See [Create device restriction profile](#configure-device-restriction-profile).
- **Create a Device configuration profile.**  Select a template that includes a logical grouping of settings for a feature or technology. See [Create Device configuration profile](#create-device-configuration-profile).
- **Create a Custom configuration profile.**  Extend your scope of management using an OMA Uniform Resource Identifier (OMA URI) from any of the [CSPs supported in Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport). See [Create custom configuration profile](#configure-custom-configuration-profile).


## Create Device restriction profile

1. Sign in to [**Microsoft Endpoint Manager admin center**](https://endpoint.microsoft.com/), select **Devices** > **Configuration profiles** > **+** **Create profile**.
2. Under **Platform**, select **Windows 10 and later** >
3. Under ****Profile type**,** select **Templates** and then select **Device restrictions (Windows 10 Team)**
4. Select **Create**.
5. Add a name and select **Next.**
6. You can now browse and select preset device restriction settings for Surface Hub across the following categories: Apps and experience, Azure operational insights, Maintenance, Session, and Wireless projection. The example shown in the following figure specifies a 4-hour maintenance window and a 15 minute timeout for screen, sleep and session resume.

     ![Configure Surface Hub settings with Intune device restriction profile](images/sh-device-restrictions.png)


For more information about creating and managing profiles, see [Restrict devices features using policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile).
 
For more information about how to manage Surface Hub features and settings, see [Surface Hub Windows 10 Team device restrictions in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## Create Device configuration profile

1. Sign in to [**Microsoft Endpoint Manager admin center**](https://endpoint.microsoft.com/), select **Devices** > **Configuration profiles** > **+ Create profile**.
2. Under **Platform**, select **Windows 10 and later** >
3. Under **Profile type**, select **Templates** and choose from the following templates supported on Surface Hub:

    - Device restrictions (Windows 10 Team), as described in the [previous section](#configure-device-restriction-profile).
    - Microsoft Defender for Endpoint (Windows 10 Desktop)
    - PKCS certificate
    - PKCS imported certificate
    - SCEP certificate
    - Trusted certificate

## Create Custom configuration profile

You can extend the scope of management by creating a custom profile using an OMA Uniform Resource Identifier (OMA URI) from any of the Configuration service providers (CSPs) supported by the Surface Hub. For details on these CSPs, see the following resources:

- [Configuration service provider reference](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference)
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Policy CSPs supported by Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)

To implement CSP-based policy settings, begin by generating an OMA URI and then add them to a custom configuration profile in Intune.

### Generate OMA URI for target setting
 
To generate the OMA URI for any setting in the CSP documentation:

1. In the CSP documentation, identify the root node of the CSP. Generally, this looks like **./Vendor/MSFT/<name of CSP>**. For example, the root node of the [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) is **./Vendor/MSFT/SurfaceHub**.
2. Identify the node path for the setting you want to use. For example, the node path for the setting to enable wireless projection is **InBoxApps/WirelessProjection/Enabled**.
3. Append the node path to the root node to generate the OMA URI. For example, the OMA URI for the setting to enable wireless projection is **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled.**
4. The data type is also stated in the CSP documentation. The most common data types are:
    - char (String)
    - int (Integer)
    - bool (Boolean)

### Add OMA URI to custom profile

1. In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.
2. Under Platform select **Windows 10 and later.** Under Profile, select **Custom**, and then select **Create.**
3. Add a name and optional description and then select **Next.**
4. Under **Configuration settings** > **OMA-URI Settings**, select **Add**.

For a detailed reference of supported Surface Hub CSP settings, refer to the [Appendix](#appendix-supported-surface-hub-csp-settings) below.
  
## Quality of Service (QoS) settings

To ensure optimal video and audio quality on Surface Hub, add the following QoS settings to the device. 

### Microsoft Teams QoS settings 

| Name | Description | OMA-URI | Type | Value |
|:------ |:------------- |:--------- |:------ |:------- |
|**Audio Ports**| Audio Port range | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | String  | 3478-3479 |
|**Audio DSCP**| Audio ports marking | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | Integer | 46 |
|**Video Port**| Video Port range | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | String  | 3480 |
|**Video DSCP**| Video ports marking | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | Integer | 34 |
|**Sharing Port**| Sharing Port range | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | String  | 3481 |
|**Sharing DSCP**| Sharing ports marking | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | Integer | 18 |
|**P2P Audio Ports**| Audio Port range | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | String  | 50000-50019 |
|**P2P Audio DSCP**| Audio ports marking | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | Integer | 46 |
|**P2P Video Ports**| Video Port range | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | String  | 50020-50039 |
|**P2P Video DSCP**| Video ports marking | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | Integer | 34 |
|**P2P Sharing Ports**| Sharing Port range | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | String  | 50040-50059 |
|**P2P Sharing DSCP**| Sharing ports marking | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | Integer | 18 |


### Skype for Business QoS settings

| Name                 | Description           | OMA-URI                                                                    | Type    | Value                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| Audio Ports          | Audio Port range      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | String  | 50000-50019                    |
| Audio DSCP           | Audio ports marking   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | Integer | 46                             |
| Audio Media Source   | Skype App name        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | String  | Microsoft.PPISkype.Windows.exe |
| Video Ports          | Video Port range      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | String  | 50020-50039                    |
| Video DSCP           | Video ports marking   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | Integer | 34                             |
| Video Media Source   | Skype App name        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | String  | Microsoft.PPISkype.Windows.exe |
| Sharing Ports        | Sharing Port range    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | String  | 50040-50059                    |
| Sharing DSCP         | Sharing ports marking | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | Integer | 18                             |
| Sharing Media Source | Skype App name        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | String  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> Both tables show default port ranges. Administrators may change the port ranges in the Skype for Business and Teams control panel.

## Microsoft Teams settings

You can configure various Microsoft Teams settings using Intune. To learn more, see [Manage Microsoft Teams configuration on Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config).

### Modes

Surface Hub comes installed with Microsoft Teams in mode 0, which supports both Microsoft Teams and Skype for Business. The modes function as described below:

- Mode 0 — Skype for Business with Microsoft Teams functionality for scheduled meetings.
- Mode 1 — Microsoft Teams with Skype for Business functionality for scheduled meetings.
- Mode 2 — Microsoft Teams only.

To adjust the mode, add the following settings to a [custom device configuration profile](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).

| Name | Description | OMA-URI | Type | Value |
|:--- |:--- |:--- |:--- |:--- |
|**Teams App ID**|App name|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|String| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams App Mode**|Teams mode|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 or 1 or 2|

### Coordinated Meetings and proximity join

Teams Coordinated Meeting and proximity join features can be [configured through an XML file](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) deployed via an Intune profile.


## Appendix: Supported Surface Hub CSP settings

| Setting                                                                      | Node in the SurfaceHub CSP                                                  | 
| -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | 
| Maintenance hours                                                                | MaintenanceHoursSimple/Hours/StartTime<br>MaintenanceHoursSimple/Hours/Duration | 
| Automatically turn on the screen using motion sensors                            | InBoxApps/Welcome/AutoWakeScreen                                                | 
| Require a pin for wireless projection                                            | InBoxApps/WirelessProjection/PINRequired                                        | 
| Enable wireless projection                                                       | InBoxApps/WirelessProjection/Enabled                                            | 
| Miracast channel to use for wireless projection                                  | InBoxApps/WirelessProjection/Channel                                            | 
| Connect to your Operations Management Suite workspace                            | MOMAgent/WorkspaceID<br>MOMAgent/WorkspaceKey                                   | 
| Welcome screen background image                                                  | InBoxApps/Welcome/CurrentBackgroundPath                                         | 
| Meeting information displayed on the welcome screen                              | InBoxApps/Welcome/MeetingInfoOption                                             | 
| Friendly name for wireless projection                                            | Properties/FriendlyName                                                         | 
| Device account                                                                   | DeviceAccount/*<name_of_policy>*                                                | 
| Specify Skype domain                                                             | InBoxApps/SkypeForBusiness/DomainName                                           | 
| Auto launch Connect App when projection is initiated                             | InBoxApps/Connect/AutoLaunch                                                    | 
| Set default volume                                                               | Properties/DefaultVolume                                                        | 
| Set screen timeout                                                               | Properties/ScreenTimeout                                                        | 
| Set session timeout                                                              | Properties/SessionTimeout                                                       | 
| Set sleep timeout                                                                | Properties/SleepTimeout                                                         | 
| Allow session to resume after screen is idle                                     | Properties/AllowSessionResume                                                   | 
| Allow device account to be used for proxy authentication                         | Properties/AllowAutoProxyAuth                                                   | 
| Disable auto-populating the sign-in dialog with invitees from scheduled meetings | Properties/DisableSignInSuggestions                                             | 
| Disable "My meetings and files" feature in Start menu                            | Properties/DoNotShowMyMeetingsAndFiles                                          | 
| Set the LanProfile for 802.1x Wired Auth                                         | Dot3/LanProfile                                                                 | 
| Set the EapUserData for 802.1x Wired Auth                                        | Dot3/EapUserData                                                                | 


## Supported Windows 10 settings

In addition to Surface Hub-specific settings, there are numerous settings common to all Windows 10 devices. These settings are defined in the [Configuration service provider reference](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).
The following tables include info on Windows 10 settings that have been validated with Surface Hub. There is a table with settings for these areas: security, browser, Windows Updates, Microsoft Defender, remote reboot, certificates, and logs.

### Security settings

| Setting            | Details                                                                                        | CSP reference                                                                                                                                                    | 
| ------------------ | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | 
| Allow Bluetooth    | Keep this enabled to support Bluetooth peripherals.                                            | [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                                     | 
| Bluetooth policies | Use to set the Bluetooth device name, and block advertising, discovery, and automatic pairing. | Bluetooth/*<name of policy>*See [Policy CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                                              | 
| Allow camera       | Keep this enabled for Skype for Business.                                                      | [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                                                       | 
| Allow location     | Keep this enabled to support apps such as Maps.                                                | [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                                                   | 
| Allow telemetry    | Keep this enabled to help Microsoft improve Surface Hub.                                       | [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                                                 | 
| Allow USB Drives   | Keep this enabled to support USB drives on Surface Hub                                         | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | 

 

### Browser settings

| Setting                                                             | Details                                                                                                                                                         | CSP reference                                                                                                                                                          | 
| ------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| Homepages                                                           | Use to configure the default homepages in Microsoft Edge.                                                                                                       | [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                                               | 
| Allow cookies                                                       | Surface Hub automatically deletes cookies at the end of a session. Use this to block cookies within a session.                                                  | [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                                                         | 
| Allow developer tools                                               | Use to stop users from using F12 Developer Tools.                                                                                                               | [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                                           | 
| Allow Do Not Track                                                  | Use to enable Do Not Track headers.                                                                                                                             | [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                                                   | 
| Allow pop-ups                                                       | Use to block pop-up browser windows.                                                                                                                            | [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                                                           | 
| Allow search suggestions                                            | Use to block search suggestions in the address bar.                                                                                                             | [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)             | 
| Allow Microsoft Defender SmartScreen                                  | Keep this enabled to turn on Microsoft Defender SmartScreen.                                                                                                      | [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                                                 | 
| Prevent ignoring Microsoft Defender SmartScreen warnings for websites | For extra security, use to stop users from ignoring Microsoft Defender SmartScreen warnings and block them from accessing potentially malicious websites.         | [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)                 | 
| Prevent ignoring Microsoft Defender SmartScreen warnings for files    | For extra security, use to stop users from ignoring Microsoft Defender SmartScreen warnings and block them from downloading unverified files from Microsoft Edge. | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | 

 

### Windows Update settings

| Setting                                           | Details                                                                                                                                                                                                                      | CSP reference                                                                                                                                       | 
| ------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- | 
| Use Current Branch or Current Branch for Business | Use to configure Windows Update for Business – see [Windows updates](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).                                                                   | [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)                        | 
| Defer feature updates                             | See above.                                                                                                                                                                                                                   | [Update/ DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | 
| Defer quality updates                             | See above.                                                                                                                                                                                                                   | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | 
| Pause feature updates                             | See above.                                                                                                                                                                                                                   | [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)                          | 
| Pause quality updates                             | See above.                                                                                                                                                                                                                   | [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)                          | 
| Configure device to use WSUS                      | Use to connect your Surface Hub to WSUS instead of Windows Update – see [Windows updates](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).                                              | [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                                | 
| Delivery optimization                             | Use peer-to-peer content sharing to reduce bandwidth issues during updates. See [Configure Delivery Optimization for Windows 10](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization) for details. | DeliveryOptimization/*<name of policy>*<br>See [Policy CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                      | 


### Microsoft Defender settings

| Setting           | Details                                                                                            | CSP reference                                                                                                      | 
| ----------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ | 
| Defender policies | Use to configure various Defender settings, including a scheduled scan time.                       | Defender/*<name of policy>*See [Policy CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx) | 
| Defender status   | Use to initiate a Defender scan, force a Security intelligence update, query any threats detected. | [Defender CSP](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                                  | 


### Remote reboot

| Setting                                              | Details                                                                                                                                                                       | CSP reference                                                                                                                       |
| ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | 
| Reboot the device immediately                        | Use in conjunction with Azure Monitor to minimize support costs – see [Monitor your Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/monitor-surface-hub). | ./Vendor/MSFT/Reboot/RebootNow<br>See [Reboot CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)               | 
| Reboot the device at a scheduled date and time       | See above.                                                                                                                                                                    | ./Vendor/MSFT/Reboot/Schedule/Single<br>See [Reboot CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)         | 
| Reboot the device daily at a scheduled date and time | See above.                                                                                                                                                                    | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent<br>See [Reboot CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | 

### Additional settings

| Setting                         | Details                                                                                                                                                                                       | CSP reference                                                                                                                |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Install trusted CA certificates | Use to deploy trusted root and intermediate CA certificates. See [Configure Intune certificate profiles](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles). | [RootCATrustedCertificates CSP](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx)                           |
| Collect ETW logs                | Use to remotely collect ETW logs from Surface Hub. Note this is not supported in Intune.                                                                                                      | [DiagnosticLog CSP](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx)                                       |
| Set Network QoS Policy          | Use to set a QoS policy to perform a set of actions on network traffic. This is useful for prioritizing Skype network packets.                                                                | [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp)         |
| Set Network proxy               | Use to configure a proxy server for ethernet and Wi-Fi connections.                                                                                                                           | [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp)                 |
| Configure Start menu            | Use to configure which apps are displayed on the Start menu. For more information, see [Configure Surface Hub Start menu](https://docs.microsoft.com/surface-hub/surface-hub-start-menu)      | [Policy CSP: Start/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) |
