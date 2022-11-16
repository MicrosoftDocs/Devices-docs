---
title: "Known issues: Windows 10 Team"
description: "This page provides a list of known issues for Surface Hubs"
keywords: separate values with commas
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/09/2021
ms.localizationpriority: Medium
---
# Known issues: Windows 10 Team

This article lists known issues for Surface Hubs running the current operating system, Windows 10 Team Edition version 22H2.

To ensure Surface Hub receives the latest updates, sign in with an Admin account and select **All apps** > **Settings** > **Update and Security** > **Windows Update**, and then install all updates.

| Issue               | Description           | Remedy                 |
|---------------------|-----------------------|------------------------|
| Adding a device account with an Exchange Online mailbox may fail during the [first-run experience](first-run-program-surface-hub.md). | Exchange Online began disabling basic authentication for all protocols as of October 1st, 2022.<br> <br>Windows 10 Team edition does fully support modern authentication, but only as of [KB5010415](https://support.microsoft.com/help/5010415) (or a subsequent Windows CU). | One of the following options can be used to address this scenario:<br>- Download the latest [Hub 2S recovery image](https://aka.ms/SRI) and follow the [USB recovery steps](surface-hub-2s-recover-reset.md#recover-surface-hub-2s-by-using-a-usb-recovery-drive) to update your Surface Hub and go through the first-run experience again.<br>- Skip setting up a device account in the first-run process, install all Windows Updates afterwards, and then add the account from **Settings** > **Surface Hub** > **Accounts**.<br>- Follow the [one-time basic auth re-enablement steps](https://aka.ms/EXOBasicAuthLatest) for the Exchange Web Services (EWS) protocol. |
| Use of the [Surface Hub password rotation feature](password-management-for-surface-hub-device-accounts.md) may not work as expected in some scenarios. | Surface Hubs may fail to rotate passwords for Azure AD-based device accounts. If the device account password expires, the Surface Hub would not be able to sync its calendar or join Teams meetings. | Microsoft is aware of and is actively investigating this issue. Microsoft will provide additional information regarding a resolution as quickly as possible.<br> <br>As a workaround, password expiry for impacted accounts could be disabled or extended. |
| Use of some [SurfaceHub CSP policies](/mem/intune/configuration/device-restrictions-windows-10-teams#apps-and-experience) will fail after KB5004198 (Teams Admin Center agent) has been installed. | Using **DefaultVolume**, **AllowSessionResume**, **DisableSigninSuggestions**, or **DoNotShowMyMeetingsAndFiles** properties in the [SurfaceHub CSP](https://learn.microsoft.com/en-us/windows/client-management/mdm/surfacehub-csp) in an MDM policy or provisioning package will fail with error 0x86000023 due to the policy nodes being locked by the TAC agent. | Microsoft is actively looking to find a resolution to this issue. |
| Some Surface Hubs are restarting when a user selects 'End Session'.  | When Surface Hub device users select the 'End Session' functionality to clear user data, the Surface Hub device may erroneously detect a cleanup failure, forcing a restart of Windows to ensure clean up occurs successfully.  | Microsoft is aware of and is actively investigating this issue.  Microsoft will provide additional information regarding a resolution as quickly as possible.|
| Authentication of hybrid device accounts with on-premises mailboxes fails. | Surface Hub devices default to using Modern Authentication for accounts that exist in Azure AD, even if they have mailboxes in on-premises Exchange environments that don't have [Hybrid Modern Authentication](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) enabled. In this scenario, the account authentication fails. As a result, it may not be possible to add a new device account or sync an existing one. | After [KB4598291](https://support.microsoft.com/help/4598291) (or a subsequent Windows CU) is installed, the [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp) has a new ExchangeModernAuthEnabled parameter available to toggle the use of Modern Authentication. This can be set to false via MDM policy or [provisioning package](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/ExchangeModernAuthDisabled.ppkg) to prevent the Hub from using Modern Authentication. |
| Hub 2S devices are unable to receive driver updates using WSUS. | Surface Hub 2S supports Windows Update and Windows Update for Business to distribute drivers; distribution via Windows Server Update Services (WSUS) is not supported. | If using WSUS, migrate to Windows Update for Business.<br> <br>**Learn more**: [What is Windows update for business?](/windows/deployment/update/waas-manage-updates-wufb) |
| Some ease-of-access settings persist after a session ends| When users turn on the High contrast toggle either from the Quick actions menu or from the Settings app, this toggle persists after the user session ends. Similarly, if users change the notifications display to indicate 7 seconds versus the admin-defined 5 seconds, it remains 7 seconds, even though other settings are reset to the admin-defined values. | Users can turn off the High Contrast toggle from the quick actions(caret) menu accessible on the Taskbar soon after launching a session on the Hub. Display duration of notifications can be set to a different value via the Settings app by the next user - this setting is accessible to all users. |
