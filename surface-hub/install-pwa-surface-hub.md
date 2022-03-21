---
title: Install Progressive Web Apps on Surface Hub
description: Explains how to install Progressive Web Apps (PWAs) on Surface Hub via Intune or a provisioning package. 
keywords: Surface Hub, PWAs, App
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/22/2022
ms.localizationpriority: medium
audience: ITPro
---

# Install Progressive Web Apps on Surface Hub

Admins can remotely install Progressive Web Apps (PWAs) on Surface Hubs via a mobile device management provider such as Microsoft Intune or a provisioning pack. PWAs function like installed native apps on supported platforms and function like regular websites on other browsers. When you install PWAs on Surface Hub, users can run them directly from the App menu.

To learn more, see [Overview of Progressive Web Apps (PWAs) - Microsoft Edge Development | Microsoft Docs](/microsoft-edge/progressive-web-apps-chromium/)

- [Install PWAs on Surface Hub via Intune](#install-pwas-via-intune)
- [Install PWAs on Surface Hub via provisioning package](#install-pwas-via-provisioning-package)

## Install PWAs via Intune

Use Intune or another MDM provider to install PWAs on Surface Hubs. To learn more, refer to [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md).

### Get started

1. Sign in to the Intune portal at  [**Microsoft Endpoint Manager admin center**](https://endpoint.microsoft.com/).
2. Go  to **Devices** > **Configuration** **Policies** > **Create profile** >
3. Under Platform, select Windows 10 and later. Under Profile **type,** select Templates**.** Under **Template name,** select **Administrative Templates.**
4. Select **Create.**
![Create profile](images/pwa-hubpwainstall.png)
5. Name the profile, enter an optional description, and select **Next**.
![Name profile](images/pwa-hubwebappscreateprofile.png)

### Configure force-installed Web Apps policy (Intune)

1. Select **Microsoft Edge Configuration** and in the Search box, enter **force-installed**, select **force-installed Web Apps**, and then select **Enabled**.
![Configure force-installed Web Apps](images/pwa-hubwebappscreateprofile.png)

2. Under **URLs for Web Apps to be silently installed**, use the following syntax:

> [!TIP]
> This example installs PWAs for YoutTube, Webex, Zoom, and Uber.

- Enter the code snippet containing URLs for the apps you want to install.

3. Enter optional Scope tags as appropriate and select **Next.**
4. Assign to users as appropriate.
5. Assign to a group containing the Surface Hubs you wish to target. To learn more, see [Add groups to organize users and devices - Microsoft Intune | Microsoft Docs](/mem/intune/fundamentals/groups-add)
6. Review and then select **Create**.
![Create profile](images/pwa-hubwebappscreateprofile.png)
7. Sync target devices as appropriate.
8. On Surface Hub, launch Edge. PWAs are installed and appear in the Start menu All apps list.

## Install PWAs via provisioning package

You can install PWAs by applying a provisioning package to target Surface Hubs using a USB drive. To learn more refer to [Create provisioning packages](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard).

### Get started with provisioning

1. On a separate PC running Windows 10 or Windows 11, install [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) (WCD) from the Microsoft Store.
2. In WCD, create a new Project. Select **Provision Desktop Devices,** provide a name for the project and choose **Finish.**
3. View all customizations: Select **Switch to advanced editor** and select **Yes** to confirm.

### Configure MSEdgePolicy

1. In the Available Customizations tree navigation pane, navigate to **\Runtime Settings\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**
2. In the customizations edit pane, enter the app name as **MSEdgePolicy** and select **Add**.
3. Select **AppName: MSEdgePolicy** in the Customizations Tree and in the Edit pane, change **SettingType** to **Policy** and choose **Add** again.
4. Select **SettingType: Policy** in the Customizations Tree and in the Edit pane, set **AdmxFileUid** to **MSEdgePolicy,** and choose **Add**.
5. Select **AdmxFileUid: MSEdgePolicy** in the Customizations Tree and in the Edit pane, set **MSEdgePolicy** by entering the following code as a single line of text:

### Configure force-installed Web Apps policy

1. Back in Customizations Tree, navigate to: **\Runtime Settings\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**
2. In the customizations edit pane, enter the Areaname as **MSEdgePolicy~Policy~microsoft_edge,** select **Add**.
3. Select **AreaName: MSEdgePolicy~Policy~microsoft_edge** in the Customizations Tree and in the Edit pane, set **Policy Name** to **WebAppInstallForceList** and select **Add**.
4. Select **PolicyName: WebAppInstallForceList** in the Customizations Tree and in the Edit pane, set **WebAppInstallForceList to** by entering the following code as a single line of text.

 > [!TIP:]
 > This example installs You Tube as a PWA.

### Export provisioning package and apply to Surface Hubs

1. In the menu bar, select **Export**, select **Provisioning Package** and follow the prompts to generate the .ppkg file.
2. Insert an empty USB flash drive. Select output location to go to the location of the package. Copy the .ppkg file to the USB drive.
3. Apply the provisioning package via the Settings app or during first-run setup. To learn more, see [Create provisioning packages](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)


## Learn more

- [WCD reference: ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
