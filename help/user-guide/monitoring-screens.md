---
title: Troubleshooting Device Control Center
description: Learn how to monitor and troubleshoot performance for your AEM Screens Player activity and device using the Device dashboard.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: troubleshoot
docset: aem65
feature: Digital Signage, Content, Players
role: Developer
level: Intermediate
exl-id: 57105d6d-51ff-44ca-bbf2-ae9cce8addd0
---
# Troubleshooting Device Control Center {#troubleshooting-device-control-center}

You can monitor and troubleshoot performance for your AEM Screens Player activity and device using the Device dashboard. This page provides information about how to monitor and troubleshoot perceived performance problems for Screens player and the assigned devices.

## Monitor and Troubleshoot from Device Control Center {#monitor-and-troubleshoot-from-device-control-center}

You can monitor the activity and hence troubleshoot your AEM Screens Player, usingtheDevice Dashboard.

### Device Dashboard {#device-dashboard}

Follow the steps below to navigate to the device dashboard:

1. Navigate to the device dashboard from your project, for example, ***Test Project*** > ***Devices***.

   Click **Devices** and **Device Manager** from the action bar.

   ![screen_shot_2019-09-03at13823pm](assets/screen_shot_2019-09-03at13823pm.png)

1. The list displays the assigned and unassigned devices, as shown in the figure below.

   ![screen_shot_2019-09-05at12823pm](assets/screen_shot_2019-09-05at12823pm.png)

1. Click the device (**NewTestDevice**) and click **Dashboard** from the action bar.

   ![screen_shot_2019-09-05at13341pm](assets/screen_shot_2019-09-05at13341pm.png)

1. The page shows the device information, activity, and the device details that let you monitor the device activities and functions.

   ![screen_shot_2019-09-05at13700pm](assets/screen_shot_2019-09-05at13700pm.png)

### Monitor Device Activity {#monitor-device-activity}

The **Activity** panel shows the last ping of your AEM Screens Player with the timestamp. The last ping corresponds to the last time that the device contacted the server.

![chlimage_1](assets/chlimage_1.png)

Also, click **Collect Logs** from the top-right hand corner of the **Activity** panel to view the logs for your player.

### Update Device Details {#update-device-details}

Check the **Device Details** panel so you can view the device IP, Storage usage, firmware version, and the player uptime for your device.

![chlimage_1-1](assets/chlimage_1-1.png)

Also, click **Clear Cache** and **Update** to clear the cache of your device and update the [firmware](screens-glossary.md) version respectively from this panel.

Also, click **...** from the top-right corner of the **Device Details** panel to restart or refresh the status of your player.

![chlimage_1-2](assets/chlimage_1-2.png)

### Update Device Information {#update-device-information}

Check the **DEVICE INFORMATION** panel. Here you can view the configuration update, device model, device OS, and the shell information.

![screen_shot_2019-09-05at13853pm](assets/screen_shot_2019-09-05at13853pm.png)

Also, click (**...**) from the top-right corner of the Device Information panel to view properties or update the device.

![screen_shot_2019-09-05at14017pm](assets/screen_shot_2019-09-05at14017pm.png)

Click **Properties** so you can view the **Device Properties** dialog box. You can edit the device title or choose the option for configuration updates as **Manual** or **Automatic**.

>[!NOTE]
>
>To learn more about the events associated with device's automatic or manual updates, see the section ***Automatic versus Manual Updates from the Device Dashboard*** in [Managing Channels](managing-channels.md).

![screen_shot_2019-09-05at14112pm](assets/screen_shot_2019-09-05at14112pm.png)

### View Player Screenshot {#view-player-screenshot}

You can view the player screenshot from the device from the **PLAYER SCREENSHOT** panel.

Click (**...**) on the top-right corner of the Player Screenshot panel and click **Refresh Screenshot** to view the snapshot of the running player.

![screen_shot_2019-09-05at14205pm](assets/screen_shot_2019-09-05at14205pm.png)

### Manage Preferences {#manage-preferences}

The **PREFERENCES** panel allows the user to change preferences for **Admin UI**, **Channel Switcher**, and **Remote Debugging** for the device.

>[!NOTE]
>To learn more about these options, See [AEM Screens Player](working-with-screens-player.md).

![screen_shot_2019-09-05at14250pm](assets/screen_shot_2019-09-05at14250pm.png)

Also, click **Settings** from the top-right corner to update device preferences. You can update the following preferences:

* **Server URL**
* **Resolution**
* **Reboot Schedule**
* **Max No. of log files to keep**
* **Log Level**

![screen_shot_2019-09-05at14511pm](assets/screen_shot_2019-09-05at14511pm.png)

>[!NOTE]
>You can click any one of the following Log levels:
>
>* **Disable**
>* **Debug**
>* **Info**
>* **Warning**
>* **Error**

![screen_shot_2019-09-05at15645pm](assets/screen_shot_2019-09-05at15645pm.png)

## Troubleshoot OSGi Settings {#troubleshoot-osgi-settings}

Enable the empty referrer to allow the device to post data to the server. For example, if the empty referrer property is disabled, the device cannot post a screenshot back.

Currently some of these features are only available if the *`Apache Sling Referrer Filter Allow Empty`* is enabled in the OSGi configuration. The dashboard may display a warning that security settings may prevent some of these features from working.

Follow the steps below to enable the Apache Sling Referrer Filter Allow Empty

1. Navigate to **Adobe Experience Manager Web Console Configuration**, that is, `https://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter`.
1. Check the **allow.empty** option.
1. Click **Save**.

![chlimage_1-3](assets/chlimage_1-3.png)

### Recommendations {#recommendations}

The following section recommends monitoring the network links, servers, and players to understand the health and react to issues.

AEM provides built-in monitoring for:

* *Heartbeat* every 5 seconds to indicate that the AEM Screens Player is in operation.
* *Screenshot* from the Player that shows what is displayed on the Player.
* The *AEM Screens Player Firmware* version is installed on the Player.
* *Free storage space* on the Player.

Recommendations for remote monitoring with third-party software:

* CPU usage in Players.
* Check if the AEM Screens Player process is running.
* Remote restart/reboot of the Player.
* Real-time Notifications.

It is recommended to deploy the Player hardware and OS in a way that allows remote login to diagnose issues and restart the Player.

#### Other Resources {#additional-resources}

See [Video Playback Configuration and Troubleshooting](troubleshoot-videos.md) if you want to debug and troubleshoot videos playing in your channel.
