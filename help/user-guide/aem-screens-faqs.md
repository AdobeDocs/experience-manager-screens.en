---
title: AEM Screens FAQs
description: Read answers to FAQs related to an AEM Screens project.
feature: Digital Signage, Content
role: Developer
level: Intermediate
exl-id: 67204f04-5535-407c-bd4d-fabfbf850411
---
# AEM Screens FAQs {#aem-screens-faqs}

This topic provides answers to commonly asked FAQs related to an AEM Screens project.

## Blank Screen Issue {#blank-screen}

>[!NOTE]
>The listed mandatory checks that primary support or customer-side support should try before raising an issue.

### 1. What should be the First aid troubleshooting steps for any customer facing a black screen or non-playing content? {#troubleshooting-blank-screen}

* Check if the channel preview is working.
* Check if the display preview is working
* Try registering the player as a browser extension on your system to that same display and check if it is working.
* With the player running on your system, navigate to `http://localhost:24502`. Check if all the content is downloaded correctly.
* Check the assets so you can ensure that the appropriate renditions are created and the correct rendition is being played.
* Check for any scheduled content and if the times are correct. Check if the time set up in the player is correct.
* Inspect the player console logs and check for any errors. Right-click and inspect to see the console logs. If you are using the Windows Player, press `CTRL + ALT +I` to bring up dev console to view the logs.

### 2. How to resolve Grey Screen Issue in AEM Screens by Creating a Default Channel or Schedule?

To avoid the blank or gray screens in the field, create a default global channel or schedule, assigned to every display with the least priority 1. In case something goes wrong with content updates because the players have this content already cached on the disk. It should play fine and avoid the gray screens.

All other content, such as channels or schedules, priority greater than 1, so the other content takes priority and global channel or schedule content (with priority 1) only plays as a fall-back option.

## Channel Management {#channel-management}

### 1. What is the difference between an online and an offline channel? {#what-is-the-difference-between-an-online-and-an-offline-channel}

An ***Online Channel*** shows the updated content in the real-time environment whereas an ***Offline Channel*** shows the cached content.

### 2. How do I make a channel online? {#how-do-i-make-a-channel-online}

Click the channel and navigate to channel properties from the action bar. Check **Developer mode (force channel to be online)** under **Channel** tab to make the channel online.

### 3. What is the use of the Channel Role field? {#what-is-the-use-of-the-channel-role-field}

The Channel Role is the abstraction of the actual channel that is run so that the author can focus on the generic experience directly. You can think of it as a kind of tag that uniquely identifies the channel in its context (display or schedule).

### 4. How does actual channel resolution happen? {#how-does-actual-channel-resolution-happen}

For *static references*, the resolution just follows the path that is specified.

For *dynamic references*, the resolution occurs once the channel is assigned to the display (not the schedule). The display path becomes the context for the channel and the resolution happens as follows (highest to lowest priority):

1. The display has a child node that matches the referenced channel name
1. The display has a sibling node that matches the referenced channel name
1. The parent location of the display has a child node that matches the referenced channel name
1. The grand-parent location of the display has a child node that matches the referenced channel name

And so on, until you reach the locations folder. Stop there at the moment (so you cannot reference a channel that would be in the channels folder for instance, only channels in the location subtree).

### 5. How to set up Custom clientlib offline configuration in AEM Screens Channel?

When using a built custom client-side code `clientlib` in an AEM Screens channel, the following steps are necessary. The steps make sure that the `clientlib` files are loaded successfully in the channel (`manifest.json`) and contains the path of the `clientlib`.

Follow the steps below from the channel editor:

1. Click a channel, then click **Edit** from the action bar.
1. Click the component where you want to add the custom `clientlib`.
1. Click the configure button (the wrench icon). 
1. Navigate to the **Offline Config** tab and add the path to your custom clientlib in **Client-side Libraries**.

## Device Registration {#device-registration}

### 1. If I discover endpoints such as requests for device onboarding and registration, I can script many devices and register these devices. Besides locking it to a branch Wi-Fi, is it possible to secure these requests? {#if-i-discover-endpoints-such-as-requests-for-device-onboarding-and-registration-i-can-script-a-large-number-of-devices-and-register-these-devices-besides-locking-this-to-a-branch-wi-fi-is-it-possible-to-secure-these-requests}

Currently Registration is only possible on the author instance. Although the registration service is unauthenticated, it only creates a pending device in AEM and does not actually register the device or assign any display.

To register a device (creating a user for the device in AEM), authenticate to AEM and manually follow the registration wizard to complete registration. Theoretically, a malicious user may create several pending devices but cannot register any if they do not have an AEM login.

### 2. Is there a way to transform HTTP GET requests into HTTP POST with some form of authentication? {#is-there-a-way-to-transform-http-get-requests-into-http-post-with-some-form-of-authentication}

