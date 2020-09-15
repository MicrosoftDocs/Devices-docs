---
title: Microsoft Surface Deployment Accelerator (Surface)
description: Microsoft Surface Deployment Accelerator provides a quick and simple deployment mechanism for organizations to reimage Surface devices.
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: deploy, install, tool
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
---

# Microsoft Surface Deployment Accelerator

Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.

Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the 
SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.

The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments. If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.

The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.

## Requirements

1. A USB thumb drive at least 16 GB in size. The USB drive will be formatted.
2. An .iso file with Windows 10 Pro or Windows 10 Enterprise. 
    - The media creation tool can be used to download and create an .iso file. For more information, see [Download Windows 10](https://www.microsoft.com/software-download/windows10).

**To run SDA:**

1. Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub. 
2. Review the [README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) documentation.
3. On the [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) page, click the **Code** button and then select **Download ZIP** to save the files locally on your computer.
4. Right-click the .zip file and then click **Properties**.
5. On the **General** tab, select the **Unblock** checkbox and then click **OK**.
6. Extract the .zip file to a location on your hard drive (ex: C:\SDA).
7. Open an elevated Windows PowerShell prompt and set ExecutionPolicy to 



Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force

.\CreateSurfaceWindowsImage.ps1 -ISO D:\SDA\19042.508.200907-1718.20h2_release_svc_refresh_CLIENTENTERPRISE_OEM_x64FRE_en-us.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True

   ![Running Surface Deployment Accelerator tool](images/surface-deployment-accelerator.png)

## Related links

 - [Open source image deployment tool released on GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
