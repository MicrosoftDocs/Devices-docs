---
title: Manage settings with an MDM provider (Surface Hub)
description: Microsoft Surface Hub provides an enterprise management solution to help IT administrators manage policies and business applications on these devices using a mobile device management (MDM) solution.
ms.assetid: 18EB8464-6E22-479D-B0C3-21C4ADD168FE
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 03/25/2021
ms.localizationpriority: medium
---

# Manage Surface Hub with an MDM provider

Surface Hub allows IT administrators to manage settings and policies using a mobile device management (MDM) provider such as Microsoft Intune. Surface Hub has a built-in management component to communicate with the management server. There is no need to install additional clients on the device.

## Enrolling Surface Hub into MDM management 

You can enroll Surface into Microsoft Intune or other MDM provider via manual or auto enrollment.

### Manual enrollment

1. Open the **Settings** app and sign in as a local administrator. Select **Surface Hub** > **Device management** and then select **+Device management**.
2. You will be prompted to sign in with the account to use for your MDM provider. After authenticating, the device automatically enrolls with your MDM provider.

> [!TIP]
> If you’re using Intune and the server address is not detected, enter **manage.microsoft.com**.
   
> [!NOTE]
> MDM enrollment uses the account details provided for authentication. The account must have permissions to enroll a Windows device as well as an Intune license (or the equivalent enrollment promissions configured in your third-party MDM provider).

### Auto Enrollment — Azure AD affiliated

During the initial setup process, when affiliating Surface Hub with an Azure Active Directory (AD) tenant that has Intune auto enrollment enabled, the device will automatically enroll with Intune. To learn more, refer to [Intune enrollment methods for Windows devices](/intune/enrollment/windows-enrollment-methods). Azure AD affiliation and Intune auto enrollment are required for the Surface Hub to be a "compliant device" in Intune. 

## Manage Surface Hub Windows 10 Team settings with Intune

