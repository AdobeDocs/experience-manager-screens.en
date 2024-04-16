---
title: Implementing Android&trade; Player
description: Learn about the implementation of Android&trade; Watchdog, a solution that lets you recover the Android&trade; player from crashes.
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: administering
docset: aem65
feature: Administering Screens, Android Player
role: Admin
level: Intermediate
exl-id: d1331cb8-8bf6-4742-9525-acf18707b4d8
---
# Implementing Android&trade; Player {#implementing-android-player}

This section describes configuring Android&trade; player. It provides information of the configuration file and the options available and recommendations as to which settings to use for development and testing.

Also, **Watchdog** is a solution to recover the player from crashes. An application must register itself with the watchdog service and then periodically send messages to the service that it is alive. In case the watchdog service does not receive a keep-alive message within a stipulated time, the service attempts to reboot the device for a clean recovery (if it has the sufficient privileges) or restart the application.

## Installing Android&trade; Player {#installing-android-player}

To implement Android&trade; Player for AEM Screens, install Android&trade; Player for AEM Screens.

Visit the [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/) page.

### Setting up Environment for AEM Screens 6.5.5 Service Pack {#fp-environment-setup}

>[!NOTE]
>Set up an environment for Android&trade; player if you are using AEM Screens 6.5.5 Service Pack.

Set the **SameSite attribute for the login-token cookies** from **Lax** to **None** from **Adobe Experience Manager Web Console Configuration** on all AEM author and publish instances.

Follow the steps below:

1. Navigate to **Adobe Experience Manager Web Console Configuration** using `http://localhost:4502/system/console/configMgr`.

1. Search for *Adobe Granite Token Authentication Handler*.

1. Set the **SameSite attribute for the login-token cookies** from **Lax** to **None**.
   ![image](/help/user-guide/assets/granite-updates.png)

1. Click **Save**.


### Ad-Hoc Method {#ad-hoc-method}

The Ad-Hoc method lets you install the latest Android&trade; Player (*.exe*). Visit [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/) page.

After you download the application, follow the steps on the player to complete the ad-hoc installation:

1. Long-press on the top-left corner to open the admin panel.
1. Navigate to **Configuration** from the left action menu and enter the location (address) of the AEM instance you wish to connect to and click **Save**.

1. Navigate to the **Device** **Registration** link from the left action menu so you can check the status of the device registration process.

>[!NOTE]
>
>If the **State** is **REGISTERED**, you can see that the **Device id** field is populated.
>
>If the **State** is **UNREGISTERED**, you can use the **Token** to register the device.

## Implementing Android&trade; Watchdog {#implementing-android-watchdog}

Due to Android&trade;'s architecture, rebooting the device requires that the application has system privileges. To do this, sign the apk using the manufacturer's signing keys, otherwise watchdog restarts the player application and not reboot the device.

### Signage of Android&trade; `apks` using Manufacturer Keys {#signage-of-android-apks-using-manufacturer-keys}

To access some of the privileged APIs of Android&trade; such as *PowerManager* or *HDMIControlServices*, sign the Android&trade; `apk` using the manufacturer's keys.

>[!CAUTION]
>
>Pre-requisites:
>
>You should have the Android&trade; SDK installed before you perform the following steps.

Follow the steps below to sign the Android&trade; apk using the manufacturer's keys:

