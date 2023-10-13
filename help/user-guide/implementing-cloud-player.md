---
title: Implementing Cloud Player
seo-title: Implementing Cloud Player
description: Follow  this page to learn about the implementation of the Cloud Player.
seo-description: Follow  this page to learn about the implementation of the Cloud Player.
uuid: eee84286-fa81-475c-ad6f-db2d6cf1fed5
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
discoiquuid: 1be944f0-02ed-48c6-98bc-504d758ff866
feature: Administering Screens
role: Admin
level: Intermediate
---
# Implementing Cloud Player  {#implementing-cloud-player}

This section describes how to implement the Cloud Player.

>[!NOTE]
>
>The Cloud Player's compatibility requires a modern browser with PWA support to ensure consistent performance across various devices.

## Installing Cloud Player {installing-cloud-player}

Cloud Player Installation may vary on different platforms. In general, any platform having a modern browser can run the cloud player application by following these steps:

1. Open the browser and enter the [cloud player URL](https://player.adobescreens.com) in the address bar.
1. The browser checks if the cloud player is installable and then show an install icon in the address bar.

![image](/help/user-guide/assets/cloud-player-install.png)

1. Click on the install icon and install button on the confirmation dialog. This way cloud player will be installed as a standalone application on your device and can be launched using an icon.

### Cloud Player Install Option {#cloud-player-install-option}

1. The install option for a PWA is also known as "Add to Home Screen" or A2HS feature.  Support for installing PWAs from the web varies by browser and by platform. 
1. Every browser has different criteria to check if the PWA app is installable or not. Generally browser checks these (more details here) - 
    * If the application has a manifest json file with minimal required keys for installing the app on the platform i.e., name, icons, start_url, display
    * If the application has a service worker file with a fetch event listener.
    * App must be served over https.
1. Install option might be visible at different locations in different browsers and device type. Some browser might hide the install icon in options menu bar.

## Bulk provisioning Cloud Player {#bulk-provisioning}

To do bulk provisioning of cloud player on multiple devices:

1. Choose a MDM solution that supports running a browser with a URL in Kiosk mode.
1. You can apply the same configurations to all the devices by following these steps:
    1. Host config.json on a server such that it is accessible such as:  https://<config_server_host>/config.json
    1. To install cloud player and apply the hosted configurations, use cloud player URL such as: https://player.adobescreens.com?playerConfigAddress=https://<config_server_host>
    1. Cloud Player application looks for config.json at the root of <config_server_host>, parse the config.json to get the custom configurations and apply those configurations.
    1. These configurations will be applied on every reload of the player.

## Bulk Provisioning on Chrome OS {#bulk-provisioning-chrome}

To learn more about bulk provisioning on Chrome OS see: [Install Cloud Player on Chrome OS](https://main--screens-franklin-documentation--hlxscreens.hlx.page/updates/cloud-player/guides/chromeos-install-cloud-player).

## Configuration required on AEM instances {#bulk-provisioning-config-aem}

Based on type of the AEM instance, select one of the following guides to enable CORS b/w AEM  & cloud player: 
* [AEM On-Premises/AMS](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-onpremandams)
* [AEM Cloud Service](https://main--screens-franklin-documentation--hlxscreens.hlx.live/updates/cloud-player/guides/cors-settings-aem-cs)
 