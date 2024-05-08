---
title: Release Notes for Feature Pack 202109
description: Learn about the AEM Screens Feature Pack 202109 that was released on September 23, 2021.
feature: Feature Pack
role: Developer
level: Intermediate
exl-id: e1794013-59ce-4ddc-93c0-601668c75cd1
---
# Release Notes for Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>Adobe recommends that you upgrade to the latest version of Adobe Experience Manager (AEM). AEM Screens provides maintenance support for the AEM 6.3 Screens platform.

## Availability {#availability}

AEM Screens released AEM 6.5 Feature Pack 9.

You can download the latest Feature Pack for AEM Screens 6.5.9 Release from the [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) using your Adobe ID. Navigate to the **Adobe Experience Manager** tab and search for **Screens** to get the latest Feature Pack titled as **AEM 6.5 Screens FP9**.

## Release Date {#release-date}

The Release Date for AEM Screens Feature Pack 202109 is September 23, 2021.

### What's New {#what-is-new}

* **Thumbnail Support for Videos**

   Thumbnail Support for videos in now supported in AEM Screens. A Content Author defines a thumbnail for videos so that the image is used as a placeholder. They also properly test content playback and targeting, while the appropriate team finalizes the actual video. The image can also be used in case the playback of the video fails.
   See [Thumbnail Support for Videos](/help/user-guide/thumbnail-support.md) for more details.

* **Basic Playback Monitoring**

   AEM Screens now supports basic playback monitoring. The player now reports various playback metrics with each ping (defaults to 30 seconds). Based on the metrics, it detects various edge cases (stuck experience, blank screen, scheduling problem, and so on). This feature lets the team remotely monitor if a player is properly playing content and improves reactivity to blank screens or broken experiences in the field. It also decreases the risk of showing a broken experience to the end user.
   See [Basic Playback Monitoring](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/installing-screens-player#playback-monitoring) for more details.

* **Updates to Content Assignment Report**

   Content Assignment Report is now optimized and improved with an enhanced user experience. The downloadable report displays improved player-related entities. Such entities include locations, displays, and devices in one spreadsheet tab. It also includes the content provider information such as channels and assets in other tab.
   See [Content Assignment Report](/help/user-guide/content-assignment-report.md) for more details.

* **Adaptive Renditions**

   Adaptive Renditions let the device click the best rendition automatically for a device based on customer-defined rules. 
   
   As an AEM Screens Developer, you can now configure device-specific asset renditions to be downloaded and played automatically without having to create all content variations manually. See [Adaptive Renditions: Architectural Overview and Configurations](/help/user-guide/adaptive-renditions.md) for more details.

   Also, as an AEM Screens Content Author, you can configure your assets to use Adaptive Renditions. You can also migrate your devices for large networks to use this feature in your AEM Screens channels. See [Using Adaptive Renditions in AEM Screens](/help/user-guide/using-adaptive-renditions.md) for more details. 

* **Support for V3 Manifests**

   You can now configure the Dispatcher for Manifest Version v3. For enabling v3 Manifest, do the following:

   * Clear any pending offline content jobs in both author and published.

      * Navigate to CRXDE Lite in Author and Publish.

      * Click Tools > Query.

      * In the query, use `/jcr:root/var/eventing/jobs/assgined//element(*,slingevent:Job)[\@event.job.topic='screens/offline_content_update']`.

      * This lists any offline content jobs that are currently running or pending in the queue.

      * Wait until there are no more offline content jobs returned from the query.

   * Disable ContentSync in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag`.
   
   * Enable SmartSync in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl`.
   
   * Update Dispatcher.

   * Update the custom component.

   
   * See [Configuring Dispatcher for Manifest Version v3](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#configuring-dispatcherv3) for more details.
   * If you are using custom components as a part of v3 manifests, see [Template for Custom Handlers](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop#custom-handlers).
   

### Bug Fixes {#bug-fixes}

**Player Side**

* Resolved file caching errors by replacing assets with renditions.

* The players now only expose asset renditions, if rendition mapping is present.

* Enhanced ping to reauthenticate if the response is not valid JSON.

* Numeric channel names/roles caused blank screen.

* Download optimized renditions by way of SmartSync.

* Transformed the mapping into a list of rendition keys.

* Removed access to `cmd.exe` and `reg.exe` in the Windows Player.

* A player must report its last successful playback event.

* A player must report its playback status.

* Player does not redownload Assets when `ALL` Cache is cleared.

* As a Player Admin, you can now choose a player name.

* Removing channel assignment from display is not reflected on the player.

* If the player is reloaded while the channel update is being downloaded, the player ignores the update.

* Embedded Page Component now respects touch event.

* Remote provisioning of the Tizen player is now supported.

**Server Side**

* Target video is not showing
* Race conditions on broadcasting display data to subsequences.

* Channel Preview does not work for Channels containing Videos.

* Preview mode showing blank for Split screen channel.

* Video thumbnails render blank with enabled Adaptive Renditions.

* Automatically update the channel manifest if the referenced page is published.

* Deleted devices now do not block the Screens replication queue.

* The manifest did not contain targeted content or Sites embedded pages. This bug is now fixed.

* A new core image component is now added to the channel manifest.

* Downloading optimized renditions by way of SmartSync is now supported.

* Play optimized rendition for all assets.

* Added support for multiple content provider types

* The Embedded Sequence Playback Strategy was broken and this bug is now fixed.

* Offline manifest using the request parameter `wcmmode` for html entry, making it uncacheable.

* Empty dynamic embedded sequence sometimes caused blank screen.

* The player now reports its playback status.

* Video was playing in `Tiny mode` and not played as full screen video on device and the issue is fixed now.

### Released AEM Screens Players

The following AEM Screens Players are released for AEM 6.5 Feature Pack 9:

* ChromeOS
* Windows
* Tizen
* Android&trade;
* Linux&reg;

#### AEM Screens Player Downloads

To download the latest AEM Screens Player and learn more about the bug fixes, see **[AEM Screens Player Downloads](https://download.macromedia.com/screens/index.html)**.
