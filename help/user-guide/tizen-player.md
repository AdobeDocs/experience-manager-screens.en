---
title: Tizen player
description: Learn about the installation and working of the Tizen player.
feature: Administering Screens, Players
role: Admin
level: Intermediate
exl-id: 45147959-b0ca-4d87-b89d-293e4b9af171
---
# Implementing Tizen player {#tizen-player}

## Installing Tizen player {#installing-tizen-player}

Follow the steps below to implement the Tizen player for AEM Screens:

1. Navigate to the [AEM Screens Player Downloads](https://download.macromedia.com/screens/) page so you can download the Tizen player.

1. Install the Tizen player *(.zip)* file from your local machine.

## Setting up the http Server {#setting-local-server}

>[!NOTE]
> Extract the zip file and make the Tizen player available through a `http server`. (The `http server` is not required to be Local or Apache server).

Follow the steps below:

1. Copy the two extracted files such as `AEMScreensPlayer.wgt` and `sssp_config.xml` to the root directory of your local Apache Web server.

   >[!NOTE]
   >The `AEMScreensPlayer.wgt`is the actual Tizen player application and `sssp_config.xml` contains information about this map that helps you to install it on Tizen device.

1. Get the IP or URL of your local HTTP server (and the path to the folder containing the extracted files in step 2 if extracted to a subfolder and not a root folder).

1. The Tizen player downloads the installer from the local server.

### Naming Tizen player {#name-tizen}

You can assign a user-friendly device name to your Tizen player, thus sending the assigned device name to Adobe Experience Manager (AEM). This capability not only lets you name your Tizen player but also lets you easily assign appropriate content.

>[!NOTE]
>You can choose the Player name only before registration. After the Player is registered, the Player name cannot be changed anymore.

Follow the steps below to configure the name in the Tizen player:

1. Click the menu button on your remote.
1. Navigate to **Network** > **Device Name** so you can assign a name to the player.

### Configuring Updates on the Samsung Device {#config-updates}

Follow the steps below on the Samsung device so you can complete the installation of the AEM Screens Player on the device:

1. Navigate to your Samsung device and turn in on.
1. Click the **MENU** button from the device's remote and scroll down to **System** from the left navigation bar.
1. Scroll down and click the **Play by way of** option and change it to the **URL Launcher** option.
   ![image](/help/user-guide/assets/tizen/rms-2.png)
1. When the URL Launcher is set, press the **Home** button from your remote.
1. Navigate to the **URL Launcher Settings** and enter the IP address of your localhost server and click **Done**.

   >[!NOTE] 
   >The Tizen player should be able to connect to the HTTP server.

1. The AEM Screens Player automatically installs and launches on your Samsung device.

   >[!NOTE]
   >Both the Tizen device and the `http` server should be able to connect with each other, that is, the server should be reachable to the Tizen player.


## Exempting User Agents with the SameSite Cookie Issue {#exempting-user-agents}

>[!IMPORTANT]
>**This section applies to Adobe Experience Manager (AEM) 6.5.5 to AEM 6.5.7**
>
>There are some browser engines that are incompatible with the *`SameSite=None`* attribute used in the login token issued by AEM 6.5.5 to AEM 6.5.7. Usually, the issue can be resolved by upgrading the browser to the latest available version. Sometimes such upgrades may not be possible such as with smart displays, set-top boxes or other devices with embedded browsing engines.

Follow the steps below to exempt these incompatible clients when using *SameSite=None*:

1. Upgrade to Adobe Experience Manager (AEM) Service Pack 6.5.7.

1. After AEM restarts, go to `/system/console/configMgr` and search for **Adobe Granite Token Authentication Handler**. Set the value for the **SameSite** value to **None**.

1. You should see a new option *`User agents to be exempted from samesite attribute`*. Populate this option with a regex corresponding to the user agent that is(are) incompatible with the *SameSite=None* attribute.

   >[!NOTE]
   >
   >See [SameSite=None: Known Incompatible Clients](https://www.chromium.org/updates/same-site/incompatible-clients) for more details. For the Tizen player, use the regex: `(.*)Tizen(.*)`.

1. Register the Tizen player against your AEM 6.5.5 and above instance and it should register and show content normally.

## Remotely Provisioning the Tizen player {#remote-provisioning}

Remotely provisioning the Tizen player lets you deploy hundreds and thousands of Samsung Tizen displays without much effort. It avoids the manual effort to configure each player with the server URL and bulk registration code, or other parameters. And, if there is AEM Screens as a Cloud Service, to configure the cloud mode and cloud token.

This feature lets you remotely configure Tizen player and also update those configurations centrally, if necessary. All you require is the `HTTP` server used to host the Tizen application `(wgt and xml file)` and a text editor to save the `config.json` with the appropriate parameters. 

Make sure you have configured the URL Launcher address on the Tizen device. Click the Home button > URL Launcher settings.
On the `HTTP` server that hosts the Tizen application, place the file `config.json` at the same location as the `wgt` file. The file name must be `config.json`.
The Tizen player installs and at launch (and every reboot), checks and applies the settings in the `config.json` file.

### Example JSON Policy {#example-json}

```java
{
  "server":  "http://your-aem-instance.com:4502",
  "registrationKey": "AdobeRocks!!",
  "enableAdminUI": true,
  "enableOSD": true,
  "enableActivityUI": true
}
```

### Policy Attributes and Purpose {#policy-attributes}

The following table summarizes the policies with their functions.

>[!NOTE]
>The player's Admin UI policy configurations are strictly enforced and are not manually overridden. To allow manual player configuration for a particular policy, do not specify the policy in the policy configuration.
>For example, if you want to allow manual configuration for reboot schedule, do not specify the key `rebootSchedule` in the policy configuration. Policy Configurations are read every time the player reloads.

| **Policy Name** |**Purpose** |
|---|---|
| server |The URL to the Adobe Experience Manager (AEM) server. |
| registrationKey |Used for bulk registration of devices using pre-shared key. |
| resolution |The resolution of the device. |
| rebootSchedule |The schedule to reboot the player.|
| enableAdminUI |Enable the Admin UI to configure the device on site. Set to false once it is fully configured and in production. |
| enableOSD |Enable the channel switcher UI for users to switch channels on the device. Consider setting to false, once it is fully configured and in production. |
| enableActivityUI |Enable so you can show the progress of activities such as download and sync. Enable for troubleshooting and disable once it is fully configured and in production. |
| cloudMode |Set to true if you want the Tizen player to connect to Screens as a Cloud Service. Set to false to connect to AMS or on-prem AEM. |
| cloudToken |Registration token to register against Screens as a Cloud Service. |


## Enrolling the Tizen Device to Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Follow the steps below to enroll the Tizen device to Samsung Remote Management Service (RMS) and remotely configure the URL Launcher:

>[!NOTE]
>Verify the network settings and the monitor. 

1. Navigate to **Menu** -> **Network** -> **Server Network Settings** and press **Enter**.

1. Navigate to the Server address and type in the MagicInfo URL access and press **Done**.

1. Setup TLS, if necessary. Navigate to the port and click the port number from the server and click **Save**.

1. Navigate to the **Device** tab and check for the device that you configured. When a device its found, click the check box, then click **Approve**.

   >![image](/help/user-guide/assets/tizen/rms-3.png)

1. Fill the required information and click a device group. Click **OK**.

   >![image](/help/user-guide/assets/tizen/rms-7.png)

1. When the Device is approved, it appears on the Device List. Click *Information* on your device box as shown in the following.

   >![image](/help/user-guide/assets/tizen/rms-6.png)

1. The device information dialog box displays. Click the **Device Info** tab and click **Edit**.  

    >![image](/help/user-guide/assets/tizen/rms-5.png)

1. Edit the device options and click the **Setup** tab. Navigate to **URL Launcher** section and enter URL hosting the wgt and `SSSP config file` so you can install an `SSSP` application, as shown in the figure below.

   ![image](/help/user-guide/assets/tizen/rms-9.png)

1. Click **Save**.

### Using the Screens Remote Control {#using-remote-control}

AEM Screens provides Remote Control functionality. Learn more about this feature here: [Screens Remote Control](implementing-remote-control.md)
