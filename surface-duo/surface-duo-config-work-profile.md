---
title: Configure Android Enterprise Work Profile for Surface Duo
description: This article explains how to set up work profile on Surface Duo.
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Duo
---

# Configure Android Enterprise Work Profile for Surface Duo

Targeted at  BYOD deployments, work profiles provide a separate space on Duo for work apps and data, giving organizations full control of their data, apps, and security policies without preventing employees from using their device for personal apps and data.

### Set up Android Enterprise Work Profile

Use work profiles to manage corporate data and apps on user-owned Android devices. By default, enrollment of personally owned work profile devices is enabled and requires no further admin configuration.  

**To enable Enterprise Work Profile:**

- In Endpoint Manager, select **Devices** > **Android** > **Android enrollment** and then select **Personal devices with work profile**.
<br><br>
 ![Enable Enterprise Work Profile](images/enroll-start.png)

 
**Sign into Surface Duo with Android Enterprise Work Profile**

1. Install the Company Portal app from Google Play Store and sign in with your Microsoft work or school account.<br><br>
![Sign into Surface Duo](images/duo-wp-1.png)
 
2. On the Access Setup page, select **Begin**.<br><br>
![Begin](images/duo-wp-2.png)

3. Review the information on the privacy page and select **Continue**.<br><br>
 ![Continue](images/duo-wp-3.png)
<br><br>
 ![Select continue](images/duo-wp-4.png)
 
4. When the work profile setup completes, select **Continue** to activate and register the device.<br><br>
 ![Select continue to activate and register the device](images/duo-wp-5.png)

5. Select **Continue**.<br><br>
 ![Select continue again](images/duo-wp-6.png)

6. When you have activated the work profile, select **Continue** to update device settings. In this example, the work profile applies an MDM setting to require a stronger 6-digit alphanumeric password. <br><br>

     ![Example alphanumeric password](images/duo-wp-7.png)<br><br>
7. Select **Resolve** to enter the required authentication and then select **Continue** to complete Work Profile setup. <br><br>
     ![Select continue to complete setup](images/duo-wp-8.png)<br><br>
     ![complete setup](images/duo-wp-9.png)<br><br>

## Learn more

- [Set up enrollment of Android Enterprise work profile devices](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

