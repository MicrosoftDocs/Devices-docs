---
title: Troubleshoot Azure Sign-in Logs for Surface Hub
description: How to troubleshoot Surface Hub sign-in issues using the Azure sign-in logs.
ms.assetid: 8BB80FA3-D364-4A90-B72B-65F0F0FC1F0D
ms.reviewer: 
manager: peterdem
ms.prod: surface-hub
ms.sitesec: library
author: ryanbwold
ms.author: rwold
ms.topic: article
ms.date: 04/11/2023
ms.localizationpriority: medium
---

# Troubleshoot Azure Sign-in Logs for Surface Hub

## What are Azure sign-in logs? ##
Azure [sign-in logs](/azure/active-directory/reports-monitoring/concept-sign-ins) provide information on successful and failed sign-in attempts that occur within an Azure AD tenant. The Azure sign-in logs provide a detailed view of all sign-in activities for an account. When sign-in issues are encountered on the Surface Hub, an IT administrator can review these logs for any interrupts or failures. Here are some common reasons these logs are helpful to troubleshoot Surface Hub issues:

- Unable to add the device account to the Surface Hub
- Device account no longer syncs with Exchange Online
- Teams Rooms client fails to sign in
- Users unable to personally sign into the device
 
If you experience sign-in issues with the Surface Hub device account or personal user sign-in, follow the troubleshooting steps on this page.
 
## View sign-in logs ##
To access the Azure sign-in logs for a tenant, a user must have the necessary [role](/azure/active-directory/reports-monitoring/concept-all-sign-ins#how-do-you-access-the-sign-in-logs) assigned.

1. Sign in to the [Azure portal](https://portal.azure.com/)
2. Go to **Azure Active Directory** > **Users**
3. Locate or search for the account you're troubleshooting and select it.
4. Select **Sign-in logs**
5. If you see a banner to **Try out our new sign-in preview**, select it.

:::image type="content" source="images/review-azure-sign-in-logs.gif#lightbox" alt-text="GIF image showing how to review Azure sign-in logs.":::

>[!NOTE]
>The sign-in logs may take 5-10 minutes to propagate to Azure.

## Analyze sign-in logs ##
Scroll through the interactive and non-interactive sign-in logs and note the **Status** column. If any failures or interrupts are seen, select the sign-in for additional details. You can optionally [filter the sign-in logs](/azure/active-directory/reports-monitoring/concept-all-sign-ins#filter-the-results) by status to only show failures and interrupts.
 
:::image type="content" source="images/azure-sign-in-logs-2.png#lightbox" alt-text="Image showing detailed view of failed sign-in logs.":::

To analyze sign-in activity older than 24 hours, select the Date field to expand the timeframe.

:::image type="content" source="images/azure-sign-in-logs-3.png#lightbox" alt-text="Image showing how to expand date range of logs.":::

## Additional sign-in details ##
After you select the sign-in, the activity details pane shows the reason for the failure or interrupt. In this example, the failure is caused by multi-factor authentication (MFA), which the Surface Hub device account doesn't support.
 
:::image type="content" source="images/azure-sign-in-logs-4.png#lightbox" alt-text="Image showing log details for failed sign-in.":::

To reveal the policy that is enforcing MFA on the device account, select the Conditional Access tab.

:::image type="content" source="images/azure-sign-in-logs-5.png#lightbox" alt-text="Image showing Conditional Access details for failed sign-in":::

Follow the guidance on [Conditional Access for Surface Hub](conditional-access-for-surface-hub.md) to better understand the requirements for the device, and how to [exclude](conditional-access-for-surface-hub.md#exclude-device-account-from-unsupported-conditional-access-policies) the device account from unsupported policies.
 
Additional details on how to view and analyze the Azure sign-in logs can be found on the [Sign-in logs in Azure Active Directory](/azure/active-directory/reports-monitoring/concept-all-sign-ins) page.



