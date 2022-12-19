---
title: Surface Slim Pen 2 haptics dev notes
description: This page provides implementation notes for app developers who want to extend Windows 11 Ink capabilities of Surface Slim Pen 2 for Business. 
ms.prod: w11

ms.localizationpriority: medium

author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 12/07/2021
ms.reviewer: gusing
manager: frankbu

appliesto:
- Windows 11
---

# Surface Slim Pen 2 haptics dev notes

This page provides implementation notes for app developers who want to extend Windows 11 Ink capabilities of [Surface Slim Pen 2 for Business](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?). Customizable haptics features include the following:

- **Inking feedback** that simulates the feel of pens, pencils, and other writing or drawing tools.
- **Interaction feedback** that responds directly to user actions such as hovering over a button, clicking a button, or completing a task with the pen.

If you're customizing an app for Surface Slim Pen 2, refer to the Windows Ink guidelines described in [Pen interactions and haptic feedback](/windows/apps/design/input/pen-haptics) and then consult the notes below.

## Implementation notes

Surface Slim Pen 2 complies with Windows 11 Ink guidelines with the following exceptions:

- **Interaction waveforms.** As documented in the [Send and stop interaction feedback](/windows/apps/design/input/pen-haptics#send-and-stop-interaction-feedback)” section, sending an interaction waveform when an inking waveform is being played will temporarily interrupt the inking waveform. However, with the current Slim Pen 2 implementation, the inking waveform might not resume when the interaction waveform stops. Therefore, if still required, the inking waveform needs to be re-enabled after the interaction feedback. There is no need to wait for the interaction feedback to complete.
- **Unsupported features.** As documented in the [Haptic feedback customizations](/windows/apps/design/input/pen-haptics#haptic-feedback-customizations)” section, the following optional features are not supported on Surface Slim Pen 2: Play Count and Replay Pause Interval. Although these usages appear in the descriptor, they are not currently supported. Therefore, the following functions return an incorrect value: IsPlayCountSupported, IsPlayDurationSupported, IsReplayPauseIntervalSupported.

## Learn more

- [Pen interactions and Windows Ink in Windows apps](/windows/apps/design/input/pen-and-stylus-interactions)
- [Surface Slim Pen 2 for Business](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?)
- [Surface pen features and compatibility](https://support.microsoft.com/surface/identify-your-surface-pen-and-features-c82a0208-2e35-b347-dae0-d7f4922edc77)

