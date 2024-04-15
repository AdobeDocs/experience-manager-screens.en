---
title: Installing Screens Player
description: Learn how to correctly install an AEM Screens Player.
contentOwner: jsyal
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: bb979a71-7235-429f-b520-6d85b8b666fa
---
# Installing AEM Screens Player {#installing-player}

This page describes how to install AEM Screens player.

## Available Screens Player {#available-players}

The AEM Screens player is available for Android&trade;, Chrome OS, and Windows.

To download **AEM Screens Player**, visit the [AEM 6.5 Player Downloads](https://download.macromedia.com/screens/) page.

>[!NOTE]
>
>After you download the latest Player (*.exe*), follow the steps on the player so you can complete the ad-hoc installation:
>
>1. Long-press on the top-left corner to open the admin panel.
>1. Navigate to **Configuration** from the left action menu and enter the location address of the AEM instance in **Server** and select **Save**.
>1. Select **Registration** link from the left action menu and the steps below to complete the device registration process.

## Basic Playback Monitoring {#playback-monitoring}

The player reports various playback metrics with each `ping` that defaults to 30 seconds. Based on these metrics, it can detect various edge cases such as stuck experience, blank screen, and scheduling issues. This lets us understand and troubleshoot issues on the device, and thus expedites an investigation and corrective measures with you.

Basic Playback monitoring in an AEM Screens player lets you do the following:

* Remotely monitor, if a player is properly playing content.

* Improve reactivity to blank screens or broken experiences in the field.

* Decreases the risk of showing a broken experience to the end user.

### Understanding Properties {#understand-properties}

The following properties are included in each `ping`:

|Property|Description|
|---|---|
|id {string}|the player identifier|
|activeChannel {string}|currently playing channel path, or null if nothing is scheduled|
|activeElements {string}|comma-separated strings, currently visible elements in all playing sequence channels (multiple in there is a multi-zone layout)|
|isDefaultContent {boolean}|true if the playing channel is considered a default or fallback channel (that is, has priority 1 and no schedule)|
|hasContentChanged {boolean}|true if the content changed in the last 5 minutes, false otherwise|
|lastContentChange {string}|timestamp of the last content change|

>[!NOTE]
>Optionally, a more advanced property can be enabled from the player preferences (Enable Playback Monitoring) and that is:
>
>|Property|Description|
>|---|---|
>|isContentRendering {boolean}|true if the GPU can confirm it is playing actual content (based on pixel analysis)|

### Limitations {#limitations}

Few limitations to basic playback monitoring are listed below:

* The player reports its own playback state to the server, so it requires an active connection.

* The `isContentRendering` property that checks the GPU is too resource intensive to be enabled by default and requires explicit opt-in from the player preferences. Adobe recommends that you do not use it with videos in production.

* This feature is only supported for sequence channels and does not yet cover the interactive channels (SPA) use case.

* The metrics are not yet fully exposed to customers, Adobe is working on enabling dashboard-like reporting and alerting mechanisms soon.

### Other Resources {#additional-resources}

See the following topics for an in-depth information:

* To download Android&trade; Player, visit **Google Play**. To learn about implementing Android&trade; Watchdog, see [Implementing Android&trade; player](implementing-android-player.md).

* To implement Chrome OS Player, see [Chrome Management Console](implementing-chrome-os-player.md) for more information.

* To configure AEM Screens Windows player, see [Implementing Windows Player](implementing-windows-player.md).
