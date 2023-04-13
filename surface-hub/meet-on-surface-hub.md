---
title: Start and finish a meeting on Surface Hub
description: Explains how to start and finish a meeting on Surface Hub.
ms.reviewer: dpandre
manager: frankbu
ms.prod: surface-hub
author: coveminer
ms.author: hachidan
ms.topic: how-to
ms.date: 04/14/2023
ms.localizationpriority: medium

---

# Start and finish a meeting on Surface Hub

Surface Hub is a collaboration device designed to be used in meeting spaces by different groups of people.

## Meet with others on Surface Hub 2S

### Have an ad-hoc meeting

If no scheduled meetings are listed on the welcome screen, the Surface Hub is free to use—sign in and start working.

How you meet is up to you—you can open Microsoft Whiteboard and start drawing out your ideas, open up your recent files to see them on the big screen, get real-time feedback from your team, and start a call with Teams or Skype. Get creative and work however, works best for that moment—it's up to you.

### Schedule a meeting

It's easy to schedule a meeting on a Surface Hub—invite it to the meeting like you would a person. Include the Surface Hub on the invite list of your meeting—you'll be able to see its availability just like you can the other people you're inviting.

If you need to know the name of the Surface Hub you want, select **Call** on the welcome screen and then look for the email address of the Surface Hub listed under **Organizer**. That's the email address you should invite to your meeting.

### Start a scheduled meeting

If you’ve scheduled a meeting on a Surface Hub, you should see your name listed on the welcome screen along with the time of the meeting. To start your meeting, select **Join**, and you'll immediately enter the meeting. If your meeting includes Teams or Skype, the call will also begin.

### Add someone to a call on Surface Hub

**Add someone to a call using Teams:**

1. Select **Show participants**.
2. Enter the name or email address of the person you want to add in the box that says **Invite someone**.
3. Or, dial the phone number of the person you want to add.

**Add someone to a call on a Surface Hub using Skype:**

1. Select **People** at the bottom of the Skype pane, then **Add.**
2. Enter the name or email address of the person you want to add or dial their number.

### Share the Surface Hub screen during a call

**Share the screen using Teams:**

1. Select **Share**. You’ll see a yellow outline around the content you’re presenting on the screen.
2. To stop sharing without hanging up, select **Stop sharing**.

**Share the screen using Skype:**

1. Select **Present screen**.
2. To stop presenting without hanging up, select **Stop presenting**.

## Finish a Surface Hub meeting with End session

At the end of a meeting, users can tap **End session** to clean up any sensitive data and prepare the device for the next meeting. Surface Hub will clean up, or reset, the following states:

- Applications
- Operating system
- User interface

This section explains what **End session** resets for each of these states.

## Applications

When you start apps on Surface Hub, they are stored in memory and data is stored at the application level. Data is available to all users during that session (or meeting) until data is removed or overwritten. When **End session** is selected, Surface Hub application state is cleared out by closing applications, deleting browser history, resetting applications, and removing Skype logs.

### Close applications

Surface Hub closes all visible windows, including Win32 and Universal Windows Platform (UWP) applications. The application close stage uses the multitasking view to query the visible windows. Win32 windows that do not close within a certain timeframe are closed using **TerminateProcess**.

### Delete browser history

Surface Hub uses Delete Browser History (DBH) in Edge to clear Edge history and cached data. This is similar to how a user can manually clear out their browser history, but **End session** also ensures that application states are cleared and data is removed before the next session, or meeting, starts.

### Reset applications

**End session** resets the state of each application installed on the Surface Hub. Resetting an application clears all background tasks, application data, notifications, and user consent dialogs. Applications are returned to their first-run state for the next people that use Surface Hub.  

### Remove Skype logs

Skype does not store personally-identifiable information on Surface Hub. Information is stored in the Skype service to meet existing Skype for Business guidance. Local Skype logging information is the only data removed when **End session** is selected. This includes Unified Communications Client Platform (UCCP) logs and media logs.

## Operating System

The operating system hosts a variety of information about the state of the sessions that needs to be cleared after each Surface Hub meeting.

### File System

Meeting attendees have access to a limited set of directories on the Surface Hub. When **End session** is selected, Surface Hub clears these directories:

- Music
- Videos
- Documents
- Pictures
- Downloads

Surface Hub also clears these directories, since many applications often write to them:

- Desktop
- Favorites
- Recent
- Public Documents
- Public Music
- Public Videos
- Public Downloads

### Credentials

User credentials stored in **TokenBroker**, **PasswordVault**, or **Credential Manager** are cleared when you tap **End session**.

## User interface

User interface (UI) settings are returned to their default values when **End session** is selected.

### UI items

- Reset Quick Actions to default state
- Clear Toast notifications
- Reset volume levels
- Reset sidebar width
- Reset tablet mode layout
- Sign user out of Microsoft 365 meetings and files

### Accessibility

Accessibility features and apps are returned to default settings when **End session** is selected.

- Filter keys
- High contrast
- Sticky keys
- Toggle keys
- Mouse keys
- Magnifier
- Narrator

### Clipboard

The clipboard is cleared to remove data that was copied to the clipboard during the session.

## Frequently asked questions

**What happens if I forget to tap End session at the end of a meeting, and someone else uses the Surface Hub later?**

- Surface Hub only cleans up meeting content when users tap **End session**. If you leave the meeting without tapping **End session**, the device will return to the welcome screen after some time. From the welcome screen, users can resume the previous session or start a new one. You can also disable the ability to resume a session if **End session** is not pressed.

**Are documents recoverable?**

- Removing files from the hard drive when **End session** is selected is just like any other file deletion from a hard disk drive. Third-party software might be able to recover data from the hard disk drive, but file recovery is not a supported feature on Surface Hub. To prevent data loss, always save the data you need before leaving a meeting.

**Do the clean-up actions from End session comply with the US Department of Defense clearing and sanitizing standard: DoD 5220.22-M?**

- No. Currently, the clean-up actions from **End session** do not comply with this standard.  
