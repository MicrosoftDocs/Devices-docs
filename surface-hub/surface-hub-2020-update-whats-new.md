---
title: "What's new in Windows 10 Team 2020 updates"
description: "Check out what's new in the latest update of the Surface Hub operating system, Windows 10 Team 2020 Update."
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
manager: frankbu
ms.topic: overview
ms.date: 02/15/2022
ms.localizationpriority: Medium
---

# What's new in Windows 10 Team 2020 updates

Surface Hub benefits from periodic updates that deliver new features and functionality. The 2020 Update (20H2) to Windows 10 Team, and subsequently Update 1 & Update 2, deliver significant improvements to device deployment and manageability along with the latest Windows features.

## Windows 10 Team 2020 Update 2 

### GCC High support

After installation of this update ([KB5010415](https://support.microsoft.com/help/5010415) or a subsequent Windows CU), Surface Hubs are supported in GCC High environments. At this time, [additional steps ](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h) are needed for the Teams Rooms client to successfully connect to GCC High tenants.

### Support for Surface Hub 2 Smart Camera

The AI-powered Surface Hub 2 Smart Camera is optimized for hybrid teams allowing remote participants to see people interact with content on the Surface Hub while also viewing everyone else in the room.  To learn more, see [Install and manage Surface Hub 2 Smart Camera](surface-hub-2-smart-camera.md). 

### Support for Progressive Web Apps (PWAs)

Admins can remotely install PWAs on Surface Hubs using a mobile device management provider (MDM) applying a provisioning pack. To learn more, see [Install Progressive Web Apps on Surface Hub](install-pwa-surface-hub.md). 

### Ease of Access updates

Users can adjust Ease of Access settings during a Surface Hub session and close apps just like they do in other versions of Windows 10 or Windows 11. 

- **Ease of Access**. Users can adjust the following settings without signing in:   Display, Text cursor, Magnifier, High contrast, Narrator, Closed captions, and Keyboard. 
- **Familiar UI for apps**. Users can close apps on Surface Hub by selecting the Close button in the top right corner of the app. This removes the need to close apps by dragging them to the bottom of the Surface Hub display. (Note: This functionality will be available on the Edge browser as part of the next Edge update, scheduled for March 2022.) 

To learn more, see [Adjust Ease of Access settings on Surface Hub](accessibility-surface-hub.md).

### Administrator updates

- **Event Viewer**. Admins can access the Windows Event Viewer directly from the Settings app. 
- **New mobile device management (MDM) policy settings**. New Configuration service providers (CSPs) include:

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

To learn more, see [Configure non-Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).

## Windows 10 Team 2020 Update 1

### Support for new Teams Rooms application

After installation of this update ([KB5005101](https://support.microsoft.com/help/5005101) or a subsequent Windows CU), Surface Hubs support an automatic upgrade to the new [Teams Rooms client](surface-hub-teams-rooms.md) through Windows Update.

### Support for new Whiteboard application

After installation of this update, Surface Hubs support an automatic upgrade (when available) to the new [Whiteboard app](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226) through Microsoft Store updates.

### New Microsoft Edge browser installed by default

After installation of this update, Surface Hubs will automatically replace their Microsoft Edge Legacy browser with the new Chromium-based Edge browser.  To learn more, see [Manage Microsoft Edge on Surface Hub](surface-hub-install-chromium-edge.md). Edge Legacy is no longer available on Windows 10 Team after installation of this update or a subsequent Windows CU.

## Windows 10 Team 2020 Update (20H2)

### Deployment and manageability

- **Modern authentication for cloud device accounts**. Surface Hub supports Exchange Web Services (EWS) and Active Directory Authentication Library (ADAL) based authentication to connect to Exchange, allowing customers to deprecate the use of Basic authentication. To learn more, see [Modern authentication on Surface Hub](surface-hub-modern-auth.md).
- **More than 20 new and updated MDM policy settings**.  These policy settings give IT admins improved control over multiple device settings, including app updates from the Microsoft Store, wireless projection settings such as Miracast over infrastructure, network settings such as Quality-Of-Service and 802.1x wired authentication, and new privacy/GDPR related settings. New CSPs include:

  - [Accounts CSP](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

To learn more, see:

- [CSPs supported in Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Manage Surface Hub with an MDM provider](manage-settings-with-mdm-for-surface-hub.md)

### Azure Active Directory Joined devices

- **Single sign-on (SSO) for Azure AD joined devices**. When users sign in with their Microsoft 365 credentials to **My meetings and files**, their credentials flow seamlessly from app to app – including Microsoft 365 experiences in the browser.
- **Conditional access (CA) for Azure AD joined devices**. IT admins can control user access to organizational resources from Azure AD joined Surface Hubs by assigning device policies per their corporate security and compliance requirements.
- **Support for non-Global admins for Azure AD joined devices**. Customers can choose a more granular set of admins within their admin hierarchy to manage Surface Hub. To learn more, see [Configure non-Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).

### Inking improvements

- **Support for dual-pen inking on Surface Hub 2S**.  Use the whiteboard and collaborate side-by-side on Surface Hub 2S with two Surface Hub 2 Pens. Any system hardware update installed after upgrading to Windows 10 Team 2020 will add firmware support for this scenario.

### Microsoft Teams  

- **Microsoft Teams installed by default**. Microsoft Teams is the default app for meetings, calls and collaboration on new Surface Hub devices, which can be changed or configured via MDM or directly on Surface Hub using the Settings app. To learn more, see [Deploy Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **Support for Proximity Join with Microsoft Teams**.  Proximity Join lets users take scheduled Microsoft Teams calls on a nearby Surface Hub using their laptop or phone.  It also lets users transition an in-progress meeting to a nearby Surface Hub. Windows 10 Team 2020 Update adds Mobile Device Management (MDM) support to configure Proximity Join. To learn more, see:

  - [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Manage Microsoft Teams settings on Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Support for Coordinated Meetings with Microsoft Teams**. In meeting rooms that feature a Surface Hub and a Microsoft Teams Room device, or spaces with two Surface Hub devices, Coordinated Meetings let users quickly leverage both devices during a Microsoft Teams meeting. Users can join a meeting from either device with a single tap and maximize screen real estate by showing video feeds on one device and a digital whiteboard or content on the other. Windows 10 Team 2020 Update adds Mobile Device Management (MDM) support to configure Coordinated Meetings, and the feature will be subsequently released as a Microsoft Teams update through Microsoft Store. To learn more, see [Set up Coordinated Meetings with Microsoft Teams Rooms and Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

### Security

- **Passwordless sign-in using FIDO2 security keys** With FIDO2 security keys, users can quickly sign in to Surface Hub without typing usernames and passwords. Combined with Single Sign-On (SSO), this feature provides fast and seamless authentication to files, apps, and websites during a meeting. To learn more, see [Configure passwordless sign-in on Surface Hub](surface-hub-2s-phone-authenticate.md).
- **Improvements to passwordless sign-in using Microsoft Authenticator**.  For organizations that use Azure AD, users can sign in with the Microsoft Authenticator app. Additionally, users can sign in with their preferred email aliases in Azure AD or their User Principal Name (UPN). To learn more, see [Sign in to Surface Hub with Microsoft Authenticator](surface-hub-authenticator-app.md).

## Learn more

- [Windows 10 Team 2020 Update 1 released to all Surface Hubs](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 Team 2020 Update available October 27](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
