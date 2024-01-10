---
title: Surface Hub can't download updates from Windows Update
description: Helps resolve the issue in which Surface Hub can't download updates from Windows Update. The download either doesn't start or remains stuck at 1% progress.
ms.date: 05/10/2023
author: Deland-Han
ms.author: delhan
manager: dcscontentpm
audience: itpro
ms.topic: troubleshooting
ms.service: surface-hub
localization_priority: medium
ms.reviewer: jarrettr
ms.custom: csstroubleshoot
ms.technology: windows
---
# Surface Hub can't download updates from Windows Update

This article helps resolve the issue in which Surface Hub can't download updates from Windows Update. The download either doesn't start or remains stuck at 1% progress.

_Applies to:_ &nbsp; Surface Hub  
_Original KB number:_ &nbsp; 3191418

## Symptoms

If you have a proxy server configured and you try to check for and download updates through Windows Update on the Surface Hub, the download either doesn't start or remains stuck at 1% progress. If you check for and download updates on a connection that has a direct access to the Windows Update servers, this works without a problem.

## Cause

This issue occurs if a proxy tries to do any of the following:

- SSL inspection
- Cache updates from Windows Update
- Block support for partial file download (HTTP range headers)

Windows Update uses dynamically created temporary file names that differ for each computer that downloads updates. This eliminates any benefit that might be gained from caching. Windows Update also uses the Background Intelligent Transfer Service (BITS) as a client, which can request partial files—an operation that the proxy may not support. (Instead, the proxy may support only entire objects.) Larger updates, such as Feature updates, can be tailored by the Windows Update servers to each individual computer.

## Resolution

To resolve this issue, make sure that the proxy doesn't try to perform any of the operations that are described in the "Cause" section on Windows Update traffic. For a list of the URLs that are used by Windows Update, see [Can't download updates from Windows Update from behind a firewall or proxy server](/troubleshoot/windows-client/deployment/windows-update-issues-troubleshooting).

If you're using a Bluecoat proxy, you can find more details at [Microsoft Windows updates fail to install](https://knowledge.broadcom.com/external/article/166719/microsoft-windows-updates-fail-to-instal.html).

> **Third-party information disclaimer**
>
> Microsoft provides third-party contact information to help you find technical support. This contact information may change without notice. Microsoft does not guarantee the accuracy of this third-party contact information.
