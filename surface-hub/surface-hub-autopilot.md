---
title: "Deploy Surface Hub 3 with Windows Autopilot & Teams Rooms Autologin"
description: "This page provides a roadmap for deploying Surface Hub 3 using Windows Autopilot and Teams Rooms Autologin."
ms.service: surface-hub
author: coveminer
ms.author: chauncel
manager: frankbu
ms.topic: overview
ms.date: 03/26/2024
ms.localizationpriority: Medium
appliesto:
- Surface Hub 3
---

# Deploy Surface Hub 3 with Windows Autopilot & Teams Rooms Autologin

In the evolving landscape of digital workplaces, the efficiency of setting up and managing devices is paramount. Windows Autopilot represents a pivotal shift in how IT admins deploy Windows devices, offering a cloud-based solution that simplifies the entire process. This service eliminates the traditional complexities associated with device setup, enabling organizations to get their devices ready for productive use with minimal effort.

For the Surface Hub 3, Windows Autopilot brings a set of unique advantages. As a state-of-the-art collaborative device, the Surface Hub 3 requires a seamless integration into corporate environments to fully leverage its capabilities for enhancing teamwork. Windows Autopilot streamlines this integration, allowing IT professionals to pre-configure devices without ever needing to physically handle them. This not only saves valuable time but also ensures that each Surface Hub 3 is configured consistently and securely, adhering to organizational policies right out of the box.

The benefits of using Windows Autopilot for Surface Hub 3 extend beyond just simplification. It introduces a level of agility and flexibility in device management that is crucial for today's dynamic work environments. From automatically joining devices to Azure Active Directory (Azure AD) or Active Directory (via Hybrid Azure AD Join), to enrolling them in Microsoft Endpoint Manager (Intune), Autopilot sets the stage for a modern management approach. This ensures that Surface Hub 3 devices are always up to date, secure, and ready to facilitate seamless collaboration through features like Teams Rooms Autologin.
 
## Overview of Windows Autopilot for Surface Hub 3

Windows Autopilot represents a transformative approach to deploying and managing new devices in a corporate environment. It leverages cloud-based services to automate the setup and pre-configuration of Windows devices, streamlining their integration into the workplace. For organizations deploying the Surface Hub 3, Windows Autopilot introduces a seamless, efficient method to prepare these devices for immediate use, enhancing the collaborative capabilities of modern workspaces.

Surface Hub 3 benefits significantly from Windows Autopilot's capabilities. This service simplifies the often complex and time-consuming process of device setup, enabling IT adminis to configure settings, policies, and applications remotely. Through Autopilot, Surface Hub 3 devices can be made ready for productive use without manual intervention, ensuring a consistent and secure configuration that aligns with organizational requirements.

Key features of Windows Autopilot for Surface Hub 3 include:

- **Zero-touch deployment**: Devices can be shipped directly to their final destination and set up by the end-users themselves, without IT having to physically touch the device.
- **Profile-based configuration**: IT administrators can create and assign profiles that specify the desired configuration, policies, and applications for devices, ensuring that each Surface Hub 3 is configured according to its intended use case.
- **Automatic enrollment**: Surface Hub 3 devices are automatically enrolled in management tools such as Microsoft Endpoint Manager (Intune), enabling further management and configuration post-deployment.
- **Self-service deployment**: End-users are guided through a simplified setup process, reducing the need for IT support and allowing users to quickly start collaborating.

Utilizing Windows Autopilot for Surface Hub 3 deployment not only reduces the operational burden on IT departments but also accelerates the adoption of collaborative technology across the organization. By ensuring devices are configured correctly and securely from the start, teams can leverage the full potential of the Surface Hub 3 for seamless collaboration and communication.
In the following sections, we will delve into the specifics of setting up Teams Rooms Autologin through Windows Autopilot, showcasing how it further enhances the meeting room experience by providing quick, easy access to Teams collaboration tools on the Surface Hub 3.
 
## Preparing for Autopilot Deployment

Implementing Windows Autopilot for the deployment of Surface Hub 3 devices necessitates careful preparation to ensure a smooth and successful process. This preparation involves a series of steps that align with organizational requirements and Autopilot's capabilities. By meticulously planning and executing these preliminary tasks, IT professionals can leverage Autopilot's full potential, making the deployment of Surface Hub 3 both efficient and effective.

## Step 1: Verify Prerequisites

Before embarking on the Autopilot deployment journey, confirm that all prerequisites are met:

- **Azure Active Directory (Azure AD)**: Ensure that your organization uses Azure AD for identity management. Windows Autopilot relies on Azure AD for device management and authentication.
- **Microsoft Endpoint Manager (Intune)**: Integration with Intune or another Mobile Device Management (MDM) service is crucial for configuring and managing devices post-deployment.
- **Device compatibility**: Verify that your Surface Hub 3 devices are compatible with Windows Autopilot. They should run a supported version of Windows that meets Autopilot's requirements.

