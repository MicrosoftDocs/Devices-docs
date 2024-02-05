---
title: Install Windows Bloom wallpaper on Surface Hub 3
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

You can use these instructions to install your own custom image. Note the following requirements: 

- Use the following dimensions: 3840 x 1080 pixels.
- Save your custom image with the same file name, listed above:**oembackgroundimage.png**
- Optionally, modify the SkypeSettings.xml sample, shown above, as needed. Depending on your image, you may need to adjust the **CustomThemeColor** values to match the primary color scheme of your custom wallpaper. The "RedComponent", "GreenComponent", and "BlueComponent" values specify the RGB color components of the theme color you wish to apply. You can customize these values to better complement or contrast with your wallpaper image for a cohesive look on your Surface Hub 3. For specific guidelines on choosing these values, consider using an RGB color picker based on your wallpaper's dominant color.










## Learn more

- [Get started with Surface Hub 3](surface-hub-3-get-started.md)
- [First-time setup for Surface Hub 3](first-run-program-surface-hub-3.md)
- [Manage settings with an XML configuration file](/microsoftteams/rooms/xml-config-file#manage-console-settings-with-an-xml-configuration-file)
