---
title: Surface Data Eraser (IT Toolkit)
description: This article describes how to use Data Eraser USB Builder, included in the Surface IT Toolkit, and generate a certificate of sanitization
ms.service: surface
ms.localizationpriority: medium
author: coveminer
ms.author: chauncel
ms.topic: overview
ms.date: 04/25/2024
ms.reviewer: chauncel
manager: frankbu
appliesto:
- Windows 11
- Windows 10
---

# Surface Data Eraser (IT Toolkit)

This article explains how to create a secure data wipe USB key with the Surface Data Eraser and generate a certificate of sanitization. You can use the data wipe USB key on your target device and other supported devices with matched architecture.

## Supported on current devices

- All current Surface devices, including Surface Pro 7 and later, Surface Laptop 3 and later, Surface Go 2 and later, Surface Laptop Studio and later, Surface Laptop SE, Surface Laptop Go and later. 

## Not supported on legacy devices

- This version of Surface Data Eraser is not supported on legacy devices such as Surface Laptop (1st gen), Surface Studio (1st gen), Surface Go, Surface Go 2, Surface Pro 5th Gen, and others. 
- To securely erase data on legacy devices, see [Microsoft Surface Data Eraser (legacy)](microsoft-surface-data-eraser.md)


## Create the Data Eraser USB

1. Open Surface IT Toolkit, select **Data Eraser USB-Builder** > **Create USB**.

    :::image type="content" source="images/it-toolkit-data-eraser.png" alt-text="Screenshot of Data Eraser.":::

2. On the Select device page, choose your target device from the list of Managed devices or from the dropdown list under **All Devices** and select **Next**.

    :::image type="content" source="images/it-toolkit-data-eraser-select-device.png" alt-text="Screenshot of Select device page.":::

3. Insert a USB drive in your device. Back up any existing data before proceeding.

4. On the Final review page, confirm your selected device and choose a validation method for the data wipe. You have the option to perform a full SSD verification after the data wipe. Select **None** or **Full** depending on your requirement.

5. Under **USB Key Selection**, choose the USB drive you intend to use. Select **Create.**

    :::image type="content" source="images/it-toolkit-create-bootable-usb1.png" alt-text="Screenshot of Final review page.":::

6. When the USB Creation process concludes, a confirmation message appears indicating **Creating Bootable USB: Complete**. Select **Finish.**

   :::image type="content" source="images/it-toolkit-finish-bootable-usb.png" alt-text="Screenshot of USB Creation Progress page.":::

7. When the tool indicates it's safe to eject the USB key, remove it from your device and plug it into the intended Surface device.

> [!WARNING]
> The Data Eraser process deletes all data on the device, including the operating system, installed apps, files, and settings.

8. To continue, type **CONFIRM** If you're unsure or do not wish to proceed, type **EXIT**.
9. Keep your device plugged into AC Power during the data wipe process.

## Generate Data Sanitization Certificate

1. On the Data Eraser tool interface, select **Generate Certificate**. This creates a certificate of sanitization using the log files written to the Data Eraser USB.

   :::image type="content" source="images/it-toolkit-certificate-sanitization.png" alt-text="Screenshot of Generate Certificate.":::

2. On the Sanitization Certificate page, enter the requested details.
3.
   :::image type="content" source="images/it-toolkit-certificate-details.png" alt-text="Screenshot of Certificate details.":::

4. Under Additional Details, input the Media Source. Use the Asset tag if available. Or you can use the Serial number or System UUID, as listed in the Surface UEFI menu on the wiped device. Optionally, you can add custom fields by clicking **+ Add custom field** if more information is necessary.
5. When all the relevant details are entered, select **Next** to proceed to the certificate creation process.
6. Review the certificate details and select **Generate**.

   :::image type="content" source="images/it-toolkit-generate-certificate.png" alt-text="Screenshot of  Certificate.":::

7. When complete, select **Show files** to access the Sanitization Certificate. Select **Finish**.

    :::image type="content" source="images/it-toolkit-certificate-complete.png" alt-text="Screenshot that shows Certficate Generation is complete.":::

8. Open the newly created certificate and add signatures as appropriate, as shown in the following redacted example.

    :::image type="content" source="images/it-toolkit-certificate-example.png" alt-text="Screenshot that shows an example Certficate.":::
