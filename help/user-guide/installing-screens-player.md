---
title: Installing Screens Player
seo-title: Installing Screens Player
description: Follow this page to learn about the installation of available AEM Screens Player.
seo-description: Installing Screens Player
contentOwner: jsyal
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: bb979a71-7235-429f-b520-6d85b8b666fa
---
# Installing AEM Screens Player {#installing-player}

This page describes how to install AEM Screens player.

## Available Screens Player {#available-players}

The AEM Screens player is available for Android, Chrome OS and Windows.

To download **AEM Screens Player**, visit the [AEM 6.5 Player Downloads](https://download.macromedia.com/screens/) page.

>[!NOTE]
>
>Once you download the latest Player (*.exe*), follow the steps on the player to complete the ad-hoc installation:
>
>1. Long-press on the top left corner to open the admin panel.
>1. Navigate to **Configuration** from the left action menu and enter the location address of the AEM instance in **Server** and click **Save**.
>1. Click on the **Registration** link from the left action menu and the steps below to complete the device registration process.

## Basic Playback Monitoring {#playback-monitoring}

The player reports various playback metrics with each `ping` that defaults to 30 seconds. Based on these metrics, we can detect various edge cases such as stuck experience, blank screen, and scheduling issues. This lets us understand and troubleshoot issues on the device, and thus expedites an investigation and corrective measures with you.

Basic Playback monitoring in an AEM Screens player allows us to:

* Remotely monitor, if a player is properly playing content.

* Improve reactivity to blank screens or broken experiences in the field.

* Decreases the risk of showing a broken experience to the end user.

### Understanding Properties {#understand-properties}

The following properties are included in each `ping`:

|Property|Description|
|---|---|
|id {string}|the player identifier|
|activeChannel {string}|currently playing channel path, or null if nothing is scheduled|
|activeElements {string}|comma-separated string, currently visible elements in all playing sequence channels (multiple in case of a multi-zone layout)|
|isDefaultContent {boolean}|true if the playing channel is considered a default or fallback channel (that is, has priority 1 and no schedule)|
|hasContentChanged {boolean}|true if the content changed in the last 5 minutes, false otherwise|
|lastContentChange {string}|timestamp of the last content change|

>[!NOTE]
>Optionally, a more advanced property can be enabled from the player preferences (Enable Playback Monitoring) and that is:
>|Property|Description|
>|---|---|
>|isContentRendering {boolean}|true if the GPU can confirm it is playing actual content (based on pixel analysis)|

### Limitations {#limitations}

Few limitations to basic playback monitoring are listed below:

* The player reports its own playback state to the server, so it requires an active connection.

* The `isContentRendering` property that checks the GPU is currently too resource intensive to be enabled by default and requires explicit opt-in from the player preferences. It is recommended not to use it in conjunction with videos in production.

* This feature is only supported for sequence channels and does not yet cover the interactive channels (SPA) use case.

* The metrics are not yet fully exposed to our customers, we are working hard on enabling dashboard-like reporting and alerting mechanism in the near future.

### Additional Resources {#additional-resources}

See the following topics for an in-depth information:

* To download Android Player, visit **Google Play**. To learn about implementing Android Watchdog, see [Implementing Android player](implementing-android-player.md).

* To implement Chrome OS Player, see [Chrome Management Console](implementing-chrome-os-player.md) for more information.

* To configure AEM Screens Windows player, see [Implementing Windows Player](implementing-windows-player.md).
