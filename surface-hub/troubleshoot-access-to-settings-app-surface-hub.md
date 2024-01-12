---
title: Troubleshoot access to Settings app on Surface Hub
description: If unable to access Settings on Surface Hub, try these troubleshooting steps.
manager: frankbu
ms.service: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: troubleshooting
ms.date: 01/09/2023
ms.localizationpriority: medium
---
# Troubleshoot access to Settings app on Surface Hub

To open the Settings app on Surface Hub, select **All apps** > **Settings**. Note that Ease of Access settings are available to anyone using Surface Hub. For all other settings, select **View as Admin** and log in with an Admin account. If you're unable to access settings after attempting to log in with your Admin account, review the troubleshooting guidance on this page, beginning with Device affiliation. 

## Device affiliation

Full access to the Settings app on Surface Hub depends on how you [initially affiliated Surface Hub during first run setup](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation) (aka OOBE) via one of the following options:

- [Microsoft Entra ID](#azure-active-directory-aad)
- [On-premises AD (Active Directory)](#on-premises-ad)
- [Local account administrator](#local-admin---no-device-affiliation)

<a name='azure-active-directory-aad'></a>

## Microsoft Entra ID

By default, when Surface Hub is joined to Microsoft Entra ID, only an account designated as a Global Administrator (GA) in your Azure tenant can access Settings. If unable to access Settings, check the following issues:

- Is the account a Global Admin account?
- Is the password expired? Try resetting the password.
- Is Surface Hub connected to the internet?
- Is Surface Hub behind a proxy or firewall that blocks access to Microsoft Entra ID?
- Did you or another admin configure [non-Global Admin policy](surface-hub-2s-nonglobal-admin.md) for Surface Hub? If yes, see the following section.

### Troubleshoot non-Global Admin policy

When joined to Microsoft Entra ID and auto-enrolled in Intune, you can configure non-Global Admin policy to allow other accounts to access Setting on Surface Hub. If non-Global Admin policy is enabled and users cannot access Settings, check the following issues:

#### Policy succeeds: Still no access to Settings

If Intune shows the non-Global Admin policy setting is successfully applied to Surface Hub:

- Is the account attempting to log in a member of the security group designated for this policy?
- Is the Surface Hub connected to the internet?
- If a GA account is being used, is it a member of the security group configured on the Surface Hub? GA accounts must also be added to this security group. Otherwise, if non-Global Admin policy is applied to Surface Hub, the GA can no longer access Settings.

#### Policy fails: Intune error

If Intune shows the non-Global Admin policy setting fails to reach Surface Hub:

- Is the security group for the accounts created in the cloud?
- Is the correct [Microsoft Entra group SID (security identifiers)](/surface-hub/surface-hub-2s-nonglobal-admin#obtain-azure-ad-group-sid-using-powershell) used in the XML?
- Is the [XML file created correctly](/surface-hub/surface-hub-2s-nonglobal-admin#create-xml-file-containing-azure-ad-group-sid)?
- Ensure the policy is assigned to Surface Hub device objects, not the device accounts. 

To learn more, see [Troubleshoot policies and configuration profiles in Microsoft Intune](/troubleshoot/mem/intune/device-configuration/troubleshoot-policies-in-microsoft-intune)

## On-premises AD

If the Surface Hub is domain joined and connected to on-prem AD, a security group in AD is specified during first-run setup to allow group members to sign into Settings. This designated group can be seen on Surface Hub within Settings > Surface Hub > Accounts. If an error message is received stating “this requires elevation” when attempting to log into Settings, check the following issues:

- Ensure the account being used is a member of the security group designated during OOBE.
- Ensure the account is enabled and the password has not expired.
 
> [!NOTE]
> If the Surface Hub loses trust with the domain and Settings can no longer be accessed, you will need to reset Surface Hub.

## Local admin - no device affiliation

If you choose to set up Surface Hub with a local admin (no device affiliation to Microsoft Entra ID or on-prem AD), the account created during first run setup is the only account that can access Settings. The local admin account is not backed by any directory service. If the credentials are forgotten or no longer working, you will need to reset Surface Hub.

> [!IMPORTANT]
> If the local admin account was created using a [provisioning package](provisioning-packages-for-surface-hub.md), the password must be reset every 42 days. Otherwise, the account may be locked out and unable to sign into Settings. If this occurs, you will need to reset Surface Hub.

## Learn more

- [Reset and recovery for Surface Hub 2S](surface-hub-recover-reset.md)
- [Reset and recovery for Surface Hub v1](device-reset-surface-hub.md)
