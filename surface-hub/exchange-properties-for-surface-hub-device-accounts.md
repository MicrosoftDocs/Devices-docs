---
title: Microsoft Exchange properties for device account on Surface Hub
description: Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub.
ms.assetid: 3E84393B-C425-45BF-95A6-D6502BA1BF29
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: glossary
ms.date: 01/24/2023
ms.localizationpriority: medium
appliesto:
- Surface Hub 
- Surface Hub 2S
---

# Microsoft Exchange properties for device account on Surface Hub

Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub. The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.
| Property              | Description                                                                                                                                                                                                  | Value                                                                                                                      | Impact                                                                                                                                 |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| AutomateProcessing    | The AutomateProcessing parameter enables or disables calendar processing on the mailbox.                                                                                                                     | AutoAccept                                                                                                                 | Surface Hub will be able to automatically accept or decline meeting requests based on its availability.                                |
| AddOrganizerToSubject | The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.                                                                            | $False                                                                                                                     | The welcome screen will not show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject). |
| AllowConflicts        | The AllowConflicts parameter specifies whether to allow conflicting meeting requests.                                                                                                                        | $False                                                                                                                     | Surface Hub will decline meeting requests that conflict with another meeting’s time.                                                   |
| DeleteComments        | The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.                                                                                  | $False                                                                                                                     | The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.                         |
| DeleteSubject         | The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.                                                                                                    | $False                                                                                                                     | Meeting request subjects can be shown on the Surface Hub.                                                                              |
| RemovePrivateProperty | The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.                                                                                               | $False                                                                                                                     | Private meeting subjects will show as Private on the welcome screen.                                                                   |
| AddAdditionalResponse | The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.                                                     | $True                                                                                                                      | When a response is sent to a meeting request, custom text will be provided in the response.                                            |
| AdditionalResponse    | The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.<br>**Note**  This text will not be sent unless AddAdditionalResponse is set to $True. | Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources. | An additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.                  |

