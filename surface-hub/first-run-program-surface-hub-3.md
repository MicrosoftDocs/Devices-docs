---
title: First-time setup for Surface Hub 3
description: Describes first run OOBE setup
ms.reviewer: 
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 12/04/2023
ms.localizationpriority: medium
appliesto:
- Surface Hub 3
---
# First-time setup for Surface Hub 3

## Unboxing and hardware setup

Carefully unbox the Surface Hub 3 and set it up on its stand or mount it as per the instructions:

- [Install and mount Surface Hub 50 inch](surface-hub-install-mount.md)
- [Install and mount Surface Hub 85 inch](surface-hub-3-85-install-mount.md)

Connect any peripherals you will use with the device, such as a keyboard or mouse, although these are not required for setup.

## Prerequisites

Before you start Surface Hub 3 for the first time, ensure that you have the following:

- An account with admin privileges
- A resource account with a [supported Microsoft Teams Rooms license](/microsoftteams/rooms/rooms-licensing)

> [!TIP]
> For general guidance about Microsoft Teams Rooms on Windows, review the [Microsoft Teams Rooms Deployment overview](/microsoftteams/rooms/rooms-deploy)

When you first start Surface Hub 3, the device automatically enters first-time Setup mode to guide you through account configuration and related settings.

## Use provisioning packages in Enterprise environments

Although not required, you can automate the setup process with a provisioning package to ensure a consistent experience across multiple Surface Hubs. This optional technology allows for a streamlined setup process that can be performed without extensive IT intervention, saving time and resources in organizational and enterprise environments.

1. Review the documentation in [Create provisioning packages](provisioning-packages-for-surface-hub.md) and save the package to a USB thumb drive.
2. Insert the USB thumb drive into one of the USB ports when you see the License Agreement page.
3. When prompted, choose the provisioning package you want.
4. Follow the rest of the steps, and remove the USB drive at the first reboot that occurs in the setup process.

## Surface Hub 3 OOBE setup

> [!TIP]
> When you run first-time setup, ensure you stay connected to automatically download required updates to enable the current user experience.

1. Press the power button to start the device.

   ![Screenshot of Surface Hub 3 startup.](images/surface-hub-3-oobe-fig1.png)

2. Connect to a network.

   ![Screenshot of Connect to a network.](images/surface-hub-3-oobe-fig1-0.png)

   > [!TIP]
   > If you have already attached an Ethernet cable, Surface Hub 3 automatically connects to your network. Alternatively, you can connect to a wireless network.

   > [!NOTE]
   > You cannot connect to a wireless network in hotspots (captive portals) that redirect sign-in requests to a provider's website.

3. **Select your region.** Confirm the auto-detected region and select **Yes**.

   ![Screenshot of Select your region.](images/surface-hub-3-oobe-fig1a.png)

4. **Confirm keyboard layout.** Select **Yes**.

   ![Screenshot of Confirm keyboard layout.](images/surface-hub-3-oobe-fig1b.png)

5. To add a second keyboard, select **Add layout**. Otherwise, select **Skip**.

   ![Screenshot of Add a second keyboard.](images/surface-hub-3-oobe-fig1c.png)

## Microsoft Teams Rooms setup

Now, you're ready to begin the Microsoft Teams Rooms setup experience.

1. Agree to Microsoft Software License Terms and acknowledge that you have read the privacy statement at [https://aka.ms/privacy](https://aka.ms/privacy). Select **Accept**.
3. Turn off Cortana Voice Activation, if desired. Select **Continue**.
2. If you received a verification code, enter it and select **Continue.** Otherwise, select **Manual setup** and enter your account and password.
4. Select **Finish** to complete the Microsoft Teams Rooms setup.

## Next steps

- Although the OOBE process automatically downloads required updates, running Windows Update is recommended to ensure you have the latest. Sign in to Surface Hub 3 with an admin account, and open **Settings > Windows Update > Check for Updates**.
- Review [Surface Hub 3 security best practices](surface-hub-3-security.md). At a minimum, recommendations include changing the Administrator password, adding a UEFI password, and implementing appropriate physical security measures.
- Optionally, you may need to [update Surface Hub Pen firmware](surface-hub-pen-firmware.md)
