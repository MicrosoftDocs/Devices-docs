---
title: Install Progressive Web Apps on Surface Hub
description: Explains how admins can install Progressive Web Apps (PWAs) on Surface Hub via Intune or a provisioning package. 
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

Admins can remotely install [Progressive Web Apps (PWAs)](/microsoft-edge/progressive-web-apps-chromium/) on Surface Hubs by using either a mobile device management provider (MDM) such as Microsoft Intune or a provisioning pack. PWAs function like installed native apps on supported platforms and function like regular websites on other browsers. When admins install PWAs on Surface Hub, users can run them directly from the App menu.

> [!IMPORTANT]
> Before you install PWAs, ensure that your Surface Hub has [KB5011543](https://support.microsoft.com/help/5011543) (or a subsequent Windows update) installed. To learn more about the latest Windows 10 Team updates, refer to [Surface Hub update history](surface-hub-update-history.md).

- [Install PWAs on Surface Hub via Intune](#install-pwas-via-intune)
- [Install PWAs on Surface Hub via provisioning package](#install-pwas-via-provisioning-package)

Users can also install PWAs for use during their Hub session. When the session ends, PWAs are removed. To learn more, see [Install, manage, or uninstall apps in Microsoft Edge](https://support.microsoft.com/topic/install-manage-or-uninstall-apps-in-microsoft-edge-0c156575-a94a-45e4-a54f-3a84846f6113)

## Install PWAs via Intune

Use Intune or another MDM provider to install PWAs on Surface Hubs. To learn more, refer to [Manage settings with an MDM provider](manage-settings-with-mdm-for-surface-hub.md).

### Get started

1. Sign in to the Intune portal at  [**Microsoft Endpoint Manager admin center**](https://endpoint.microsoft.com/).
2. Go  to **Devices** > **Configuration** **Policies** > **Create profile**.
3. Under Platform, select **Windows 10 and later**. Under Profile type, select **Templates**. Under Template name, select **Administrative Templates.**
4. Select **Create.**

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="Create Intune Configuration profile" :::

5. Name the profile, enter an optional description, and select **Next**.

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="Name profile" :::

### Configure force-installed Web Apps policy (Intune)

1. Under **All Settings** > **Computer Configuration**,  select **Microsoft Edge** and in the Search box, enter **force-installed**, select **force-installed Web Apps**, and then select **Enabled**.

    :::image type="content" source="images/pwa-enable-force-install.png" alt-text="Enable force-installed Web apps" :::

2. Under **URLs for Web Apps to be silently installed**, copy and enter the following code snippet to install PWAs for YouTube, Webex, Zoom, and Uber. Or skip to the next step to install other PWAs.

    :::image type="content" source="images/hub-pwa-install-enable.png" alt-text="Enter list of force-installed Web apps" :::

    ```json
    [
    { "url": "https://www.youtube.com/",       "default_launch_container": "window" },
    { "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
    { "url": "https://zoom.us/join",           "default_launch_container": "window" },
    { "url": "https://www.uber.com/",          "default_launch_container": "tab"}
    ]
    ```

3. Alternatively, you can create a JSON snippet from the following syntax to install other PWAs.

    ```json
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  }, ]
    ```

4. On the Scope tags page, select **Next** to skip.
5. On the Assignments page, under **Included groups**, select **Add groups**.

    :::image type="content" source="images/pwa-add-groups.png" alt-text="Add groups" :::

6. Under **Select groups to include**, enter the name of a group containing the Surface Hubs you wish to target, choose **Select**, and then click **Next**. To learn more about assigning a Configuration profile to a group, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).

    :::image type="content" source="images/pwa-select-groups.png" alt-text="Select groups" :::

7. Review and then select **Create**.

    :::image type="content" source="images/pwa-create-profile.png" alt-text="Create profile" :::

    > [!TIP]
    > To apply the Configuration profile immmediately, select **Devices** > **All devices** and find the device you targeted. Open its Overview pane, and select **Sync**.

8. On Surface Hub, launch Edge. PWAs are installed and appear in the Start menu All apps list.

## Install PWAs via provisioning package

You can install PWAs by applying a provisioning package to Surface Hubs using a USB drive. To learn more refer to [Create provisioning packages](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard).

### Get started with provisioning

1. On a separate PC running Windows 10 or Windows 11, install [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) (WCD) from the Microsoft Store.
2. In WCD, create a new Project. Select **Provision Desktop Devices,** provide a name for the project and choose **Finish.**
3. Select **Switch to advanced editor** and select **Yes** to confirm.

### Configure MSEdgePolicy

1. In the Available customizations pane in WCD, go to **\Runtime Settings\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**
2. In the customizations edit pane, enter the app name as **MSEdgePolicy** and select **Add**.

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="Enter app name as MSEdgePolicy" :::

3. In the Available customizations pane, select **AppName: MSEdgePolicy** and in the edit pane, change **SettingType** to **Policy** and choose **Add**.
4. In the Available customizations pane, select **SettingType: Policy** and in the edit pane, set **AdmxFileUid** to **MSEdgePolicy,** and choose **Add**.
5. In the Available customizations pane, select **AdmxFileUid: MSEdgePolicy** and in the edit pane, set **MSEdgePolicy** by entering the following code as a single line of text:

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="Enter code for MSEdgePolicy" :::

    ```xml
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```

### Configure force-installed Web Apps policy (provisioning package)

1. In the Available customizations pane in WCD, go to: **\Runtime Settings\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**
2. In the customizations edit pane, enter the Areaname as **MSEdgePolicy~Policy~microsoft_edge,** select **Add**.
3. In the Available customizations pane, select **AreaName: MSEdgePolicy~Policy~microsoft_edge** and in the edit pane, set **Policy Name** to **WebAppInstallForceList** and select **Add**.
4. In the Available customizations pane, select **PolicyName: WebAppInstallForceList** and in the edit pane for **WebAppInstallForceList** enter the following code as a single line of text.

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="Enter code for force-installed Web Apps policy" :::

    > [!TIP]
    > This example installs YouTube as a PWA. Replace the URL as appropriate.

```xml
    <enabled/><data id="WebAppInstallForceList" value="[{"url": "https://www.youtube.com", "create_desktop_shortcut": true, "default_launch_container": "window"}]"/>
```

### Export provisioning package and apply to Surface Hubs

1. In the menu bar, select **Export**, select **Provisioning Package** and follow the prompts to generate the .ppkg file.
2. Insert an empty USB flash drive. Select output location to go to the location of the package. Copy the .ppkg file to the USB drive.
3. Apply the provisioning package via the Settings app or during first-run setup. To learn more, see [Create provisioning packages](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

## Learn more

- [WCD reference: ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [Overview of Progressive Web Apps (PWAs)](/microsoft-edge/progressive-web-apps-chromium/)
