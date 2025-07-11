---
title: Implementing Chrome OS Player
description: Learn about the implementation of the Chrome OS Player using the Chrome Management Console.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 4f16605b-aec1-45fa-a110-0af6925b74b0
---
# Implementing Chrome OS Player {#implementing-chrome-os-player}

This section describes how to implement the Chrome OS Player using the Chrome Management Console.

## Using Chrome Management Console {#using-chrome-management-console}

Follow the steps below to set up the Chrome management console:

1. Register for the Chrome Management Console. You must obtain a license for Chrome Management Console. Contact [Google Support](https://support.google.com/chrome/a/answer/1375678?hl=en&ref_topic=2935995) to Manage Chrome device settings for more information.
1. Enroll your Chrome OS Device into the domain and wait for 15 minutes for the device to sync with the Chrome Management Console. To learn more about enrolling Chrome device, click [here](https://support.google.com/chrome/a/answer/1360534?hl=en).
1. The Chrome Player is available in the Chrome Web Store.

>[!NOTE]
>
>A device management solution such as the Chrome Management Console is recommended for deployment and management of Chrome OS Devices. Although this document provides implementation for Chrome Management Console there are other vendors who claim to provide similar functionality. Contact the vendor of your device management software.

## Naming Chrome OS Player {#name-chrome}

You can assign a user-friendly device name to your Chrome Player, thus sending the assigned device name to Adobe Experience Manager (AEM). This capability not only lets you name your Chrome Player but also lets you easily assign appropriate content.

>[!NOTE]
>You can choose the Player name only before registration. After the Player is registered, the Player name cannot be changed anymore.

Follow the steps below to configure the name in Chrome Player:

1. You can optionally allow Audio-Video integrators or IT administrators to set the Asset ID and location as part of enterprise enrollment.

   ![image](/help/user-guide/assets/chrome-device/chrome1.png)

1. You are presented with the options when you can enroll the device.

   ![image](/help/user-guide/assets/chrome-device/chrome2.jpg)

1. You can set the Asset ID as part of enterprise enrollment and in the Chrome Management Console.

   ![image](/help/user-guide/assets/chrome-device/chrome3.png)

    >[!NOTE]
    >Chrome Players must be enrolled in enterprise enrollment and the Chrome Player must be deployed through Chrome Management Console, otherwise the Asset ID returns blank (for example, Chrome as an extension). The device name is only recorded at the time of registration. Future changes do not get picked up by Adobe Experience Manager (AEM).

### Enabling Kiosk Mode {#enabling-kiosk-mode}

Follow the steps below to enable the Kiosk mode:

1. Log in to the Chrome Developer Console.

   ![screen_shot_2017-12-08at20303pm](assets/screen_shot_2017-12-08at20303pm.png)

1. Browse to **Device Management** > **Chrome Management** > **Device Settings**.
1. Scroll down to **Kiosk Settings** and click **Manage Kiosk Applications**.

   ![kiosk](assets/kiosk.png)

1. Click the AEM Screens Player from the Chrome Web Store.

   >[!NOTE]
   >
   >A recently published app may take about 15 minutes to appear in this list.

1. Click **AEM Screens Player** from the **Auto Launch Kiosk App** dropdown.

   It may take a few minutes depending on the network for the changes to take effect. A reboot is recommended.

#### Checking Remote Device Status {#checking-remote-device-status}

1. Log in to the Chrome Developer Console.
1. Browse to **Device Management** > **Chrome Devices** and click the device you want to control.
1. Click **System Activity and troubleshooting**.
1. Check the **Reboot Device** and **Screen Capture** properties of the device. You can also check the device status and health information.

>[!NOTE]
>
>These settings can be enabled several minutes after the device is enrolled. Each option can become enabled over time.

### Configuring Remote Configuration of Chrome OS Players {#configuring-remote-configuration-of-chrome-os-players}

The AEM Screens Player is a Kiosk enabled application that also enables Remote Policy Configuration for Chrome OS Players.

Follow the steps below to configure the various options of the player:

1. Log in to the Chrome Management Console.
1. Click **Device Management** > **Chrome Management** > **App Management**. The AEM Screens Player displays in the list.
1. Click the application **AEM Screens Player**.
1. Click **Kiosk settings** and click your org (*if using a test environment*).
1. Click **upload configuration file** and upload the configuration policy (*JSon file*).
1. Click **Save**. Reboot the device so you can sync the policy.

>[!NOTE]
>
>Reboot the device so you can sync policy changes.

#### Example Policy JSON file {#example-policy-json-file}

```java
{
  "server": {
    "Value": "https://aemscreensdemo.adobeitc.com"
  },
  "resolution": {
    "Value": "auto"
  },
  "rebootSchedule": {
    "Value": "at 4:00am"
  },
  "enableAdminUI": {
    "Value": true
  },
  "enableOSD": {
    "Value": true
  },
  "enableActivityUI": {
    "Value": true
  }
}
```

### Policy attributes and purpose {#policy-attributes-and-purpose}

The following table summarizes the policies with their functions.

| **Policy Name** |**Purpose** |
|---|---|
| server |The URL to the Adobe Experience Manager (AEM) server. |
| registrationKey |Used for bulk registration of devices using pre-shared key. |
| resolution |The resolution of the device. |
| rebootSchedule |The schedule to reboot the player.|
| enableAdminUI |Enable the Admin UI to configure the device on site. Set to false once it is fully configured and in production. |
| enableOSD |Enable the channel switcher UI for users to switch channels on the device. Consider setting it to false once it is fully configured and in production. |
| enableActivityUI |Enable so you can show the progress of activities, such as download and sync. Enable for troubleshooting and disable once it is fully configured and in production. |
| cloudMode |Set to true if you want the Chrome Player to connect to Screens as a Cloud Service. Set to false to connect to AMS or on-prem AEM. |
| cloudToken |Registration token to register against Screens as a Cloud Service. |

>[!NOTE]
>
>Policy configurations are strictly enforced and the player's Admin UI does not override manually. To allow manual player configuration for a particular policy, do not specify the policy in the ***policy configuration***. For example, if you want to allow manual configuration for reboot schedule, do not specify the key ***rebootSchedule*** in the policy configuration.

### Using the Screens Remote Control {#using-remote-control}

AEM Screens provides Remote Control functionality. Learn more about this feature here: [Screens Remote Control](implementing-remote-control.md)
