---
title: Install wallpaper on Surface Hub 3
description: Explains how admins can install the Windows Bloom background wallpaper on Surface Hub 3. 
ms.reviewer: dpandre
manager: frankbu
ms.service: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 02/05/2024
ms.localizationpriority: medium
appliesto:
- Surface Hub 3

---

# Install wallpaper on Surface Hub 3

This article explains how to replace the default Microsoft Teams Rooms wallpaper with the Windows Bloom wallpaper or a custom image. 

## Windows Bloom wallpaper

1. On a separate device, download the [Windows Bloom wallpaper](images/oembackgroundimage.png) and save it to a USB drive.
2. Copy the following XML into a text editor, name it **SkypeSettings.xml**, and save it to your USB drive.  

  ```xml
<SkypeSettings>
  <Theming>
       <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>OEMBackgroundImage.png</CustomThemeImageUrl>
       <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
       </CustomThemeColor>
  </Theming>
</SkypeSettings>

  ```

3. Insert the USB drive into the Surface Hub.
4. Connect an external keyboard and press the **Windows** key five times to open the Windows login screen and sign in with your admin credentials.
6. Save the wallpaper image file, **oembackgroundimage.png**, and **SkypeSettings.xml** in the following folder:

- **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**

7. Restart Surface Hub. The new wallpaper is displayed.

## Custom wallpaper

To create a custom wallpaper, see [IT Admins- Manage and create custom meeting backgrounds for Teams meetings](/MicrosoftTeams/custom-meeting-backgrounds). 






## Learn more

- [Get started with Surface Hub 3](surface-hub-3-get-started.md)
- [First-time setup for Surface Hub 3](first-run-program-surface-hub-3.md)
- [Manage settings with an XML configuration file](/microsoftteams/rooms/xml-config-file#manage-console-settings-with-an-xml-configuration-file)