The registration request is a POST request.

It is recommended to obtain the device ID from the session rather than passed as a parameter. Doing so would clean up the server logs, browser cache, and so on. It is not a security issue. Semantically. GET is used when there is no state change on the server and POST is used when there is a state change.

### 3. Is there a way to decline a device registration request? {#is-there-a-way-to-decline-a-device-registration-request}

You cannot decline the registration requests. Instead, the registration requests should expire after a timeout that is configured in `Adobe Experience Manager Web Console`. By default, this value is set to one day and is stored in a memory cache.

## Device Monitoring and Health Reports {#device-monitoring-and-health-reports}

### 1. How do I troubleshoot, if my AEM Screens Player shows a blank screen?

Check for the following possibilities to troubleshoot the blank screen issue:

* AEM is unable to push the Offline Content
* The channel does not have any content
* None of the assets are scheduled to show at the current time

### 2. What do I do if the AEM Screens Player cannot register and its state is displayed as Failure? 

Enable the Apache Sling Referrer Filter Allow Empty. Required for optimal operation of the control protocol between AEM Screens Player and AEM Screens server.

1. Navigate to **Adobe Experience Manager Web Console Configuration**
1. Check the **allow.empty** option.
1. Click **Save**.

### 3. How to troubleshoot if while registering an AEM Screens Player, the device shows FAILURE and the console logs display an ENAME_NOT_FOUND error?

This issue may occur if the player is unable to find the AEM Screens Server DNS. You can try using the IP address to connect. To obtain the IP of the server, use: *arp <server_dns_name>*.

### 4. Does AMS recommend implementing an Android&trade; Watchdog on all Devices? Is the Watchdog (Cordova) plugin included as part of the APK? {#does-ams-recommend-implementing-an-android-watchdog-on-all-devices-is-the-watchdog-cordova-plugin-included-as-part-of-the-apk}

A cross-platform Android&trade; watchdog using pure Android&trade; APIs is already a part of the apk. No additional software is needed. However, depending on the device that you use, you can resign the apk to obtain system privileges for a full power cycle (`Powermanager` api), if necessary. If it is not resigned using the manufacturer keys, it quits and restarts the application, but does not power cycle.

For more information on how to implement Android&trade; Player, see [**Implementing Android&trade; Player**](implementing-android-player.md).

### 5. What third-party remote monitoring and alerting tools (software) does Adobe/AMS recommend for monitoring each device? {#what-third-party-remote-monitoring-and-alerting-tools-software-does-adobe-ams-recommend-for-monitoring-each-device}

Depending on what you desire out of the monitoring and alerts, a new feature AEM Screens Notifications service notifies you if a device has not pinged in a while. The third-party tools depend on your Operating System (OS), its capabilities, and the customer's specific needs.

For more information on where you can monitor device activity, see [**AEM Scree ns Notifications Service**](screens-notifications-service.md).

## AEM Screens Player

### 1. How to Install ChromeOS player as Chrome browser plugin? {#how-to-install-chromeos-player-as-chrome-browser-plugin}

ChromeOS player can be installed as a Chrome browser plugin in developer mode without requiring an actual Chrome Player device. For installation, follow the steps below:

