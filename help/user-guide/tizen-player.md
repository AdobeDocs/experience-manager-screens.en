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

1. The Tizen player will download the installer from the local server.

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
>There are some browser engines that are incompatible with the *SameSite=None* attribute used in the login token issued by AEM 6.5 to AEM 6.7. In most cases the issue can be resolved by upgrading the browser to the latest available version. In some cases such upgrades may not be possible such as with smart displays, set top boxes or other devices with embedded browsing engines. 

Follow the steps below to exempt these incompatible clients when using *SameSite=None*:

1. Upgrade to Adobe Experience Manager (AEM) Service Pack 6.5.7.

1. After AEM restarts go to `/system/console/configMgr` and search for **Adobe Granite Token Authentication Handler**. Set the value for the **SameSite** value to **None**.

1. You should see a new option *User agents to be exempted from samesite attribute*. Populate this with a regex corresponding to the user agent(s) that is(are) incompatible with the *SameSite=None* attribute.
   >[!NOTE]
   >See [SameSite=None: Known Incompatible Clients](https://www.chromium.org/updates/same-site/incompatible-clients) for more details. For the Tizen player use the regex: `(.*)Tizen(.*)`.

1. Register the Tizen player against your AEM 6.5.5 and above instance and it should register and show content normally.

## Bulk Provisioning of Tizen Player {#bulk-provisioning-tizen-player}

>[!NOTE]
>It can be a tedious effort to manually enter your AEM server's address in the admin UI of each and every device for a large number of devices. It is recommended to use Samsung Remote Management (RMS) solution for deploying and managing larger solutions. Refer to [Enrolling the Tizen Device to Samsung Remote Management Service (RMS)](#enroll-tizen-device-rm) for more details.

Follow the steps below steps to bulk provision the application to point to your AEM author instance when it launches:

1. Download and install the [Tizen Studio](https://developer.tizen.org/development/tizen-studio/download).
1. Open the `wgt` file using Tizen studio.
1. Open the file `firmware-platform.js` and search for `DEFAULT_PREFERENCES` and change the server URL to the AEM author URL and save.
1. Build the new `wgt` file.

   >[!NOTE]
   >You may need to create or setup a signing certificate.

1. Deploy this new `wgt` file using RMS or URL Launcher and when the player launches it should automatically point to your server so you do not need to manually enter it for every device.

### Enrolling the Tizen Device to Samsung Remote Management Service (RMS) {#enroll-tizen-device-rms}

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
