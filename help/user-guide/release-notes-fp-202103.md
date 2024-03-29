---
title: Release Notes for Feature Pack 202103
description: "Follow this page to get information for AEM Screens Feature Pack 202103 released on March 05, 2021."
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: a8741cc7-de4f-4e5a-b69e-852a43597123
---
# Release Notes for Feature Pack 202103 {#release-notes-for-feature-pack}

>[!CAUTION]
>It is recommended that you upgrade to the latest version of Adobe Experience Manager (AEM). Screens provides maintenance support for AEM 6.3 Screens platform.

## Availability {#availability}

AEM Screens released AEM 6.5 Feature Pack 7.

You can download the latest feature pack for AEM Screens 6.5.7 Release from the [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) using your Adobe ID. Navigate to **Adobe Experience Manager** tab and search for **Screens** to get the latest feature pack titled as **AEM 6.5 Screens FP7**.

## Release Date {#release-date}

The Release Date for AEM Screens Feature Pack 202103 is March 05, 2021.

### What's New {#what-is-new}

* **AEM Screens Auto Registration of Players** 

   Bulk registering thousands of players manually is very cumbersome and adds time and cost. To simplify this process, the Auto Registration of players feature allows you to specify a pre-shared key in AEM that can be provisioned into a player either through a configuration file or an Mobile Device Management (MDM) solution.
   
   Refer to [Auto Registration of Players](/help/user-guide/auto-registration-players.md) for more details.


* **Bulk Provisioning of Android Player using Enterprise Mobility Management**
   
   When deploying the Android player in bulk, it becomes tedious to manually register every single player with AEM. It is highly recommended to use an EMM (Enterprise Mobility Management) solution such as VMWare Airwatch, MobileIron or Samsung Knox to remotely provision and manage your deployment. AEM Screens Android player supports the industry standard EMM AppConfig to allow for remote provisioning.

   Refer to [Bulk Provisioning of Android Player using Enterprise Mobility Management](/help/user-guide/implementing-android-player.md#implementation) for more details.


### Bug Fixes {#bug-fixes}

* Improved performance for computing `clientlib` and `asset hashes`.

* SmartSync migration would break the player, if cache was not invalidated.

* Offline caches were not created, if the Assignment had *OfflineConfig*.

* Updates to Tizen player that broke because referrer policy strict-origin-when-cross-origin is not supported.

* Changing assigned channel's schedule *Repeats* field was breaking the UI.

* Update offline content was failing with query exceptions.

* Time lag between transitions during the interaction in interactive experience is now fixed.

* Failed config update request was causing the blank screen.

### Released AEM Screens Players {#released-aem-screens-players}

The following AEM Screens Players are released for AEM 6.5 Feature Pack 7:

* Chrome OS
* Windows
* Linux

#### AEM Screens Player Downloads  {#aem-screens-player-downloads}

To download the latest AEM Screens player and learn more about the bug fixes, refer to **[AEM Screens Player Downloads](https://download.macromedia.com/screens/index.html)**.
