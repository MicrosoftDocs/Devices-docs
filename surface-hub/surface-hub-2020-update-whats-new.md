---
title: "What's new in Windows 10 Team 2020 updates"
description: "Check out what's new in the latest update of the Surface Hub operating system, Windows 10 Team 2020 Update."
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/19/2021
ms.localizationpriority: Medium
---

# What's new in Windows 10 Team 2020 updates

Surface Hub benefits from periodic updates that bring new features and functionality to Surface Hub. Windows 10 Team 2020 Update and Windows 10 Team 2020 Update 2 bring major improvements to device deployment and manageability along with the latest Windows 10 features.

## Windows 10 Team 2020 Update 2 

### Ease of use updates

Users can adjust Ease of use settings during a Surface Hub session and close apps just like they do in other versions of Windows 10. 

- **Accessibility**. Users can adjust the following settings without signing in:   Display, Mouse Pointer, Text cursor, Magnifier, High contrast, Narrator, Closed captions, Keyboard. 
- **Familiar UI for apps**. Users can now close apps on Surface Hub by selecting the close button, in the top right corner of the app,  This removes the need to close apps by dragging them to the bottom of the Surface Hub display. 

To learn more, see [Adjust ease of use settings on Surface Hub](accessibility-surface-hub.md).

### Administrator updates

- **Event Viewer**. Admins can access the Windows Event Viewer directly from the Settings app. 
- **New mobile device management (MDM) policy settings**. New Configuration service providers (CSPs) include:

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

To learn more, see [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).

## Windows 10 Team 2020 Update 

### Deployment and manageability

- **Modern authentication for cloud device accounts**. Surface Hub supports Exchange Web Services (EWS) and Active Directory Authentication Library (ADAL) based authentication to connect to Exchange, allowing customers to deprecate the use of Basic authentication. To learn more, see [Modern authentication on Surface Hub](surface-hub-modern-auth.md).
- **More than 20 new and updated MDM policy settings**.  These policy settings give IT admins improved control over multiple device settings including: app updates from the Microsoft Store, wireless projection settings such as Miracast over infrastructure, network settings such as Quality-Of-Service and 802.1x wired authentication, and new privacy/GDPR related settings. New Configuration service providers (CSPs) include:

  - [Accounts CSP](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)


To learn more, see:

- [CSPs supported in Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Manage Surface Hub with an MDM provider](manage-settings-with-mdm-for-surface-hub.md)

### Azure Active Directory Joined devices

- **Single sign-on (SSO) for Azure AD joined devices**. When users sign in with their Microsoft 365 credentials to “My meetings and files”, their user credentials flow seamlessly from app to app – including Microsoft 365 experiences in the browser.
- **Conditional access (CA) for Azure AD joined devices**. IT admins can control user access to organizational resources from Azure AD joined Surface Hubs by assigning device policies in accordance with their corporate security and compliance requirements.
- **Support for non-Global admins for Azure AD joined devices**. Customers can choose a more granular set of admins within their admin hierarchy to manage Surface Hub. To learn more, see [Configure non Global admin accounts on Surface Hub](surface-hub-2s-nonglobal-admin.md).

### Browser and pen

- **New Microsoft Edge installed by default**. Microsoft Edge has been rebuilt for optimal compatibility performance, security and privacy. To learn more, see [Manage Microsoft Edge on Surface Hub](surface-hub-install-chromium-edge.md).
- **Dual-pen inking on Surface Hub 2S**.   Users can whiteboard and collaborate side-by-side on Surface Hub 2S using two Surface Hub 2 Pens. The firmware updates required to enable dual-pen inking will be released with a subsequent update.

### Microsoft Teams  

- **Microsoft Teams installed by default**.        Microsoft Teams is included as the default Meetings, calling and collaboration app on new Surface Hub devices which can be changed or configured via MDM or directly on Surface Hub using the Settings app. To learn more, see [[Deploy Microsoft Teams](/MicrosoftTeams/teams-surface-hub).
- **Support for Proximity Join with Microsoft Teams**.  Proximity Join enables users to take scheduled Microsoft Teams calls on a nearby Surface Hub using their laptop/phone, or seamlessly transition an in-progress meeting to a nearby Surface Hub. Windows 10 Team 2020 Update adds Mobile Device Management (MDM) support to configure Proximity Join. To learn more, see:

  - [Microsoft Teams Blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833).
  - [Manage Microsoft Teams settings on Surface Hub](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **Support for Coordinated Meetings with Microsoft Teams**. In meeting rooms that feature a Surface Hub and a Microsoft Teams Room device, or spaces with two Surface Hub devices, Coordinated Meetings enable users to easily leverage both devices during a Microsoft Teams meeting. With a single tap, users can join a meeting from either device and maximize screen real estate by showing video feeds on one device, and a digital whiteboard or content on the other. Windows 10 Team 2020 Update adds Mobile Device Management (MDM) support to configure Coordinated Meetings, and the feature will be subsequently released as a Microsoft Teams update through Microsoft Store.To learn more, see [Set up Coordinated Meetings with Microsoft Teams Rooms and Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings).

### Security

- **Passwordless sign-in using FIDO2 security keys**     Using FIDO2 security keys, customers can quickly and easily sign into Surface Hub without having to type in usernames and passwords. Combined with Single Sign-On (SSO), this feature provides fast and seamless authentication to files, apps, and websites during a meeting. To learn more, see [Configure passwordless sign-in on Surface Hub](surface-hub-2s-phone-authenticate.md).
- **Improvements to passwordless sign-in using Microsoft Authenticator**.  For organizations that use Azure AD, users can use the Microsoft Authenticator app to sign in without having to type in usernames and passwords. Additionally, users can sign-in using their preferred email aliases in Azure AD in addition to their User Principal Name (UPN). To learn more, see [Sign in to Surface Hub with Microsoft Authenticator](surface-hub-authenticator-app.md).

## Learn more

- [Windows 10 Team 2020 Update 1 released to all Surface Hubs](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Install Windows 10 Team 2020 Update](surface-hub-2020-update.md)  
