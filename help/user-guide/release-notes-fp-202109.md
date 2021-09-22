---
title: Release Notes for Feature Pack 202109
description: Follow this page to get information for AEM Screens Feature Pack 202105 released on September 23, 2021.
feature: Feature Pack
role: Developer
level: Intermediate
index: no
---
# Release Notes for Feature Pack 202109 {#release-notes-for-feature-pack}

>[!CAUTION]
>It is recommended that you upgrade to the latest version of Adobe Experience Manager (AEM). Screens provides maintenance support for AEM 6.3 Screens platform.

## Availability {#availability}

AEM Screens released AEM 6.5 Feature Pack 9.

You can download the latest feature pack for AEM Screens 6.5.9 Release from the [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) using your Adobe ID. Navigate to **Adobe Experience Manager** tab and search for **Screens** to get the latest feature pack titled as **AEM 6.5 Screens FP9**.

## Release Date {#release-date}

The Release Date for AEM Screens Feature Pack 202109 is September 23, 2021.

### What's New {#what-is-new}

* **Thumbnail Support for Videos**

   Thumbnail Support for videos in now supported in AEM Screens. A content author can define a thumbnail for videos so that the image can be used as a placeholder and properly test content playback and targeting, while the actual video is being finalized by the appropriate team. The image can also be used, in case the playback of the video fails.
   See Thumbnail Support for Videos for more details.

* **Basic Playback Monitoring**

   AEM Screens now supports basic playback monitoring. The player will now report various playback metrics with each ping (defaults to 30 seconds). Based on the metrics, it provides the ability to detect various edge cases (stuck experience, blank screen, scheduling problem, etc.). This feature allows the team to remotely monitor if a player is properly playing content, improves reactivity to blank screens or broken experiences in the field, and decreases the risk of showing a broken experience to the end user.
   See Basic Playback Monitoring for more details.

* **Updates to Content Assignment Report**

   Content Assignment Report is now optimized and improved with enhanced user experience. The downloadable report displays improved player related entities  such as locations, displays, and device in one spreadsheet tab and the content provider information such as channels and assets in other tab.

* **Adaptive Renditions**

   Adaptive Renditions allow the devices to automatically select the best rendition for a device based on customer-defined rules. 
   
   As an AEM Screens Developer, you can now configure device-specific asset renditions to be downloaded and played automatically without having to create all content variations manually. See Adaptive Renditions: Architectural Overview and Configurations to learn more.

   Additionally, as an AEM Screens Content Author, you can now use Adaptive Renditions in your AEM Screens project and also apply migration strategy for large networks. See Using Adaptive Renditions for more details.

* **Support for V3 Manifests**

   You can now configure the Dispatcher for Manifest Version v3. Refer to [Configuring Dispatcher for Manifest Version v3](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens.html?lang=en#configuring-dispatcherv3) for more details.
   Additionally, if you are using custom components as a part of v3 manifests, see [Template for Custom Handlers](https://experienceleague.adobe.com/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop.html?lang=en#custom-handlers).


### Bug Fixes {#bug-fixes}

**Player Side**

* Resolved file caching errors by replacing assets with renditions.

* The players now only expose asset renditions, if rendition mapping is present.

* You can now setup slack alerts based on splunk logs.

* Enhanced ping to re-authenticate if response is not valid JSON.

* Numeric channel names/roles caused blank screen.

* Download optimized renditions via SmartSync.

* Transformed the mapping into list of rendition keys.

* Removed access to `cmd.exe` and `reg.exe` in the windows player.

* A player needs to report its last successful playback event.

* A player needs to report its playback status.

* Player does not re-download Assets when `ALL` Cache is cleared.

* As a Player Admin, you can now choose a player name.

* Removing channel assignment from display is not reflected on the player.

* If player is reloaded while channel update is being downloaded, the player ignores the update.

* Embedded Page Component now respects touch event.

* Remote provisioning of Tizen player is now supported.

**Server Side**

* Target video is not showing
* Race condition on broadcasting display data to subsequences.

* Channel Preview does not work for Channels containing Videos.

* Preview mode showing blank for Split screen channel.

* Video thumbnails render blank with enabled adaptive renditions.

* Automatically update channel manifest if referenced page is published.

* Deleted devices now does not block the Screens replication queue.

* Manifest did not contain targeted content nor Sites embedded pages. This has now been fixed.

* New core image component are now added to the channel manifest.

* Downloading optimized renditions via SmartSync is now supported.

* Play optimized rendition for all assets.

* Added support for multiple content provider types

* Embedded Sequence Playback Strategy was broken and this has now been fixed.

* Offline manifest using the request parameter `wcmmode` for html entry, making it uncacheable.

* Empty dynamic embedded sequence sometimes caused blank screen.

* Player now report its playback status.

* Video was playing in `Tiny mode` and not played as full screen video on device and the issue is fixed now.

### Released AEM Screens Players {#released-aem-screens-players}

The following AEM Screens Players are released for AEM 6.5 Feature Pack 9:

* ChromeOS
* Windows
* Tizen
* Android
* Linux

#### AEM Screens Player Downloads  {#aem-screens-player-downloads}

To download the latest AEM Screens player and learn more about the bug fixes, refer to **[AEM Screens Player Downloads](https://download.macromedia.com/screens/index.html)**.
