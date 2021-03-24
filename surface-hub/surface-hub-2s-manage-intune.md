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

You can fully manage Surface Hub settings via Intune in the following ways:
 
- Create a **Device restriction profile** from options available directly in the Intune UI such as turning a feature on or off or choosing a preset value from a drop-down list. See [Configure device restriction profile](#configure-device-restriction-profile).
- Create a **Device configuration profile** and select a template that includes a logical grouping of settings for a feature or technology. See [Create Device configuration profile](#create-device-configuration-profile).
- Create a **Custom configuration profile** that lets you extend the scope of management by implementing Configuration service provider (CSP) based policy settings. These consist of OMA Uniform Resource Identifier (OMA URI) values that map to Registry keys or feature settings. See [Configure custom configuration profile](#configure-custom-configuration-profile).


### Configure device restriction profile

1. Sign in to [**Microsoft Endpoint Manager admin center**](https://endpoint.microsoft.com/), select **Devices** > **Configuration profiles** > **+** **Create profile**.
2. Under **Platform**, select **Windows 10 and later** >
3. Under ****Profile type**,** select **Templates** and then select **Device restrictions (Windows 10 Team)**
4. Select **Create**.
5. Add a name and select **Next.**
6. You can now browse and select preset device restriction settings for Surface Hub across the following categories: Apps and experience, Azure operational insights, Maintenance, Session, and Wireless projection. The example shown in the following figure specifies a 4-hour maintenance window and a 15 minute timeout for screen, sleep and session resume.

     ![Configure Surface Hub settings with Intune device restriction profile](images/sh-device-restrictions.png)


For more information about creating and managing profiles, see [Restrict devices features using policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile).
 
For more information about how to manage Surface Hub features and settings, see [Surface Hub Windows 10 Team device restrictions in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

### Create device configuration profile

1. Sign in to [**Microsoft Endpoint Manager admin center**](https://endpoint.microsoft.com/), select **Devices** > **Configuration profiles** > **+ Create profile**.
2. Under **Platform**, select **Windows 10 and later** >
3. Under **Profile type**, select **Templates** and choose from the following templates supported on Surface Hub:

    - Device restrictions (Windows 10 Team), as described in the [previous section](#configure-device-restriction-profile).
    - Microsoft Defender for Endpoint (Windows 10 Desktop)
    - PKCS certificate
    - PKCS imported certificate
    - SCEP certificate
    - Trusted certificate


### Configure custom configuration profile

You can extend the scope of management by using an OMA Uniform Resource Identifier (OMA URI) integrated with the Surface Hub Configuration service provider (CSP) along with multiple other CSPs across a wide range of enterprise management areas. To implement CSP-based policy settings, begin by generating an OMA URI and then add them to a custom configuration profile in Intune.

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
 
For more information, see the following resources:

- [Configuration service provider reference](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference)
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Policy CSPs supported by Microsoft Surface Hub](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)


## Supported Surface Hub CSP settings

| Setting                                                                      | Node in the SurfaceHub CSP                                                  | Supported with Intune? |
| -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | --------------------------------- |
| Maintenance hours                                                                | MaintenanceHoursSimple/Hours/StartTime<br>MaintenanceHoursSimple/Hours/Duration | Yes                               |
| Automatically turn on the screen using motion sensors                            | InBoxApps/Welcome/AutoWakeScreen                                                | Yes                               |
| Require a pin for wireless projection                                            | InBoxApps/WirelessProjection/PINRequired                                        | Yes                               |
| Enable wireless projection                                                       | InBoxApps/WirelessProjection/Enabled                                            | Yes                               |
| Miracast channel to use for wireless projection                                  | InBoxApps/WirelessProjection/Channel                                            | Yes                               |
| Connect to your Operations Management Suite workspace                            | MOMAgent/WorkspaceID<br>MOMAgent/WorkspaceKey                                   | Yes                               |
| Welcome screen background image                                                  | InBoxApps/Welcome/CurrentBackgroundPath                                         | Yes                               |
| Meeting information displayed on the welcome screen                              | InBoxApps/Welcome/MeetingInfoOption                                             | Yes                               |
| Friendly name for wireless projection                                            | Properties/FriendlyName                                                         | Yes. Use custom profile           |
| Device account                                                                   | DeviceAccount/*<name_of_policy>*                                                | No                                |
| Specify Skype domain                                                             | InBoxApps/SkypeForBusiness/DomainName                                           | Yes                               |
| Auto launch Connect App when projection is initiated                             | InBoxApps/Connect/AutoLaunch                                                    | Yes                               |
| Set default volume                                                               | Properties/DefaultVolume                                                        | Yes                               |
| Set screen timeout                                                               | Properties/ScreenTimeout                                                        | Yes                               |
| Set session timeout                                                              | Properties/SessionTimeout                                                       | Yes                               |
| Set sleep timeout                                                                | Properties/SleepTimeout                                                         | Yes                               |
| Allow session to resume after screen is idle                                     | Properties/AllowSessionResume                                                   | Yes                               |
| Allow device account to be used for proxy authentication                         | Properties/AllowAutoProxyAuth                                                   | Yes                               |
| Disable auto-populating the sign-in dialog with invitees from scheduled meetings | Properties/DisableSignInSuggestions                                             | Yes                               |
| Disable "My meetings and files" feature in Start menu                            | Properties/DoNotShowMyMeetingsAndFiles                                          | Yes                               |
| Set the LanProfile for 802.1x Wired Auth                                         | Dot3/LanProfile                                                                 | Yes. Use custom profile.          |
| Set the EapUserData for 802.1x Wired Auth                                        | Dot3/EapUserData                                                                | Yes. Use custom profile.          |




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