1. Download the apk from Google Play or from [AEM Screens Player Downloads](https://download.macromedia.com/screens/) page
1. Obtain the platform keys from the manufacturer so you can get a *pk8* and a *pem* file

1. Locate the `apksigner` tool in Android&trade; sdk using find `~/Library/Android/sdk/build-tools -name "apksigner"`
1. `<pathto> /apksigner sign --key platform.pk8 --cert platform.x509.pem aemscreensplayer.apk`
1. Find the path to the zip align tool in Android&trade; sdk
1. `<pathto> /zipalign -fv 4 aemscreensplayer.apk aemscreensaligned.apk`
1. Install ***aemscreensaligned.apk*** using adb install to the device

## Understanding Android&trade; Watchdog Services {#android-watchdog-services}

The cross-Android watchdog service is implemented as a Cordova plugin using *AlarmManager*.

The following diagram shows the implementation of watchdog service:

![chlimage_1-31](assets/chlimage_1-31.png)

**1. Initialization** &ndash; At the time of initialization of the Cordova plugin, permissions are checked to see if you have system privileges and thus the Reboot permission. If these two criteria are met, a pending Intent for Reboot is created, otherwise a pending Intent to restart the application (based on its Launch Activity) is created.

**2. Keep Alive Timer** &ndash; A keep alive timer is used to trigger an event every 15 seconds. In that event, cancel the existing pending intent (to reboot or restart the app) and register a new pending intent for the same 60 seconds in the future (essentially postponing reboot).

>[!NOTE]
>
>In Android&trade;, the *AlarmManager* is used to register the *pendingIntents* that can execute even if the app has crashed and its alarm delivery is inexact from API 19 (Kitkat). Keep some spacing between the timer's interval and the *AlarmManager's* *pendingIntent's* alarm.

**3. Application Crash** &ndash; If there is a crash, the pendingIntent for Reboot registered with AlarmManager is no longer reset. Therefore, it runs a reboot or restart of the app (depending on permissions available at the time of initialization of the Cordova plugin).

## Bulk Provisioning of Android&trade; Player {#bulk-provision-android-player}

When rolling out the Android&trade; player in bulk, there is a need to provision the player to point to an AEM instance and configure other properties without manually entering those in the Admin UI. 

>[!NOTE]
>This feature is available from Android&trade; player 42.0.372.

Follow the steps below to allow bulk provisioning in the Android&trade; player:

1. Create a configuration JSON file with the name `player-config.default.json`. 
   See an [Example JSON Policy](#example-json) and a table that describes the use of the various [Policy Attributes](#policy-attributes).

1. Use an MDM or ADB or Android&trade; Studio file explorer to drop this policy JSON file to the *sdcard* folder on the Android&trade; device. 

1. When the file is deployed, use the MDM to install the player application.

1. When the player application launches, this configuration file is read and points to the applicable AEM server where it is registered and then controlled.

   >[!NOTE]
   >This file is *read only* the first time that the application is launched and cannot be used for subsequent configurations. If the player is launched before the configuration file was dropped, simply uninstall and reinstall the application on the device.

### Policy Attributes {#policy-attributes}

The following table summarizes the policy attributes with an example policy JSON for reference:

| **Policy Name** |**Purpose** |
|---|---|
| *server* |The URL to the Adobe Experience Manager server. |
| *resolution* |The resolution of the device. |
| *rebootSchedule* |The schedule to reboot applies to all platforms. |
| *enableAdminUI* |Enable the Admin UI to configure the device on site. Set to *false* once it is fully configured and in production. |
| *enableOSD* |Enable the channel switcher UI for users to switch channels on device. Consider setting to *false* once it is fully configured and in production. |
| *enableActivityUI* |Enable if you want to show the progress of activities such as download and sync. Enable for troubleshooting and disable once it is fully configured and in production. |
| *enableNativeVideo* |Enable if you want to use native hardware acceleration for video playback (Android&trade; only). |

### Example JSON Policy {#example-json}

```java
{
  "server": "https://author-screensdemo.adobecqms.net",
"device": "",
"user": "",
"password": "",
"resolution": "auto",
"rebootSchedule": "at 4:00 am",
"maxNumberOfLogFilesToKeep": 10,
"logLevel": 3,
"enableAdminUI": true,
"enableOSD": true,
"enableActivityUI": false,
"enableNativeVideo": false,
"enableAutoScreenshot": false,
"cloudMode": false,
"cloudUrl": "https://screens.adobeioruntime.net",
"cloudToken": "",
"enableDeveloperMode": true
}
```

>[!NOTE]
>All Android&trade; devices have an `*sdcard*` folder whether an actual `*sdcard*` is inserted or not. This file when deployed would be at the same level as the Downloads folder. Some MDMs, such as Samsung Knox, may see this *sdcard* folder location as *Internal storage*.

## Bulk Provisioning of Android&trade; Player using Enterprise Mobility Management {#bulk-provisioning}

When deploying the Android&trade; player in bulk, it becomes tedious to manually register every player with AEM. It is highly recommended to use an EMM (Enterprise Mobility Management) solution such as [`VMWare Airwatch`](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), MobileIron, or Samsung Knox to remotely provision and manage your deployment. AEM Screens Android&trade; player supports the industry standard EMM AppConfig to allow for remote provisioning. 

## Naming Android&trade; Player {#name-android}

You can assign a user-friendly device name to your Android&trade; player, thus sending the assigned device name to AEM (Adobe Experience Manager). This capability not only lets you name your Android&trade; player but also allows to you to easily assign appropriate content.

>[!NOTE]
>You can choose the Player name only before registration. After the Player is registered, the Player name cannot be changed anymore.

Follow the steps below to configure the name in Android&trade; player:

1. Navigate to **settings** > **About device** 
1. Edit and set your device name to name your Android&trade; player

### Implementing Bulk Provisioning of Android&trade; Player using Enterprise Mobility Management {#implementation}

Follow the steps below to allow bulk provisioning in Android&trade; Player:

1. Ensure your Android&trade; device supports Google Play services.
1. Enroll your Android&trade; player devices with your favorite EMM solution that supports AppConfig. 
1. Log in to your EMM console and pull the AEM Screens Player application from Google Play.
1. Click managed configuration or related option.
1. You should now see a list of player options that can be configured, such as server and bulk registration code.
1. Configure these parameters, save, and deploy the policy to the devices.

   >[!NOTE]
   >The devices should receive the application along with the configuration and point to the correct AEM server with the selected configuration. If you chose to configure the bulk registration code and kept it the same as configured in AEM, the player should be able to automatically register itself. If you configured a default display, it can also download and show some default content (which can later be changed as per your convenience).

Also, you should check with your EMM vendor on AppConfig support. Most popular ones such as [`VMWare Airwatch`](https://docs.samsungknox.com/admin/uem/vm-configure-appconfig.htm), [`Mobile Iron`](https://docs.samsungknox.com/admin/uem/mobileiron2-configure-appconfig.htm), [`SOTI`](https://docs.samsungknox.com/admin/uem/soti-configure-appconfig.htm), [`BlackBerry&reg; UEM`](https://docs.samsungknox.com/admin/uem/bb-configure-appconfig.htm), [`IBM&reg; Maas360`](https://docs.samsungknox.com/admin/uem/ibm-configure-appconfig.htm), and [`Samsung Knox`](https://docs.samsungknox.com/admin/uem/km-configure-appconfig.htm) among others support this industry standard.

### Using the Screens Remote Control {#using-remote-control}

AEM Screens provides Remote Control functionality. Learn more about this feature here: [Screens Remote Control](implementing-remote-control.md)