The foundational building block of policy settings management in Intune and other MDM providers is the XML-based Open Mobile Alliance-Device Management (OMA-DM) protocol. Windows implements OMA-DM XML via one of many available Configuration service providers (CSPs) with names like AccountManagement CSP, DeviceStatus CSP, WiFi-CSP, and so on. For a complete list, refer to [CSPs supported in Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-support#csps-supported-in-microsoft-surface-hub).

Microsoft Intune and other MDM providers use CSPs to deliver a UI that enables you to configure policy settings within Configuration profiles. Intune uses the Surface Hub CSP for its built-in template —  **Device restrictions (Windows 10 Team)** — letting you configure basic settings such as preventing Surface Hub from "waking up" whenever anyone moves nearby within its proximity range. To manage Hub settings and features outside of Intune's built-in profile, you'll need to use a custom profile, as [shown below](#create-custom-configuration-profile). 

To summarize, options to configure and manage policy settings within Intune include the following: 
 
- **Create a Device restriction profile.** Use Intune's built-in Surface Hub template and configure settings directly in the Intune UI. See [Create device restriction profile](#create-device-restriction-profile).
- **Create a Device configuration profile.**  Select a template focused on a specific feature or technology such as Microsoft Defender or security certificates. See [Create Device configuration profile](#create-device-configuration-profile).
- **Create a Custom configuration profile.**  Extend your scope of management using an OMA Uniform Resource Identifier (OMA URI) from any of the [CSPs supported in Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-support#csps-supported-in-microsoft-surface-hub). See [Create custom configuration profile](#create-custom-configuration-profile).

> [!NOTE]
> Profiles should be assigned to device groups containing the enrolled Surface Hub devices.

## Create Device restriction profile

1. Sign in to [**Microsoft Endpoint Manager admin center**](https://endpoint.microsoft.com/), select **Devices** > **Configuration profiles** > **+** **Create profile**.
2. Under **Platform**, select **Windows 10 and later** >
3. Under ****Profile type**,** select **Templates** and then select **Device restrictions (Windows 10 Team)**
4. Select **Create**, add a name and then select **Next.**
6. You can now browse and choose from preset device restriction settings for Surface Hub across the following categories: Apps and experience, Azure operational insights, Maintenance, Session, and Wireless projection. The example shown in the following figure specifies a 4-hour maintenance window and a 15 minute timeout for screen, sleep and session resume.

     ![Configure Surface Hub settings with Intune device restriction profile.](images/sh-device-restrictions.png)

For more information about creating and managing profiles, see [Restrict devices features using policy in Microsoft Intune](/mem/intune/configuration/device-restrictions-configure#create-the-profile).
 
For more information about how to manage Surface Hub features and settings, see [Windows 10 Team settings to allow or restrict features on Surface Hub using Intune](/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## Create Device configuration profile

1. Sign in to [**Microsoft Endpoint Manager admin center**](https://endpoint.microsoft.com/), select **Devices** > **Configuration profiles** > **+ Create profile**.
2. Under **Platform**, select **Windows 10 and later** >
3. Under **Profile type**, select **Templates** and choose from the following templates supported on Surface Hub:

    - Device restrictions (Windows 10 Team), as described in the [previous section](#create-device-restriction-profile).
    - Microsoft Defender for Endpoint (Windows 10 Desktop)
    - PKCS certificate
    - PKCS imported certificate
    - SCEP certificate
    - Trusted certificate

## Create Custom configuration profile

You can extend the scope of management by [creating a custom profile](/mem/intune/configuration/custom-settings-configure) using an OMA URI from any of the [CSPs supported in Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-support#csps-supported-in-microsoft-surface-hub). Each setting in a CSP has a corresponding OMA-URI that you can set by using custom configuration profiles in Intune. For details on the CSPs supported by Surface Hub, you can reference the following resources: 

- [Configuration service provider support](/windows/client-management/mdm/configuration-service-provider-support#csps-supported-in-microsoft-surface-hub)
- [Policy CSPs supported by Microsoft Surface Hub](/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> Managing the device account using settings from [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp) is not currently possible with Intune and requires using a third-party MDM provider.

To implement CSP-based policy settings, begin by generating an OMA URI and then add it to a custom configuration profile in Intune.

### Generate OMA URI for target setting
 
To generate the OMA URI for any setting:

1. In the [CSP documentation](/windows/client-management/mdm/configuration-service-provider-support#csps-supported-in-microsoft-surface-hub), identify the root node of the CSP. Generally, this looks like **./Vendor/MSFT/NameOfCSP**. 
    - **Example:** The root node of the [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp) is **./Vendor/MSFT/SurfaceHub**.
2. Identify the node path for the setting you want to use. 
    - **Example:** The node path for the setting to enable wireless projection is **InBoxApps/WirelessProjection/Enabled**.
3. Append the node path to the root node to generate the OMA URI. 
    - **Example:** The OMA URI for the setting to enable wireless projection is **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled.**
4. The data type is also stated in the CSP documentation. The most common data types are:
    - char (String)
    - int (Integer)
    - bool (Boolean)

### Add OMA URI to Custom configuration profile

1. In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.
2. Under Platform select **Windows 10 and later.** Under Profile, select **Custom**, and then select **Create.**
3. Add a name and optional description and then select **Next.**
4. Under **Configuration settings** > **OMA-URI Settings**, select **Add**.

  
## Microsoft Teams and Skype for Business settings

This section highlights Teams and Skype for Business settings that you can manage via Intune or other MDM provider. This includes:

- [Quality of Service (QoS)](#quality-of-service-settings)
- [Manage Teams-specific features](#manage-teams-specific-features)

### Quality of Service settings

To ensure optimal video and audio quality on Surface Hub, add the following QoS settings to the device. 

| Name                 | Description           | OMA-URI                                                                 | Type    | Value                          |
| -------------------- | --------------------- | ----------------------------------------------------------------------- | ------- | ------------------------------ |
| Audio Ports          | Audio Port range      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/SourcePortMatchCondition    | String  | 50000-50019                    |
| Audio DSCP           | Audio ports marking   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/DSCPAction                  | Integer | 46                             |
| Video Ports          | Video Port range      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/SourcePortMatchCondition    | String  | 50020-50039                    |
| Video DSCP           | Video ports marking   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/DSCPAction                  | Integer | 34                             |
| Sharing Ports        | Sharing Port range    | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/SourcePortMatchCondition  | String  | 50040-50059                    |
| Sharing DSCP         | Sharing ports marking | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/DSCPAction                | Integer | 18                             |

> [!NOTE]
> The table shows default port ranges. Administrators may change the port ranges in the Skype for Business and Teams control panel.

### Manage Teams-specific features

You can create a Custom configuration profile to manage Teams Coordinated Meetings, Proximity Join, and other features. To learn more, see [Manage Microsoft Teams configuration on Surface Hub](/microsoftteams/rooms/surface-hub-manage-config).

### Changing default app for meetings & calls

The default app for meetings & calls on the Surface Hub varies depending on how you install Windows 10 Team 2020 Update (aka Windows 10 20H2 Team edition). If you re-image a Surface Hub to Windows 10 20H2, Microsoft Teams will be set as the default, with Skype for Business not available (Mode 1). If you upgrade your Hub from an earlier OS version, Skype for Business will remain as the default, with Teams functionality available (Mode 0) unless you had already configured Teams as your default. 

To change the default installation, use a [custom profile](/mem/intune/configuration/custom-settings-configure) to set the Teams Meeting Mode as follows:  

- Mode 0 — Skype for Business with Microsoft Teams functionality for scheduled meetings.
- Mode 1 — Microsoft Teams only.

| Name | Description | OMA-URI | Type | Value |
|:--- |:--- |:--- |:--- |:--- |
|**Teams App ID**|App name|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|String| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams App Mode**|Teams mode|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|Integer| 0 or 1|


