---
title: Change display language on Surface Hub
description: Once a Surface Hub admin installs other language packs, users can change the display language by selecting a new one from the available installed languages.
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: troubleshooting
ms.date: 03/21/2023
ms.localizationpriority: medium
---
# Change display language on Surface Hub

Surface Hub now allows end users to change the display language and preferred language, just like in other versions of Windows 10.

Once a Surface Hub admin installs extra languages, users can change the display language by selecting a new one from the available installed languages.

> [!NOTE]
> Only Surface Hub admins can install additional languages for end users. First, ensure that your Surface Hub has [KB5023773](https://support.microsoft.com/help/5023773)(or a subsequent Windows update) installed. To learn more about the latest Windows 10 Team updates, refer to [Surface Hub update history](surface-hub-update-history.md).

## End user language option

Users can change the display language on Surface Hub via a similar process used on desktop versions of Windows 10.

### Change the Display language

1. Select **Start > Settings > Time & Language**.
    :::image type="content" source="images/hub-user-change-language-settings.png" alt-text="Screenshot of Surface Hub settings." :::
2. Choose from the available languages as installed by your Surface Hub admin.
    :::image type="content" source="images/hub-user-change-display-language.png" alt-text="Screenshot that shows Windows Display language settings on Surface Hub." :::
3. Optional: For best results, also move the new language to the top of the **Preferred languages** list.
    :::image type="content" source="images/hub-user-change-preferred-language.png" alt-text="Screenshot that shows Preferred languages list on Surface Hub." :::
4. Restart Surface Hub.

> [!NOTE]
> The new language setting remains in effect for all future sessions unless changed by another user or an admin. Unlike other user-modified settings, the chosen language is not removed when a user selects **End session.**

## Admin-only settings

To enable users to change the display language on Surface Hub, admins must first install the desired languages and related options, such as keyboard settings.

### Modify language settings

1. Select **Start -> Settings -> Time & Language > View as Admin** and sign in with your admin credentials.
2. Install languages based on the users' geography, diversity, and preferences to enable an inclusive and seamless interaction with the device in the collaboration space.
3. Use the same procedure described in [Manage the input and display language settings in Windows](https://support.microsoft.com/windows/manage-the-input-and-display-language-settings-in-windows-12a10cb4-8626-9b77-0ccb-5013e0c7c7a2#WindowsVersion=Windows_10).

> [!NOTE]
> When end users change the display language, some screens that display admin-only info are not switched to the newly selected language.

> [!TIP]
> Admins can also install a keyboard layout for another language without switching the user interface. This may be useful for users who collaborate in English and communicate with colleagues in another language.

## Learn more

- [Manage the input and display language settings in Windows](https://support.microsoft.com/windows/manage-the-input-and-display-language-settings-in-windows-12a10cb4-8626-9b77-0ccb-5013e0c7c7a2#WindowsVersion=Windows_10)
- [Install Windows 10 Team 2022 Update](surface-hub-2022-update.md)
- [Surface Hub update history](surface-hub-update-history.md)
- [Adjust accessibility settings](accessibility-surface-hub.md)
