---
title: First-time setup for Surface Hub 3
description: Describes first run OOBE setup
ms.reviewer: 
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: chauncel
ms.topic: how-to
ms.date: 12/05/2023
ms.localizationpriority: medium
appliesto:
- Surface Hub 3
---

# First-time setup for Surface Hub 3

## Unboxing and hardware setup

Carefully unbox the Surface Hub 3 and set it up on its stand or mount it as per the instructions: 

- [Install and mount Surface Hub 50 inch](surface-hub-2s-install-mount.md)
- [Install and mount Surface Hub 85 inch](surface-hub-2s-85-install-mount.md)

Connect any peripherals that you will be using with the device, such as a keyboard or mouse, although these are not required for setup.

## Prerequisites

Before you start Surface Hub 3 for the first time, ensure that you have the following: 

- An account with admin privileges
- A resource account with a [supported Microsoft Teams Rooms license](s/microsoftteams/rooms/rooms-licensing)
 
> [!TIP]
> Review the [Microsoft Teams Rooms Deployment overview](/microsoftteams/rooms/rooms-deploy)

When you first start Surface Hub 3, the device automatically enters first-time Setup mode to guide you through account configuration and related settings.

## Use provisioning packages in enteprise environments

Although not required, you can automate the setup process with a provisioning package to ensure a consistent experience across multiple Surface Hubs. This optional technology allows for a streamlined setup process that can be performed without extensive IT intervention, saving time and resources in organizational and enterprise environments.

1. To begin, review the documentation in [Create provisioning packages](provisioning-packages-for-surface-hub.md) and save the provisioning package to a USB thumb drive.
2. Insert the USB thumb drive into one of the USB ports when you see the License Agreement page.
3. When prompted, choose the provisioning package you'd like to use.
4. Follow the rest of the steps, and remove the USB drive at the first reboot that occurs in the setup process.

## Surface Hub 3 OOB setup

Once the Surface Hub 3 is in place and connected to power, press the power button to start the device.

1. **Select your region.** Confirm the auto-detected region and select **Yes**.

    :::image type="content" source="images/hub-setup-region.png" alt-text="Select your region.":::

2. **Confirm keyboard layout.** Select **Yes**.

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="Confirm keyboard layout.":::

3. To add a second keyboard, select **Add layout**. Otherwise, select **Skip**.

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="Add a second keyboard.":::

4. **Connect to a network.** If you have already attached an Ethernet cable, Surface Hub 3 automatically connects to your network. Alternatively, you can connect to a wireless network. **Note:** You cannot connect to a wireless network in hotspots (captive portals) that redirect sign-in requests to a provider's website. Select **Next**.

    :::image type="content" source="images/hub-setup-network.png" alt-text="Connect to a network.":::

6. **Accept License Agreement.** Select **Accept**.

    :::image type="content" source="images/hub-setup-license.png" alt-text="Accept  License Agreement.":::

7. **Enter Device account info** using a UPN address (user@contoso.com) or a down-level domain address (CONTOSO\user). Use the format that matches your environment and enter the password.

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="Enter Device account info.":::

  | Environment                                              | Required format for device account |
  | -------------------------------------------------------- | ---------------------------------- |
  | Device account is hosted only online                     | username@contoso.com               |
  | Device account is hosted only on-premises                | CONTOSO\user                       |
  | Device account is hosted online and on-premises (hybrid) | CONTOSO\user                       |

  > [!NOTE]
  > Although you can skip setting up a device account, the device will not be fully integrated into your infrastructure. If you skip setting it up now, you can add a device account using the Settings app later.

8. **Enter your password** and select **Next**.

9. Surface Hub 3 automatically detects Exchange server and SIP address info from the domain entered in the previous step. Or, if needed, provide your Exchange server address and select **Next**.

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange server and SIP address.":::

10. **Name this device.** Enter a name for your device or use the suggested one. **Select Next**.

    :::image type="content" source="images/hub-setup-name.png" alt-text="Name this device.":::

   - The **Friendly name** is visible on the bottom left corner of Surface Hub 3.
   - The **Device name** identifies the device when affiliated with Active Directory or Microsoft Entra ID and when enrolling the device with Intune.

   > [!IMPORTANT]
   > If you plan to affiliate the Surface Hub with Active Directory, the device name must meet the [standard requirements for computer names in AD](/troubleshoot/windows-server/identity/naming-conventions-for-computer-domain-site-ou#computer-names).Otherwise the setup will fail.

### Configure device admin accounts

You can set up device admins during first-time Setup or later if needed. For more information, refer to:

- [Surface Hub device affiliation](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [Admin Group Management](admin-group-management-for-surface-hub.md)

1. **Choose the type of admin account.** Select one of the following options: Active Directory Domain Services, Microsoft Entra ID, or Local admin.

    :::image type="content" source="images/hub-setup-join.png" alt-text="Choose type of admin account.":::

### Active Directory Domain Services

1. If you intend to use Surface Hub 3 in an on-premises environment, you can affiliate Hub with **Active Directory Domain Services**.  Enter the credentials of a user with permissions to join the device to Active Directory.
2. Select the Active Directory Security Group containing members allowed to sign in to the Settings app on Surface Hub 3.
3. Select **Finish**. The device will restart.

<a name='microsoft-azure-active-directory'></a>

### Microsoft Entra ID

1. If you intend to manage Surface Hub 3 from the cloud using Microsoft Intune or an MDM provider, select **Microsoft Entra ID**.
2. Select Next and sign in with a work or school account. If redirected, authenticate using your organization’s sign-in page and provide additional credentials if requested. Otherwise, enter your password and select **Next.**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="The screenshot shows the dialog to sign in with a work or school account.":::

> [!TIP]
> To configure who can use the Settings app to manage Surface Hubs, ensure that automatic Intune enrollment is enabled in your tenant before joining the device to Microsoft Entra ID. Intune policies can then be used to [configure non-Global admins](surface-hub-2s-nonglobal-admin.md) on Surface Hubs.

### Local Administrator account

- Enter a username and a memorable password for your local admin. (If you forget the local admin password, you will need to [recover your device](surface-hub-2s-recover-reset.md) and repeat the setup process.)  

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="This screenshot shows the field to enter a memorable password for local admin account.":::

### Choose privacy settings for your device

- Select from the available privacy settings and select **Accept.**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="This screenshot shows the dialog to choose privacy settings.":::

### Use provisioning packages

You can customize first-time setup options to ensure a consistent experience across multiple Surface Hubs.

1. To begin, review the documentation in [Create provisioning packages](provisioning-packages-for-surface-hub.md) and save the provisioning package to a USB thumb drive.
2. Insert the USB thumb drive into one of the USB ports when you see the License Agreement page (step 6 in the ["Get started"](#get-started) steps above).
3. When prompted, choose the provisioning package you'd like to use.
4. Follow the rest of the steps, and remove the USB drive at the first reboot that occurs in the setup process.

## Learn more

- [Prepare your environment for Surface Hub](prepare-your-environment-for-surface-hub.md)
- [Surface Hub and Microsoft Teams Rooms automated setup guide](https://go.microsoft.com/fwlink/?linkid=2221605)


## Learn more

