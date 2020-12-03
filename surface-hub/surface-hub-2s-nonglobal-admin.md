---
title: "Configure non Global admin accounts on Surface Hub 2S"
description: "This article describes how to configure non Global Admin accounts to manage Surface Hub 2S."
keywords: Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/03/2020
ms.localizationpriority: Medium
---

# Configure non Global admin accounts on Surface Hub 2S

When you join Surface Hub 2S to an Azure AD domain, you can configure non Global Admin accounts that limit permissions to the Settings app. 

By default, the admin account for an AAD-joined Hub is set as Global Admin, which also grants admin rights across an entire corporate tenant. 

Before you begin, make sure your Surface Hub is joined to Azure Active Directory. If not, you will need to run OOBE setup and choose the option to join Azure AD. 

## Summary 

The process of creating non Global admin accounts involves the following steps: 

1. In Microsoft Endpoint Manager (aka Intune), create a security group containing the desired user accounts as members of the group.
2. Obtain Azure AD Group SID using PowerShell.
3. Create XML file containing Azure AD Group SID.
4. In Endpoint Manager, create a custom configuration profile targeting your security group.


## Create Azure AD security group 

1. In Endpoint Manager, click Groups > Create Group > enter a name (for example, Surface Hub Local Admins), add the target admin accounts (the user accounts of the persons designated to manage Surface Hub), and then click Create. 

## Obtain Azure AD Group SID using PowerShell

1. Launch PowerShell with elevated account privileges (**Run as Administrator**). 
2. [Install Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) and install the PowerShell module. 
3. Sign into your Azure AD tenant
 ...
Connect-AzAccount
  ...
4. When you're signed into your tenant, run the following commandlet:
...
  - function Convert-ObjectIdToSid
{    param([String] $ObjectId)   
     $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
	 
}
...
5. The commandlet returns the following instruction:
- "Please type the Object ID of your Azure AD Group."
- In Endpoint Manager, select the group you created earlier and copy the Object ID, as shown in the figure below. 
- Add image
6. Paste the Object ID into the PowerShell commandlet and press Enter. 
7. The commandlet returns the Azure AD Group SID. 

## Create XML file containing Azure AD Group SID

1. Copy the following into a text editor. Replace the placeholder SID with your Azure AD Group SID obtained in the previous step. 

...
      <groupmembership>   
	  <accessgroup desc = "Administrators">        
	  <member name = "Administrator" />        
	  <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
	  </accessgroup>
	  </groupmembership>
  ...

2. Save the file as XML. 

## Create a custom configuration profile

1. In Endpoint Manager, click **Devices** > **Configuration profiles** > **Create profile** 
2. Under platform choose  **Windows 10 and later.** Under Profile, choose **Custom**, and then click **Create.**
3. Add a name and description and then click **Next.**
4. Under **Configuration settings** > **OMA-URI Settings** click **Add**.
5. In the Add Row pane, add a name and under OMA-URI, add **./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership**.
6. Under Data type, select **String XML** and browse to open the XML file you created in the previous step. 
- add image
7. Click Save.
8. Click **Select groups to include** and choose the group you created earlier. Click **Next.**
- Under Applicability rules, add a Rule if desired. Otherwise, click **Next** and then click **Create**.
- 

## Non Global admins managing Surface Hub

The user accounts added to **Surface Hub Local Admins** are ready to use. 
