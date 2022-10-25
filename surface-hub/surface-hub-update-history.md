---
title: Surface Hub update history
description: Surface Hub update history
ms.assetid: d66a9392-2b14-4cb2-95c3-92db0ae2de34
keywords:
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: dpandre
ms.topic: article
ms.localizationpriority: high
---

# Surface Hub update history

Windows was designed to be a service, which means it automatically gets better through periodic software updates. Typically you don’t have to do anything to get the latest Windows 10 updates—they'll download and install whenever they’re available.

Most Windows updates focus on performance and security improvements. In the list below, the most recent Windows update with Surface Hub-specific improvements is listed first. Updates are cumulative, so installing the latest available Windows update (even if it isn't on the list below) ensures that you also benefit from improvements in any previous updates. Microsoft Store apps are updated through the Microsoft Store (managed by the Surface Hub's system administrator). Details about app updates are provided on a per-app basis.

> [!TIP]
> This page is refreshed as new updates are released. Please refer to the [Surface Hub Important Information](https://support.microsoft.com/products/surface-devices/surface-hub) page for related topics on current and past releases that may require your attention.

## Windows 10 Team 2022 Update (22H2)

<details>
<summary>October 25, 2022 - update for Team based on KB5018482* (OS Build 19045.2193)</summary>

This update brings the Windows 10 Team 2022 Update to Surface Hub and includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Resolves an issue where Surface Hub devices did not advertise Miracast availability in some scenarios.
 
Please refer to the "[Install Windows 10 Team 2022 Update](/surface-hub/surface-hub-2022-update)" page for more information regarding update availability by region, distribution method, and device type.
*[KB5018482](https://support.microsoft.com/help/5018482)
</details>

## Windows 10 Team 2020 Update (20H2)

<details>
<summary>August 26, 2022 - update for Team based on KB5016688* (OS Build 19042.1949)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Resolves an issue where Teams or Skype for Business Quality of Service settings did not apply DSCP markings as expected.
* Update to allow the Edge (Chromium) browser to launch the File Explorer app when clicking on the Downloads folder icon.
 
Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5016688](https://support.microsoft.com/help/5016688)
</details>

<details>
<summary>August 24, 2022 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface UEFI update - 697.178.768.0
  * Improves system security and stability.
* Surface ME Firmware update - 11.8.92.4222
  * Improves system security and stability.
* Intel(R) Management Engine Interface driver - 2145.1.42.0
  * Improves system security and stability.
</details>

<details>
<summary>June 2, 2022 - update for Team based on KB5014023* (OS Build 19042.1741)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Resolves an issue where meeting invitations did not show up immediately on the Welcome screen calendar in some environments without a reboot.
* Resolves an issue where one-click meeting join from the Welcome screen calendar did not work in GCC High environments.
* Resolves an issue where a "Microsoft Teams is not responding" window would sometimes appear during regular Teams usage.
 
Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5014023](https://support.microsoft.com/help/5014023)
</details>

<details>
<summary>May 19, 2022 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Intel(R) graphics driver - 30.0.101.1339
  * Improves system stability.
* Intel(R) Ethernet driver - 12.19.1.37
  * Improves system stability.
* Surface SMC Firmware update - 4.3.139.0
  * Improves Surface Hub 2 Smart Camera performance in different lighting conditions.
* Surface UEFI update - 697.148.768.0
  * Improves thermal logging and detection of thermal shutdown scenarios.
</details>

<details>
<summary>April 21, 2022 - update for Team based on KB5011831* (OS Build 19042.1682)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Fix that prevents "End Session" from triggering the message "Your device needs an update. Restarting to finish it up..." and subsequent restart in some scenarios.
* Fix that ensures the [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp#deviceaccount) can be used with SyncML policies that configure Device Accounts in `DOMAIN\username` format.
 
Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5011831](https://support.microsoft.com/help/5011831)
</details>

<details>
<summary>March 22, 2022 - update for Team based on KB5011543* (OS Build 19042.1620)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Adds ability for administrators to [install Progressive Web Apps](install-pwa-surface-hub.md) (PWAs).
* Resolves an issue where Surface Hubs joined to Azure AD or configured with a local administrator account could fail to synchronize their computer clock.
* Resolves an issue where using Meetings and Files sign-in suggestions with the Authenticator app could force the user to repeat the login process.
 
Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5011543](https://support.microsoft.com/help/5011543)
</details>

<details>
<summary>February 15, 2022 - update for Team based on KB5010415* (OS Build 19042.1566)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub are outlined in [Windows 10 Team 2020 Update 2](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-2), and also include the below:

* Fix that allows Exchange services to be disabled during Device Account setup.
* Improves reliability for some Device Account setup scenarios when using an on-premises Exchange mailbox.
* Improves reliability for some MDM policy setting scenarios when using the SurfaceHub CSP.
* Improves reliability for incoming call scenarios when using Skype for Business.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5010415](https://support.microsoft.com/help/5010415)
</details>

<details>
<summary>January 25, 2022 - update for Team based on KB5009596* (OS Build 19042.1503)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Resolves an issue where Surface Hubs could not report data to their configured Azure Log Analytics workspaces.
* Resolves an issue where starting a Skype for Business meeting from a Surface Hub's Welcome screen could result in a fully maximized SfB client that was not minimizable.
* Resolves an issue where Azure AD-joined Surface Hubs did not pre-populate Meetings and Files sign-in with a list of meeting invitees.
* Resolves an issue where device account password rotation could not be enabled in some on-premises scenarios.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5009596](https://support.microsoft.com/help/5009596)
</details>

<details>
<summary>January 21, 2022 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface UEFI update - 694.3924.768.0
  * Improves system security and stability.
* Intel(R) Management Engine Interface driver - 2120.100.0.1085
  * Improves system security and stability.
</details>

<details>
<summary>November 22, 2021 - update for Team based on KB5007253* (OS Build 19042.1387)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Fix that enforces a 32-character limit when using MDM policy to set 'Friendly Name' on a Surface Hub.
* Fix that corrects AllowStorageCard MDM policy behavior when it is reverted back to a value of 1 (storage cards allowed) from 0.
* Update to allow the Edge (Chromium) browser to access the same file locations accessible in File Explorer, including an attached USB drive.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5007253](https://support.microsoft.com/help/5007253)
</details>

<details>
<summary>September 30, 2021 - KB5004196, KB5004198, and KB5004199</summary>

These updates to the Surface Hub deliver the Teams Room client, Teams Admin Center agent, and Managed Meeting Rooms agent. Key features are outlined in [Teams Room on Surface Hub](surface-hub-teams-rooms.md).
 
Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
</details>

<details>
<summary>September 30, 2021 - update for Team based on KB5005611* (OS Build 19042.1266)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Replaces Meeting Mode 1 (Teams preferred/SfB available) with Mode 2 functionality (Teams only); either setting can be used, but both have the same effect.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5005611](https://support.microsoft.com/help/5005611)
</details>

<details>
<summary>September 1, 2021 - update for Team based on KB5005101* (OS Build 19042.1202)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub are outlined in [Windows 10 Team 2020 Update 1](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-1) and also include the below:

* Improves reliability for some Device Account setup scenarios when using an on-premises Exchange mailbox.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5005101](https://support.microsoft.com/help/5005101)
</details>

<details>
<summary>July 29, 2021 - update for Team based on KB5004296* (OS Build 19042.1151)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Update to the "Collect logs" feature to include Windows diagnostic data in csv format.
* Fix that ensures that End Session cleanup fully removes all data related to Edge Chromium.
* Improves some personal sign-in scenarios with Azure AD-joined Surface Hubs when using the Authenticator app.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5004296](https://support.microsoft.com/help/5004296)
</details>

<details>
<summary>June 10, 2021 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface UEFI update - 694.3751.768.0
  * Addresses critical security vulnerability and improves system stability.
* Surface ME Firmware update - 11.8.86.3877
  * Addresses critical security vulnerability and improves system stability.
* Intel(R) Management Engine Interface driver - 2102.100.0.1044
  * Addresses critical security vulnerability and improves system stability.
</details>

<details>
<summary>April 13, 2021 - update for Team based on KB5001330* (OS Build 19042.928)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Resolves an issue where some Surface Hub devices were only installing monthly Windows security updates, instead of all Windows cumulative updates.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB5001330](https://support.microsoft.com/help/5001330)
</details>

<details>
<summary>March 13, 2021 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Intel(R) Bluetooth driver - 22.30.0.4
  * Improves system security and stability.
* Intel(R) graphics driver - 27.20.100.8682
  * Improves system security and stability.
* Intel(R) Wi-Fi driver - 22.30.0.11
  * Improves system security and stability.
</details>

<details>
<summary>February 2, 2021 - update for Team based on KB4598291* (OS Build 19042.789)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Fix that allows calendar synchronization with Exchange to work when the Device Account's UPN is not equal to its SMTP address.
* Adds ability for administrators to [disable the use of Modern Authentication](/windows/client-management/mdm/surfacehub-csp#deviceaccount-exchangemodernauthenabled) during calendar synchronization with Exchange.
* Ensures that Surface Hub users aren't prompted to enter proxy credentials after the "Use device account credentials" feature has been enabled.
* Resolves an issue where Windows Update and Store update checks would never complete if a proxy requiring authentication was in use.
* Improves the reliability of the Connect App during wired ingest scenarios.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB4598291](https://support.microsoft.com/help/4598291)
</details>

<details>
<summary>January 15, 2021 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface SMC Firmware update - 3.93.139.0
* Surface UEFI update - 694.3473.768.0
</details>

<details>
<summary>December 11, 2020 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface SMC Firmware update - 3.92.139.0
* Surface UEFI update - 694.3447.768.0
</details>

<details>
<summary>November 30, 2020 - update for Team based on KB4586853* (OS Build 19042.662)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), include:

* Update to Privacy Settings page to provide additional options.
* Resolves an issue where meetings that had already started were not displayed on Welcome/Start screen.
* Resolves an issue with cloud recovery for non-en-US locales.
* Skype for Business
  * Improves directional audio performance.
  * Reduced “pen tap” sounds when using Pen during Skype for Business calls.
* Improves reliability when enrolling into Windows Insider Program.
* Improves reliability of Windows Team shell.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services. *[KB4586853](https://support.microsoft.com/help/4586853)
</details>

<details>
<summary>November 24, 2020 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface SMC Firmware update - 3.91.139.0
  * Improve connected standby reliability.
* Surface Touch Firmware update - 3.91.139.0
  * Improve connected standby touch response.
* Surface USB Audio Firmware update - 3.91.139.0
* Surface Pen Firmware update - 3.91.139.0
</details>

<details>
<summary>October 27, 2020 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface System Aggregator Firmware update - 4.14.139.0
* Surface UEFI update - 694.3386.768.0
</details>

<details>
<summary>October 13, 2020 - update for Team based on KB4579311* (OS Build 19042.572)</summary>

Windows 10 Team 2020 Update for Surface Hub - General Release notes 

This update brings the Windows 10 Team 2020 Update to Surface Hub and includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4581839/windows-10-update-history), are noted on the page "[What's new in Windows 10 Team 2020 Update](/surface-hub/surface-hub-2020-update-whats-new)".

*[KB4579311](https://support.microsoft.com/help/4579311)
</details>

## Windows 10 Team Creators Update (1703)

<details>
<summary>September 1, 2020 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface SMC Firmware update - 1.177.139.0
  * Improves field repair scenarios.
* Surface SSD Firmware update - 5.14.139.0
  * Improves system stability.
* Surface Serial Hub driver - 9.40.139.0
  * Improves system stability.
</details>

<details>
<summary>May 4, 2020 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface USB audio driver - 15.3.6.0
  * Improves directional audio performance.
* Intel(R) display audio driver - 10.27.0.5
  * Improves screen sharing scenarios.
* Intel(R) graphics driver - 26.20.100.7263
  * Improves system stability.
* Surface System driver - 1.7.139.0
  * Improves system stability.
* Surface SMC Firmware update - 1.176.139.0
  * Improves system stability.
</details>

<details>
<summary>February 28, 2020 - update for Surface Hub 2S</summary>

This update is specific to the Surface Hub 2S and provides the driver and firmware updates outlined below:

* Surface Integration driver - 13.46.139.0 
  * Improves display brightness scenarios.
* Intel(R) Management Engine Interface driver - 1914.12.0.1256
  * Improves system stability.
* Surface SMC Firmware update - 1.161.139.0
  * Improves pen battery performance.
* Surface UEFI update - 694.2938.768.0
  * Improves system stability.
</details>

<details>
<summary>February 11, 2020 - update for Team based on KB4537765* (OS Build 15063.2284)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Resolves an issue where the Hub 2S can't be heard well by other participants during Skype for Business calls.
* Improves reliability for some Arabic, Hebrew, and other RTL language usage scenarios on Surface Hub.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4537765](https://support.microsoft.com/help/4537765)
</details>

<details>
<summary>January 14, 2020 - update for Team based on KB4534296* (OS Build 15063.2254)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Addresses an issue with log collection for Microsoft Surface Hub 2S.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4534296](https://support.microsoft.com/help/4534296)
</details>

<details>
<summary>September 24, 2019 - update for Team based on KB4516059*  (OS Build 15063.2078)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

 * Update to Surface Hub 2S Recovery Settings page to accurately reflect recovery options.
 * Update to Surface Hub 2S Welcome screen to improve device recognizability.
 * Addressed an issue with the Windows Team shell background displaying incorrectly.
 * Addressed an issue with Start Menu layout persistence when configured using MDM policy.
 * Fixed an issue in Microsoft Edge that occurs when browsing some internal websites.
 * Fixed an issue in Skype for Business that occurs when presenting in full-screen mode.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4516059](https://support.microsoft.com/help/4516059)
</details>

<details>
<summary>August 17, 2019 - update for Team based on KB4512474*  (OS Build 15063.2021)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

 * Ensures that Video Out on Hub 2S defaults to "Duplicate" mode.
 * Improves reliability for some Arabic language usage scenarios on Surface Hub.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4512474](https://support.microsoft.com/help/4512474)
 </details>

<details>
<summary>June 18, 2019 - update for Team based on KB4503289*  (OS Build 15063.1897)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Addresses an issue preventing a user from signing in to a Microsoft Surface Hub device with an Azure Active Directory account. This issue occurs because a previous session did not end successfully.
* Adds support for TLS 1.2 connections to identity providers and Exchange in device account setup scenarios.
* Fixes to improve reliability of Hardware Diagnostic App on Hub 2S. 
* Fix to improve consistency of first-run setup experience on Hub 2S. 

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4503289](https://support.microsoft.com/help/4503289)
</details>

<details>
<summary>May 28, 2019 - update for Team based on KB4499162*  (OS Build 15063.1835)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Ensures that Surface Hub users aren't prompted to enter proxy credentials after the "Use device account credentials" feature has been enabled.
* Resolves an issue where Skype connections fail periodically because audio/video isn't using the correct proxy.
* Adds support for TLS 1.2 in Skype for Business.
* Resolves a SIP connection failure in the Skype client when the Skype server has TLS 1.0 or TLS 1.1 disabled.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4499162](https://support.microsoft.com/help/4499162)
</details>

<details>
<summary>April 25, 2019 - update for Team based on KB4493436*  (OS Build 15063.1784)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Resolves video and audio sync issue with some USB devices that are connected to the Surface Hub.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4493436](https://support.microsoft.com/help/4493436)
</details>

<details>
<summary>November 27, 2018 - update for Team based on KB4467699*  (OS Build 15063.1478)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Addresses an issue that prevents some users from Signing-In to “My Meetings and Files.”

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4467699](https://support.microsoft.com/help/4467699)
</details>

<details>
<summary>October 18, 2018 - update for Team based on KB4462939*  (OS Build 15063.1418)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Skype for Business fixes: 
  * Resolves Skype for Business connection issue when resuming from sleep
  * Resolves Skype for Business network connection issue, when device is connected to Internet
  * Resolves Skype for Business crash when searching for users from directory
* Resolves issue where the Hub mistakenly reports “No Internet connection” in enterprise proxy environments.
* Implemented a feature allowing customers to opt in to a new Whiteboard experience.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4462939](https://support.microsoft.com/help/4462939)
</details>

<details>
<summary>August 31, 2018 - update for Team based on KB4343889* (OS Build 15063.1292)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Adds support for Microsoft Teams
* Resolves task management issue with Intune registration
* Enables Administrators to disable Instant Messaging and Email services for the Hub
* Additional bug fixes and reliability improvements for the Surface Hub Skype for Business App

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4343889](https://support.microsoft.com/help/4343889)
</details>

<details>
<summary>June 21, 2018 - update for Team based on KB4284830* (OS Build 15063.1182)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Telemetry change in support of GDPR requirements in EMEA

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4284830](https://support.microsoft.com/help/4284830)
</details>

<details>
<summary>April 17, 2018 - update for Team based on KB4093117* (OS Build 15063.1058)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Resolves a wired projection issue
* Enables bulk update for certain MDM (Mobile Device Management) policies
* Resolves phone dialer issue with international calls
* Addresses image resolution issue when two Surface Hubs join the same meeting
* Resolves OMS (Operations Management Suite) certificate handling error
* Addresses a security issue when cleaning up at the end of a session
* Addresses Miracast issue, when Surface Hub is specified to channels 149 through 165
  * Channels 149 through 165 will continue to be unusable in Europe, Japan or Israel due to regional governmental regulations

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4093117](https://support.microsoft.com/help/4093117)
</details>

<details>
<summary>February 23, 2018 - update for Team based on KB4077528* (OS Build 15063.907)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Resolved an issue where MDM settings were not being correctly applied
* Improved Cleanup process

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4077528](https://support.microsoft.com/help/4077528)
</details>

<details>
<summary>January 16, 2018 - update for Team based on KB4057144* (OS Build 15063.877)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Adds ability to manage Start Menu tile layout via MDM
* MDM bug fix on password rotation configuration

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4057144](https://support.microsoft.com/help/4057144)
</details>

<details>
<summary>December 12, 2017 - update for Team based on KB4053580* (OS Build 15063.786)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Resolves camera video flashes (tearing or flickers) during Skype for Business calls
* Resolves Notification Center SSD ID issue

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4053580](https://support.microsoft.com/help/4053580)
</details>

<details>
<summary>November 14, 2017 - update for Team based on KB4048954* (OS Build 15063.726)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Feature update that allows customers to enable 802.1x wired network authentication using MDM policy.
* A feature update that enables users to dynamically select an application of their choice when opening a file.
* Fix that ensures that End Session cleanup fully removes all connections between the user’s account and the device.
* Performance fix that improves cleanup time as well as Miracast connection time.
* Introduces Easy Authentication utilization during ad-hoc meetings.
* Fix that ensures proxy settings configured on the device are used across all service components.
* Reduces and more thoroughly secures the telemetry transmitted by the device, reducing bandwidth utilization.
* Enables a feature allowing users to provide feedback to Microsoft after a meeting concludes.

Please refer to the [Surface Hub Admin guide](/surface-hub/) for enabling/disabling device features and services.
*[KB4048954](https://support.microsoft.com/help/4048954)
</details>

<details>
<summary>October 10, 2017 - update for Team based on KB4041676* (OS Build 15063.674)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Skype for Business
  * Resolves issue that required a device reboot when resuming from sleep.
  * Fixes issue where external contacts did not resolve through Skype Online Hub account.
* PowerPoint
  * Fixes problem where some PowerPoint presentations would not project on Hub.
* General
  * Fix to resolve issue where USB port could not be disabled by System Administrator.

*[KB4041676](https://support.microsoft.com/help/4041676)
</details>

<details>
<summary>September 12, 2017 - update for Team based on KB4038788* (OS Build 15063.605) </summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Security
  * Resolves issue with Bitlocker when device wakes from sleep.
* General
  * Reduces frequency/amount of device health telemetry, improving system performance.
  * Fixes issue that prevented device from collecting system logs.

*[KB4038788](https://support.microsoft.com/help/4038788)
</details>

<details>
<summary>August 1, 2017 - update for Team based on KB4032188* (OS Build 15063.498)</summary>

* Skype for Business 
  * Resolves Skype for Business Sign-In issue, which required retry or system reboot.
  * Resolves Skype for Business meeting time being incorrectly displayed.
  * Fixes to improve Surface Hub Skype for Business reliability.

*[KB4032188](https://support.microsoft.com/help/4032188)
</details>

<details>
<summary>June 27, 2017 - update for Team based on KB4022716* (OS Build 15063.442)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Address NVIDIA driver crashes that may necessitate sleeping 84” Surface Hub to power down, requiring a manual restart.
* Resolved an issue where some apps fail to launch on an 84” Surface Hub.

*[KB4022716](https://support.microsoft.com/help/4022716)
</details>

<details>
<summary>June 13, 2017 - update for Team based on KB4022725* (OS Build 15063.413)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* General
  * Resolved Pen ink dropping issues with pens
  * Resolved issue causing extended time to “cleanup” meeting

*[KB4022725](https://support.microsoft.com/help/4022725)
</details>

<details>
<summary>May 24, 2017 - update for Team based on KB4021573* (OS Build 15063.328)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* General
  * Resolved issue with proxy setting retention during update issue

*[KB4021573](https://support.microsoft.com/help/4021573)
</details>

<details>
<summary>May 9, 2017 - update for Team based on KB4016871* (OS Build 15063.296)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* General
  * Addressed sleep/wake cycle issue
  * Resolved several Reset and Recovery issues
  * Addressed Update History tab issue
  * Resolved Miracast service launch issue
* Apps
  * Fixed App package update error

*[KB4016871](https://support.microsoft.com/help/4016871)
</details>

<details>
<summary>Windows 10 Team Creators Update 1703 for Surface Hub - General Release notes (OS Build 15063.0)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Evolving the large screen experience 
  * Improved the meeting carousel in Welcome and Start
  * Join meetings and end the session directly from the Start menu
  * Apps can utilize more of the screen during a session
  * Simplified Skype controls
  * Improved mechanisms for providing feedback
* Access My Personal Content*
  * Personal single sign-on from Welcome or Start
  * Join meetings and end the session directly from the Start menu
  * Access personal files through OneDrive for Business directly from Start
  * Pre-populated attendee sign-in
  * Streamlined authentication flows with “Authenticator” app**
* Deployment & Manageability 
  * Simplified OOBE experience through bulk provisioning
  * Cloud-based device recovery service
  * Enterprise client certificate support
  * Improved proxy credential support
  * Added and /improved Skype Quality of Service (QoS) configuration support
  * Added ability to set default device volume in Settings
  * Improved MDM support for Surface Hub [settings](/surface-hub/remote-surface-hub-management)
* Improved Security 
  * Added ability to restrict USB drives to BitLocker only
  * Added ability to disable USB ports via MDM
  * Added ability to disable “Resume session” functionality on timeout
  * Addition of wired 802.1x support
* Audio and Projection
  * Dolby Audio “Human Speaker” enhancements
  * Reduced “pen tap” sounds when using Pen during Skype for Business calls
  * Added support for Miracast infrastructure connections
* Reliability and Performance fixes
  * Resolved several Reset and Recovery issues
  * Resolved Surface Hub Exchange authentication issue when utilizing client certificates
  * Improved Wi-Fi network connection and credentials stability
  * Fixed Miracast audio popping and sync issues during video playback
  * Included setting to disable auto connect behavior

*Single sign-in feature requires use of Office365 and OneDrive for Business
**Refer to Admin Guide for service requirements

</details>

## Windows 10 Team Anniversary Update (1607)

<details>
<summary>March 14th, 2017 - update for Team based on KB4013429* (OS Build 14393.953)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* General
  * Security fix for File Explorer to prevent navigation to restricted file locations
* Skype for Business
  * Fix to address latency during Remote Desktop based screen sharing

*[KB4013429](https://support.microsoft.com/help/4013429)
</details>

<details>
<summary>January 10th, 2017 - update for Team based on KB4000825* (OS Build 14393.693)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Enabled selection of 106/109 Keyboard Layouts for use with physical Japanese keyboards

*[KB4000825](https://support.microsoft.com/help/4000825)
</details>

<details>
<summary>December 13, 2016 - update for Team based on KB3206632* (OS Build 14393.576)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Resolves wired connection audio distortion issue

*[KB3206632](https://support.microsoft.com/help/3206632)
</details>

<details>
<summary>November 4, 2016 - update for Team based on KB3200970* (OS Build 14393.447)</summary>

This update to the Windows 10 Team Anniversary Update (version 1607) for Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Skype for Business bug fixes to improve reliability

*[KB3200970](https://support.microsoft.com/help/3200970)
</details>

<details>
<summary>October 25, 2016 - update for Team based on KB3197954* (OS Build 14393.351)</summary>

This update to the Surface Hub includes quality improvements and security fixes. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Enabling new Sleep feature in OS and Bios to reduce the Surface Hub’s power consumption and improve its long-term reliability
* General
  * Resolves scenarios where the on-screen keyboard would sometimes not appear
  * Resolves Whiteboard application shift that occasionally occurs when opening scheduled meeting
  * Resolves issue that prevented Admins from changing the local administrator password, after device has been reset
  * BIOS change to resolve an issue with status bar tracking during device reset
  * UEFI update to resolve powering down issues

*[KB3197954](https://support.microsoft.com/help/3197954)
</details>

<details>
<summary>October 11, 2016 - update for Team based on KB3194496* (OS Build 14393.222)</summary>

This update brings the Windows 10 Team Anniversary Update to Surface Hub and includes quality improvements and security fixes. (Your device will be running Windows 10 Version 1607 after it's installed.) Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Skype for Business
  * Performance improvements when joining meetings, including issues when joining a meeting using federated accounts
  * Video Based Screen Sharing (VBSS) support now available on Skype for Business for Surface Hub
  * Resolved disconnection after 5 minutes of idle time issue
  * Resolved Skype Hub-to-Hub screen sharing failure
  * Improvements to Skype video, including:
    * Loss of video during meeting with multiple video presenters
    * Video cropping during calls
    * Outgoing call video not displaying for other participants
  * Addressed issue with UPN sign-in error
  * Addressed issue with dial pad during use of Session Initiation Protocol (SIP) calls
* Whiteboard
  * User can now save and recall Whiteboard sessions using OneDrive online service (via Share functionality)
  * Improved launching Whiteboard when removing pen from dock
* Apps
  * Pre-installed OneDrive app, for access to your personal and work files
  * Pre-installed Photos app, to view photos and video
  * Pre-installed PowerBI app, to view dashboards
  * The Office apps – Word, Excel, PowerPoint – are all ink-enabled
  * Edge on Surface Hub now supports Flash-based websites
* General
  * Enabled Audio Device Selection (for Surface Hubs attached using external audio devices)
  * Enabled support for HDCP on DisplayPort output connector
  * System UI changes to settings for usability optimization (refer to [User and Admin Guides](https://www.microsoft.com/surface/support/surface-hub) for additional details)
  * Bug fixes and performance optimizations to speed up the Azure Active Directory sign-in flow
  * Reduced time needed to reset and restore a Surface Hub
  * Windows Defender UI has been added within settings
  * Improved UX touch to start
  * Enabled support for greater than 1080p wireless projection via Miracast, on supported devices
  * Resolved “There’s no internet connection” and “Appointments may be out of date” false notification states from launch
  * Improved reliability of on-screen keyboard
  * Additional support for creating Surface Hub provisioning packages using Windows Imaging & Configuration Designer (ICD) and improved Surface Hub monitoring solution on Operations Management Suite (OMS)

*[KB3194496](https://support.microsoft.com/help/3194496)
</details>

## Updates for Windows 10 Version 1511

<details>
<summary>July 12, 2016 - update for Team based on KB3172985* (OS Build 10586.494)</summary>

This update includes quality improvements and security fixes. No new operating system features are being introduced in this update.  Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Fixed issue that caused Windows system crashes
* Fixed issue that caused repeated Edge crashes
* Fixed issue causing pre-shutdown service crashes
* Fixed issue where some app data wasn’t properly removed after a session
* Updated Broadcom NFC driver to improve NFC performance
* Updated Marvell Wi-Fi driver to improve Miracast performance
* Updated Nvidia driver to fix a display bug in which 84" Surface Hub devices show dim or fuzzy content
* Numerous Skype for Business issues fixed, including: 
  * Issue that caused Skype for Business to disconnect during meetings
  * Issue in which users were unable to join meetings when the meeting organizer was on a federated configuration
  * Enabling Skype for Business application sharing
  * Issue that caused Skype application crashes
* Added a prompt in “Settings” to inform users that the OS can become corrupted if device reset is interrupted before completion

*[KB3172985](https://support.microsoft.com/help/3172985)
</details>

<details>
<summary>June 14, 2016 - update for Team based on KB3163018* (OS Build 10586.420)</summary>

This update to the Surface Hub includes quality improvements and security fixes. No new operating system features are being introduced in this update. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Constrained release. Refer to July 12, 2016 — [KB3172985](https://support.microsoft.com/en-us/help/3172985) (OS Build 10586.494) for Surface Hub specific package details

*[KB3163018](https://support.microsoft.com/help/3163018)
</details>

<details>
<summary>May 10, 2016 - update for Team based on KB3156421* (OS Build 10586.318)</summary>

This update to the Surface Hub includes quality improvements and security fixes. No new operating system features are being introduced in this update. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Fixed issue that prevented certain Store apps (OneDrive) from installing
* Fixed issue that caused touch input to stop responding in applications

*[KB3156421](https://support.microsoft.com/help/3156421)
</details>

<details>
<summary>April 12, 2016 - update for Team based on KB3147458* (OS Build 10586.218)</summary>

This update to the Surface Hub includes quality improvements and security fixes. No new operating system features are being introduced in this update. Key updates to Surface Hub, not already outlined in [Windows 10 Update History](https://support.microsoft.com/help/4018124/windows-10-update-history), include:

* Fixed issue where volume level wasn’t properly reset between sessions

*[KB3147458](https://support.microsoft.com/help/3147458)
</details>

## Related topics

* [Windows 10 release information](https://go.microsoft.com/fwlink/p/?LinkId=724328)
* [Windows 10 November update: FAQ](https://windows.microsoft.com/windows-10/windows-update-faq)
* [Microsoft Surface update history](https://go.microsoft.com/fwlink/p/?LinkId=724327)
* [Microsoft Lumia update history](https://go.microsoft.com/fwlink/p/?LinkId=785968)
* [Get Windows 10](https://go.microsoft.com/fwlink/p/?LinkId=616447)
