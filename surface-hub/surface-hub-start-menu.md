---
title: Configure Surface Hub Start menu
description: Modify the Surface Hub Start menu with custom tiles to include specific apps such as Progressive Web Apps. 
ms.prod: surface-hub
ms.sitesec: library
author: coveminer
ms.author: dpandre
ms.topic: article
ms.date: 05/06/2022
ms.reviewer: dpandre
manager: laurawi
ms.localizationpriority: medium
---

# Configure Surface Hub Start menu

Surface Hub ships with a default Start menu that admins can modify with specific apps to meet organizational requirements. For example, you can [install Progressive Web Apps](install-pwa-surface-hub.md) and include them in the Start menu for quick user access at the start of every Hub session.

## Overview

The Surface Hub Start menu is rendered from a [Start layout XML file](#default-surface-hub-start-menu) that includes App ID values (AppUserModelID) for default applications such as Microsoft PowerPoint, Word, and Excel. You can add new tiles or replace the default values with the AppUserModelID associated with the apps you wish to display. [As described below](#deploy-customized-start-menu-to-surface-hub), use a mobile device management (MDM) provider such as Microsoft Intune to deploy a Start layout device policy containing the modified Start layout XML.

### Differences between Surface Hub and desktop Start menu

There are a few key differences between Start menu customization for Surface Hub and a Windows 10 desktop:

- You cannot use the Start layout XML to configure the taskbar or the Welcome screen for Surface Hub.
- The Start layout policy should be assigned only to devices, not users.
- The OMA-URI setting to use in the policy is `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- `SecondaryTile`, used for links, will open the link in Microsoft Edge.
- **[DesktopApplicationTile](/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile)** is only supported for Edge and Microsoft Teams. All other Win32 apps are blocked by Code Integrity policy

## Default Surface Hub Start menu

  :::image type="content" source="images/figa-default-surface-hub-start-menu.png" alt-text="Default Surface Hub Start menu":::

The default Start menu is rendered by the following Start XML layout.

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:DesktopApplicationTile
            DesktopApplicationID="MSEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

### Modify default Start menu

Customize the Start menu by modifying the XML that renders tiles displaying the various apps. Surface Hub supports a maximum of 12 tiles.

This example adds the following [Progressive Web Apps](install-pwa-surface-hub.md) to the default XML layout. See [Appendix A](#appendix-a-surface-hub-start-menu-modified-for-progressive-web-apps) for the modified Start layout XML file containing these PWAs.

| **App** | **AppUserModelID**                          |
| ------- | ------------------------------------------- |
| WebEx   | signin.webex.com-8846C236_2aab1d9x9fqba!App |
| Zoom    | zoom.us-F576B427_j0dtdqw38r40m!App          |
| YouTube | www.youtube.com-756BE99A_pd8mbgmqs65xy!App  |

> [!TIP]
> See [Appendix B](#appendix-b-extract-appusermodelids-from-installed-apps) for instructions on obtaining the AppUserModelID for other apps installed on Surface Hub.

## Deploy customized Start menu to Surface Hub

1. Save your [modified Start menu XML](#appendix-a-surface-hub-start-menu-modified-for-progressive-web-apps) to a separate PC.
2. Sign in to the Intune portal at [**Microsoft Endpoint Manager admin center**](https://endpoint.microsoft.com/).
3. Go to **Devices** > **Configuration** **Policies** > **Create profile**.
4. Under Platform, select **Windows 10 and later**. Under Profile type, select **Templates**. Under Template name, select **Custom** and choose **Create**.

    :::image type="content" source="images/fig1-start-custom-profile.png" alt-text="Start creating the custom Configuration profile":::

5. Name the profile, enter an optional description, and select **Next**.

    :::image type="content" source="images/fig2-name-custom-profile.png" alt-text="Name custom Configuration profile":::

6. On the configuration settings page, select **Add.** Enter a name and optional description.
7. For OMA-URI, enter the following string:

```xml
./Device/Vendor/MSFT/Policy/Config/Start/StartLayout
```

  :::image type="content" source="images/fig3-add-uri-string.png" alt-text="Add OMA-URI string":::

8. For Data type, select **String (XML file) and** open your modified Start layout XML file. Select **Save** and then click **Next**.

    :::image type="content" source="images/fig4-upload-modified-xml.png" alt-text="Upload modified Start layout XML file":::

### Assign Start layout policy

The Configuration profile **must** be assigned to devices and targeted to the device URI. Do not use: ./User/Vendor/MSFT/Policy/Config/Start/StartLayout.  
  
1. On the Assignments page, under **Included groups**, select **Add groups**.
2. Under **Select groups to include**, enter the name of a group containing the Surface Hubs you wish to target, choose **Select**, and then click **Next**. To learn more about assigning a Configuration profile to a group, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).

    :::image type="content" source="images/fig5-selectgroup.png" alt-text="Select group containing targeted Surface Hubs]":::

3. On the Applicability Rules page, enter optional criteria if desired. Otherwise, select **Next**.
4. Review the Configuration profile and select **Create**.

    :::image type="content" source="images/fig6-create-custom-profile.png" alt-text="Finish creating Custom configuration profile":::

5. To apply the Configuration profile immediately, select **Devices** > **All devices** and find the Surface Hub you targeted. Open its Overview pane, and select **Sync**.

    :::image type="content" source="images/pwa-sync-tenant.png" alt-text="Sync targeted Surface Hub":::

6. Once applied, you will see the customized Start menu on your Surface Hub.

    :::image type="content" source="images/figb-modified-start-menu.png" alt-text="Modified Surface Hub Start menu with PWAs":::

## Appendix A: Surface Hub Start menu modified for Progressive Web Apps

The following modified Start layout XML includes [PWAs](install-pwa-surface-hub.md) for WebEx, Zoom, and YouTube.

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:DesktopApplicationTile
            DesktopApplicationID="MSEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        <start:Tile
            AppUserModelID="signin.webex.com-8846C236_2aab1d9x9fqba!App"
            Size="2x2"
            Row="6"
            Column="0"/>
        <start:Tile 
            AppUserModelID="zoom.us-F576B427_j0dtdqw38r40m!App"
            Size="2x2" 
            Row="6"
            Column="2"/>
        <start:Tile
            AppUserModelID="www.youtube.com-756BE99A_pd8mbgmqs65xy!App"
            Size="2x2"
            Row="6"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

## Appendix B: Extract AppUserModelIDs from installed apps

To obtain the AppUserModelID of apps installed on Surface Hub:

1. Sign in to Surface Hub as an admin, open **Settings**, and select **Update & Security**.
2. Select Logs. Insert a USB drive, then select **Collect logs.**
3. On a separate PC, open the USB drive and unzip the Log folder.
4. In the Registry folder, open **HKLM_SOFTWARE_Microsoft.txt**.
5. Search for the **ApplicationUserModelId** associated with the app you want to include in the Start menu.

  ![Locate the app ID in the Hub registry](images/fig8-locate-appid-in-hub-registry.png)
