---
title: Implementing Cloud Player
description: Learn about the implementation of the Cloud Player.
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 184168f5-6070-4c33-a2c5-5429061dac75
---
# Implementing Cloud Player  {#implementing-cloud-player}

AEM Screens has traditionally offered distinct native player applications for various platforms including ChromeOS, Windows, Android&trade;, and `Tizen`. However, in response to the evolving needs of users, Adobe introduced an innovative solution - the AEM Screens Cloud Player.

The Cloud Player represents a significant departure from Adobe's previous native applications. It is a Progressive Web App (PWA), hosted on a server. This transformative approach empowers customers with a platform-independent player that runs directly within a web browser.

Accessing the Cloud Player is as simple as visiting `https://player.adobescreens.com`. Users can install it on their device, regardless of the platform, and enjoy seamless digital signage experiences. The Cloud Player's compatibility hinges on the presence of a modern browser with PWA support, ensuring consistent performance across various devices. Say goodbye to manual updates and hello to a player that automatically delivers fixes and features, ensuring you always have the latest capabilities at your fingertips. This shift to a PWA-based Cloud Player marks an exciting evolution in Adobe's digital signage offerings, making it more accessible, versatile, and user-friendly than ever before.

This section describes how to implement the Cloud Player.

>[!NOTE]
>
>The Cloud Player's compatibility requires a modern browser with PWA support to ensure consistent performance across various devices.

## Installing Cloud Player {#installing-cloud-player}

Cloud Player Installation may vary on different platforms. In general, any platform having a modern browser can run the cloud player application by following these steps:

1. Open the browser and enter the [cloud player URL](https://player.adobescreens.com/content/dam/universal-player/firmware.html) in the address bar.
1. The browser checks if the cloud player is installable, and then shows an install icon in the address bar.

    ![image](/help/user-guide/assets/cloud-player-install.png)

1. Click the install icon and install button on the confirmation dialog box. Cloud Player is installed as a standalone application on your device and can be launched using an icon.

>[!NOTE]
>
>### Cloud Player Install Option {#cloud-player-install-option}
>
>1. The install option for a PWA is also known as "Add to Home Screen" or A2HS feature. Support for installing PWAs from the web varies by browser and by platform. 
>1. Every browser has different criteria to check if the PWA app is installable or not. Generally browser checks these (more details here): 
>
>    * If the application has a manifest json file with minimal required keys for installing the app on the platform that is, name, icons, start_url, display
>    * If the application has a service worker file with a fetch event listener
>    * App must be served over https
>
>1. Install option might be visible at different locations in different browsers and device types. Some browsers might hide the install icon in options menu bar.

## Bulk provisioning Cloud Player {#bulk-provisioning}

To do bulk provisioning of cloud player on multiple devices:

1. Choose an MDM solution that supports running a browser with a URL in Kiosk mode.
1. You can apply the same configurations to all the devices by following these steps:

    1. Host config.json on a server such that it is accessible such as: `https://<config_server_host>/config.json`
    1. To install cloud player and apply the hosted configurations, use cloud player URL such as: `https://player.adobescreens.com?playerConfigAddress=https://<config_server_host>`
    1. Cloud Player application looks for config.json at the root of <config_server_host>, parse the config.json to get the custom configurations and apply those configurations.
    1. These configurations are applied on every reload of the player.

## Bulk Provisioning on Chrome OS {#bulk-provisioning-chrome}

Learn more about bulk provisioning on Chrome OS, see [Install Cloud Player on Chrome OS](https://www.adobe.com/go/aem_screens_cloud_player_en).

## Configuration required on AEM instances {#bulk-provisioning-config-aem}

Based on type of the AEM instance, click one of the following guides to enable CORS b/w AEM  & cloud player: 
* [AEM On-Premises/AMS](https://www.adobe.com/go/aem_screens_cors_ams_en)
* [AEM Cloud Service](https://www.adobe.com/go/aem_screens_cors_aemaacs_en)

>[!NOTE]
>
>## Chrome Apps Deprecation by Google
>
>1. Chrome Apps on Chrome OS Hardware:
>
>   Google has been actively deprecating Chrome Apps in favor of PWA apps, with a planned migration until January 2025. Therefore, the AEM Screens Player app on Chrome OS ceases to function based on the shared timeline. Adobe urges users who are currently using Chrome Player in production to plan for transitioning to the Screens Cloud Player.
>
>1. Chrome Extension Player on Mac, Windows, and Linux&reg;:
>
>   Due to Google's deprecation process, starting from Google Chrome version 114, the Screens Chrome Extension Player is no longer supported. Adobe advises that you transition to their Screens Cloud Player for all your development and testing requirements.

## Offline Support for External Content Retrieval {#offline-support}

In various usage scenarios, channels may require the retrieval of content from an external source (for example, weather widgets or Commerce integrated Single Page Applications) that cannot inherently provide offline support. To enable offline functionality for these specific use cases, the Cloud Player offers support for custom header.

Cloud Player employs a Network First cache strategy, which means it attempts to fetch content from the network (then update the cache with latest), falling back to cached content if available. To implement offline support for such content retrieval, the custom header must be included in the request. Then, the request with the custom header is cached on the player, facilitating offline access to the content while maintaining the Network First cache strategy.

```
// Sample fetch request with the 'X-Cache-Strategy' header
fetch(externalUrl, {
  headers: {
    'X-Cache-Strategy': 'external-cache'
  }
})
  .then(response => {
    // Handle the response, which may be from the network or cache.
    // Your logic here.
  })
  .catch(error => {
    // Handle any errors that may occur during the fetch operation.
    // Your error handling logic here.
  }); 
```

## Feedback

Adobe values your feedback. Share your thoughts with us through this [form](https://forms.office.com/pages/responsepage.aspx?id=Wht7-jR7h0OUrtLBeN7O4TFE0b_GjstOj6I1uGs9vLpURVdWWklQQTZZRTFVNEhRVlBWWldMWlJXOC4u).