1. Click [here](https://download.macromedia.com/screens/) to download the latest Chrome Player.
1. Unzip and save it on disk.
1. Open the Chrome browser and click **Extensions** from the menu or directly navigate to ***chrome://extensions***.
1. Switch on the **Developer mode** from the top-right corner.
1. Click **Load Unpacked** from the top-left corner and load unzipped Chrome Player.
1. If available in the list of extensions, check the **AEM Screens Chrome Player** plugin.
1. Open a new tab and click the **Apps** icon from the top-left corner, or directly navigate to ***chrome://apps***.
1. Click the **AEM Screens** Plugin. By default, the player is launched in full screen mode. Press **Esc** to exit full screen mode.

### 2. How to troubleshoot if Screens player is unable to authenticate through publishing instance with a custom error handler?

When AEM Screens Player starts, it makes a request to ***/content/screens/svc.ping.json***, when the player gets a 404 error. The player initiates an authentication request to authenticate against the publishing instance. If there is a custom error handler in the publish instance, make sure that you return the 404 status code for an anonymous user on ***/content/screens/svc.ping.json***.

### 3. How to set the device screen stay on in an Android&trade; Player? {#how-to-set-the-device-screen-stay-on-in-an-android-player}

Follow the steps below to turn on Stay Awake in on any Android&trade; player:

1. Navigate to Android&trade; player settings > **About**.
1. Tap seven times on the build number so you can enable **Developer Options** in **Settings**.
1. Navigate to **Developer Options**.
1. Enable **Stay Awake**.

### 4. How to enable window mode for the Windows Player?{#enable-player}

There is no window mode in Windows Player. It is always in full screen mode.

### 5. How to troubleshoot if an AEM Screens Player continuously sends login requests?

Follow the steps below to troubleshoot an AEM Screens Player that continuously sends requests to `/content/screens/svc.json` and `/libs/granite/core/content/login.validate/j_security_check`:

1. When AEM Screens Player starts, it requests to `/content/screens/svc.json`. When the player gets a 404 status code in the response, it initiates an authentication request by using `/libs/granite/core/content/login.validate/j_security_check` against the *publish* instance. If there is a custom error handler in the *publish* instance, make sure to return the 404 status code for anonymous user on `/content/screens/svc.json` or `/content/screens/svc.ping.json`.

1. Check if your Dispatcher configuration allows these requests in the `/filters`.
   
   See [Configuring Screens Filters](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#step-configure-screens-filters) for more details.

1. Check if your Dispatcher rewrite rules are rewriting any of the screen paths to a different path.

1. Check if you have `/etc/map` rules on the *author* or *publish* instance and screens paths are matched to `sling:match` and internally redirected to a different path. Resolving the exact url in `/system/console/jcrresolver` helps in identifying if the *publish* instance is rewriting these URLs to any other path.

1. Check if the Apache Sling Resource Resolver Factory configuration is causing internal rewrites.

### 6. How to get the details of the display and device from the player API?

You can get the details of the display and device by way of:

* **an internal JS API**
* **a ContextHub store**: Three ContextHub stores are defined in `/libs/screens/clientlibs/contexthub` to expose channels, device and, display info.

   Follow the steps below to use these ContentHub store values:

   * Edit the channel properties and set the ContextHub path in the personalization tab to the value (as mentioned above)
   * In the channel JS, you can use:

      ```shell
         ContextHub.getStore('screens-device');
         ContextHub.getStore('screens-display');
         ContextHub.getStore('screens-channels');
      ```

## General Troubleshooting Tips {#general-troubleshooting-tips}

### 1. How to Disable Livefyre to avoid A/P Screens Error?

Disable Livefyre to avoid log errors by doing the following.

1. ***Disable Livefyre bundle:***

    * Navigate to `https://<host>:<port>/system/console/bundles`.
    * Search for the AEM Livefyre bundle: `com.adobe.cq.social.cq-social-livefyre`.
    * Click **Stop**.

1. ***Disable Livefyre poller:***

    * In CRXDE Lite, navigate to `/etc/importers/polling/livefyre-poller/jcr:content`.
    * Add a property *enabled* type *Boolean*.
    * Set **Enabled property** to be **false**.

### 2. How to Add Oak Index information? {#add-oak-index-info}

AEM Screens creates index definitions for the queries used by the product. 
If there are any *Query Traversal WARNs* in the `error.log`, create a custom index for your query. See [Configuring the Indexes](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/queries-and-indexing#configuring-the-indexes) for more details.

You can also see an additional resource on [Oak Documentation](https://jackrabbit.apache.org/oak/docs/query/lucene.html).


### 3. What is required to configure v3 Manifests? {#configure-v3}

For enabling v3 Manifest, do the following:

* Update Dispatcher.
  See [Configuring Dispatcher for Manifest Version v3](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/administering/dispatcher-configurations-aem-screens#configuring-dispatcherv3) for more details.

* Update Custom Component.
   See [Template for Custom Handlers](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/developing/developing-custom-component-tutorial-develop#custom-handlers) for more details.

* Disable ContentSync in `/system/console/configMgr/configMgr/com.adobe.cq.screens.offlinecontent.impl.ContentSyncCacheFeatureFlag`.

* Enable SmartSync in `/system/console/configMgr/com.adobe.cq.screens.offlinecontent.impl.OfflineContentServiceImpl`.

* Edit `channel/experience fragment/page components`.

* Navigate to the **Offline Config** tab.

* Enter `clientlibs `and folders for static files that must be added to the manifest.

### 4. What should you do, if, after the package screens-cloud-ams-pkg-0.0.20, screens-cloud-ams-pkg-0.0.16 and the screens core bundles are installed but not active?

Install a minimum version of AEM 6.5 Feature Pack 8 for the AMS connector to work. See [Availability](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/release-notes/release-notes-fp-202105#availability) so you can get the minimum version of AEM Screens Feature Pack.

### 5. How to configure CQ Link Externalizer service in Screens?

The service is used to define the public hostname for the author and publish instances, and the values are then used to update the device server URLs and also for ContextHub targeting.

CQ Link Externalizer service in Screens can be configured in the following way:

1. Navigate to `http://localhost:4502/system/console/configMgr`
1. Day CQ Link Externalizer
1. Change the hostname for the `author/publish` entries as needed