## Step 2: Gather device information

For Autopilot to recognize and manage Surface Hub 3 devices, specific device information must be collected and registered:

- **Hardware hash**: Collect the hardware hash, which uniquely identifies each device.
- **Serial number and Product ID**: Record these details for each device as they're required for registration with the Autopilot service.

This information can be obtained manually or, more efficiently, through cooperation with your Microsoft partner, who can pre-register these details with Microsoft on your behalf.

## Step 3: Register Devices with Autopilot

Device registration can be conducted in several ways, depending on your situation and preferences:

- **Vendor registration**: If your Surface Hub 3 devices are sourced from a vendor that supports Autopilot, they can register your devices directly with the service.
- **Manual registration**: For devices already in possession or when vendor registration is not an option, use the Microsoft Endpoint Manager Admin Center or Windows PowerShell scripts to manually upload device information.

## Step 4: Configure network

Ensure that your network is configured to allow devices to access the necessary Microsoft services during the setup process. This may involve configuring firewalls and proxies to permit connections to Autopilot and related services.

## Step 5: Plan your deployment

- **Deployment profiles**: Determine the settings and configurations that will be applied to your Surface Hub 3 devices. Create deployment profiles in Microsoft Endpoint Manager, specifying aspects like language, region, and whether users should be allowed to personalize their devices.
- **User roles and permissions**: Decide which users will have administrative rights on the devices and configure these settings accordingly.

## Setting up Teams Rooms Autologin

Integrating Surface Hub 3 devices into the collaborative ecosystem of an organization involves ensuring they are ready to facilitate seamless meetings. A key component of this readiness is configuring Teams Rooms to support Autologin, allowing for an effortless start to meetings without manual sign-ins. This setup is crucial for organizations looking to maximize the efficiency and usability of their collaborative spaces.

### Understanding Teams Rooms Autologin

Teams Rooms Autologin enables the Surface Hub 3 to automatically sign into a Microsoft Teams Rooms account upon startup. This functionality ensures that the device is immediately ready for use in a Teams meeting, minimizing setup time and improving the user experience. To achieve this, specific configuration steps must be followed during the deployment process.

### Configuring Autologin for Teams Rooms

The setup process involves several key steps, executed through the Microsoft Endpoint Manager (Intune), ensuring that each Surface Hub 3 is configured to meet the organization's requirements for Teams meetings.

> [!TIP]
> This section provides an overview of Autologin for Teams Rooms. For detailed guidance, see **Add link here to Teams Rooms documentation**. 

1. **Create a Configuration Profile**:
    - In the Microsoft Endpoint Manager Admin Center, navigate to **Devices** > **Configuration profiles** > **Create profile**.
    - Select **Windows 10 and later** as the platform and **Custom** as the profile type.
    - Enter a meaningful name for the profile, such as "Teams Rooms Autologin Configuration".
2. **Configure profile settings**:
    - Add the necessary configuration settings that enable Autologin. This typically involves specifying the Teams Rooms account credentials and configuring the device to use these credentials for automatic sign-in.
    - Ensure that the settings adhere to your organization's security policies, especially regarding credential storage and management.
3. **Assign the profile**:
    - Assign the newly created configuration profile to your Surface Hub 3 devices. This can be done based on groups, ensuring that only devices designated as Teams Rooms receive this configuration.
    - Monitor the profile deployment to ensure it is successfully applied to the devices.
4. **Test the Autologin functionality**:
    - After the profile is applied, test the Autologin functionality on a Surface Hub 3 device. Verify that the device automatically signs into the Teams Rooms account without requiring manual input.
    - Ensure that the device can successfully initiate and join Teams meetings.

### Security Considerations

When configuring Teams Rooms Autologin, it's essential to balance convenience with security. Consider the following:

- **Credential management**: Securely manage the credentials used for Autologin, ensuring they are protected against unauthorized access.
- **Device access**: Implement measures to prevent unauthorized use of the Surface Hub 3, such as physical security controls and device lockdown policies.

### Best practices

- **Regularly Update Credentials**: Change the Teams Rooms account credentials periodically to enhance security.
- **Monitor Device Activity**: Keep an eye on the usage of Teams Rooms-enabled devices to detect any unusual activity or unauthorized access attempts.

Setting up Teams Rooms Autologin on Surface Hub 3 devices significantly enhances the meeting room experience by reducing setup times and streamlining the start of meetings. By following these steps, organizations can ensure their collaborative spaces are equipped for efficient, secure, and engaging meetings.
