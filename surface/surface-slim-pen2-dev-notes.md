---
title: Surface Slim Pen 2 developer notes
description: This page provides implementation notes for app developers who want to extend Windows 11 Ink capabilities of Surface Slim Pen 2 for Business. 
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/07/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
---

# Surface Slim Pen 2 developer notes

This page provides implementation notes for app developers who want to extend Windows 11 Ink capabilities of [Surface Slim Pen 2 for Business](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?). Customizable features include the following:

- **Haptic feedback** that simulates the feel of pens, pencils, and other writing or drawing tools.
- **Interaction feedback** that responds to user actions such as hovering over a button, clicking a button, or completing a task with the pen.

If you're customizing an app for Surface Slim Pen 2, refer to the following Windows Ink guidelines [Pen interactions and haptic feedback](/windows/apps/design/input/pen-haptics) in conjunction with the notes listed below.

## Implementation notes

Slim Pen 2 complies with Windows 11 Ink guidelines with the following exceptions:

- **Interaction waveforms.** As documented in the [Send and stop interaction feedback](/windows/apps/design/input/pen-haptics#send-and-stop-interaction-feedback)” section, sending an interaction waveform when an inking waveform is being played will temporarily interrupt the inking waveform. However, with the current Slim Pen 2 implementation, the inking waveform might not resume when the interaction waveform stops. Therefore, if still required, the inking waveform needs to be re-enabled after the interaction feedback. There is no need to wait for the interaction feedback to complete.
- **Unsupported features.** As documented in the [Haptic feedback customizations](/windows/apps/design/input/pen-haptics#haptic-feedback-customizations)” section, the following optional features are not supported on Surface Slim Pen 2: Play Count and Replay Pause Interval. Although these usages appear in the descriptor, they are not currently supported.

