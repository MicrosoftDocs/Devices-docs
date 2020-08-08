---
title: Surface Duo 
description: This article explains
ms.prod: surface-duo
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/12/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Duo
---

# Configure Android Enterprise Work Profile for Surface Duo

Targeted at  BYOD deployments, work profiles provide a separate space on Duo for work apps and data, giving organizations full control of their data, apps, and security policies without preventing employees from using their device for personal apps and data.

### Setup Android Enterprise Work Profile

Use work profiles to manage corporate data and apps on user-owned Android devices. By default, enrollment of personally owned work profile devices is enabled and requires no further admin configuration.  d

**To enable Enterprise Work Profile:**

- In Endpoint Manager, select **Devices** > **Android** > **Android enrollment** and then select **Personal devices with work profile**.

 ![alt text](images/enroll-start.png)

 
**Sign into Surface Duo with Android Enterprise Work Profile**

1. Install the Company Portal app from Google Play Store and sign in with your Microsoft work or school account.
![alt text](images/duo-wp-1.png)
 
2. On the Access Setup page, select **Begin**.
![alt text](images/duo-wp-2.png)

3. Review the information on the privacy page and select **Continue**.
 ![alt text](images/duo-wp-3.png)
<br><br>
 ![alt text](images/duo-wp-4.png)
 
4. When the work profile setup completes, select **Continue** to activate and register the device.
 ![alt text](images/duo-wp-5.png)

5. Select **Continue**.
 ![alt text](images/duo-wp-6.png)

6. When you have activated the work profile, select Continue to update device settings.  If your company app protection policy requires stronger authentication than the default 4-character numerical passcode, review the guidance and select **Continue**.

**Note:** In this example, the work profile applies an MDM setting to require a stronger password — 6 characters long continuing both numbers and letters. 
 ![alt text](images/duo-wp-7.png)
 ![alt text](images/duo-wp-8.png)
 ![alt text](images/duo-wp-9.png)

7. Select **Resolve** to enter the required authentication and then select **Continue** to complete Work Profile setup. 

## Learn more

- [Set up enrollment of Android Enterprise work profile devices](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll).

