---
title: Tizen Player
description: This page describes the installation and working of Tizen Player.
feature: Administering Screens, Players
role: Administrator
level: Intermediate
exl-id: 45147959-b0ca-4d87-b89d-293e4b9af171
---
# Implementing Tizen Player {#tizen-player}

## Installing Tizen Player {#installing-tizen-player}

Follow the steps below to implement Tizen Player for AEM Screens:

1. Navigate to the [AEM Screens Player Downloads](https://download.macromedia.com/screens/) page to download the Tizen Player.

1. Install the Tizen player *(.zip)* file from local machine.

## Setting up the Local Server and Extracting Zip Files {#setting-local-server}

>[!NOTE]
> Extract the zip file and make the Tizen player available through a `http server`. (The `http server` is not required to be Local or Apache server).

Follow the steps below:

1. Copy the two extracted files such as `AEMScreensPlayer.wgt` and `sssp_config.xml` to the root directory of your local Apache Web server.

   >[!NOTE]
   >The `AEMScreensPlayer.wgt`is the actual Tizen player application and `sssp_config.xml` contains information about this map that helps you to install it on Tizen device.

1. Get the IP or URL of your local HTTP server (and path to the folder containing the extracted files in step 2 if extracted to a sub folder and not root folder)

1. The Tizen player downloads the installer from the local server.

### Naming Tizen Player {#name-tizen}

You can assign a user-friendly device name to your Tizen player, thereby sending the assigned device name to Adobe Experience Manager (AEM). This capability not only allows you to name your Tizen player but also allows to you to easily assign appropriate content.

Follow the steps below to configure the name in Tizen player:

1. Click the menu button on your remote.
1. Navigate to **network** --> **Device Name** to assign a name to the player.

### Configuring Updates on the Samsung Device {#config-updates}

Follow the steps below on the Samsung device to complete the installation of the AEM Screens player on the device:

1. Navigate to your Samsung device and turn in on.

1. Click the **MENU** button from the device's remote and scroll down to **System** from the left navigation bar.

1. Scroll down and select the **Play via** option and change it to **URL Launcher** option.
   ![image](/help/user-guide/assets/tizen/rms-2.png)

1. Once the URL Launcher is set, press the **Home** button from your remote.

1. Navigate to the **URL Launcher Settings** and enter the IP address of your localhost server and click **Done**.
   >[!NOTE] 
   >The Tizen player should be able to connect to the http server.

1. The AEM Screens Player should now automatically install and launch on your Samsung device.

   >[!NOTE]
   >Both the Tizen device and the `http` server should be able to connect with each other, that is, the server should be reachable to the Tizen player.


## Exempting User Agents with the SameSite Cookie Issue {#exempting-user-agents}

>[!IMPORTANT]
>**This section applies to Adobe Experience Manager (AEM) 6.5.5 to AEM 6.5.7**
>There are some browser engines that are incompatible with the *SameSite=None* attribute used in the login token issued by AEM 6.5 to AEM 6.7. Usually, the issue can be resolved by upgrading the browser to the latest available version. In some cases such upgrades may not be possible such as with smart displays, set top boxes or other devices with embedded browsing engines. 

Follow the steps below to exempt these incompatible clients when using *SameSite=None*:

1. Upgrade to Adobe Experience Manager (AEM) Service Pack 6.5.7.

1. After AEM restarts go to `/system/console/configMgr` and search for **Adobe Granite Token Authentication Handler**. Set the value for the **SameSite** value to **None**.

1. You should see a new option *User agents to be exempted from samesite attribute*. Populate this with a regex corresponding to the user agent that is(are) incompatible with the *SameSite=None* attribute.
   >[!NOTE]
   >See [SameSite=None: Known Incompatible Clients](https://www.chromium.org/updates/same-site/incompatible-clients) for more details. For the Tizen player use the regex: `(.*)Tizen(.*)`.

1. Register the Tizen player against your AEM 6.5.5 and above instance and it should register and show content normally.

## Remotely Provisioning the Tizen Player {#remote-provisioning}

Remotely provisioning the Tizen Player allows you to deploy hundreds and thousands of Samsung Tizen displays without much effort. It avoids the tedious manual effort to configure each player with the server URL and bulk registration code, or other parameters and in the case of Screens as a Cloud Service to configure the cloud mode and cloud token.

This feature allows you to remotely configure Tizen player and also update those configurations centrally, if required. All you require is the `HTTP` server used to host the Tizen application `(wgt and xml file)` and a text editor to save the `config.json` with the appropriate parameters. 

Make sure you have configured the URL launcher address on the Tizen Device, that is, Home Button --> URL Launcher settings.
On the `HTTP` server that hosts the Tizen application, place the file `config.json` at the same location as the `wgt` file. The file name must be `config.json`.
The Tizen player will install and at launch (and every reboot) will check and apply the settings in the `config.json` file.

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
>Policy configurations are strictly enforced and are not manually overridden at the player's Admin UI. To allow manual player configuration for a particular policy, do not specify the policy in the policy configuration, for example, if you want to allow manual configuration for reboot schedule, do not specify the key `rebootSchedule` in the policy configuration. Policy Configurations are read every time the player reloads.

| **Policy Name** |**Purpose** |
|---|---|
| server |The URL to the Adobe Experience Manager (AEM) server. |
| registrationKey |Used for bulk registration of devices using pre-shared key. |
| resolution |The resolution of the device. |
| rebootSchedule |The schedule to reboot the player.|
| enableAdminUI |Enable the Admin UI to configure the device on site. Set to false once it is fully configured and in production. |
| enableOSD |Enable the channel switcher UI for users to switch channels on device. Consider setting to false, once it is fully configured and in production. |
| enableActivityUI |Enable to show progress of activities such as download and sync. Enable for troubleshooting and disable once it is fully configured and in production. |
| cloudMode |Set to true if you want the Tizen player to connect to Screens as a Cloud Service. Set to false in order to connect to AMS or on-Prem AEM. |
| cloudToken |Registration token to register against Screens as a Cloud Service. |


## Enrolling the Tizen Device to Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

Follow the steps below to enroll the Tizen device to Samsung Remote Management Service (RMS) and remotely configure the URL Launcher:

>[!NOTE]
>Verify the network settings and the monitor. 

1. Navigate to **Menu** -> **Network** -> **Server Network Settings** and press **Enter**.

1. Navigate to Server address and type in the MagicInfo URL access and press **Done**.

1. Setup TLS, if required. Navigate to the port and select the port number from the server and click on **Save**.

1. Navigate to the **Device** tab and check for the device you just configured. Once a device its found, click on the check box and select **Approve**.

   >![image](/help/user-guide/assets/tizen/rms-3.png)

1. Fill the required information and select a device group. Click on **OK** to complete the approval process.

   >![image](/help/user-guide/assets/tizen/rms-7.png)

1. Once Device is approved, it should appear on the Device List. Click on the *Information* button located on your device box, that is **i**, as shown in the figure below.

   >![image](/help/user-guide/assets/tizen/rms-6.png)

1. The device information dialog box displays. Select the **Device Info** tab and click on **Edit**.  

    >![image](/help/user-guide/assets/tizen/rms-5.png)

1. Edit the device options and select the **Setup** tab. Navigate to **URL Launcher** section and enter URL hosting the wgt and `SSSP config file` to install an `SSSP` application, as shown in the figure below.

   ![image](/help/user-guide/assets/tizen/rms-9.png)

1. Click on **Save** for the changes to appear on the display screen.
