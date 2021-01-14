---
title: Tizen Player
description: This page describes the installation and working of Tizen Player.
---

# Implementing Tizen Player {#tizen-player}

## Installing Tizen Player {#installing-tizen-player}

Follow the steps below to implement Tizen Player for AEM Screens:

1. Navigate to the [AEM 6.5 Player Downloads](https://download.macromedia.com/screens/) page to download the Tizen Player.

1. Install the Tizen player *(.zip)* file from local machine.

## Exempting User Agents with the Samesite Cookie Issue {#exempting-user-agents}

>[!IMPORTANT]
>**This section applies to AEM 6.5.5 to AEM 6.5.7**
>There are some browser engines that are incompatible with the *SameSite=None* attribute used used in the login token issued by AEM 6.5 to AEM 6.7. In most cases the issue can be resolved by upgrading the browser to the latest available version. In some cases such upgrades may not be possible such as with smart displays, set top boxes or other devices with embedded browsing engines. To exempt these incompatible clients when using SameSite=None, please use the following steps.

1. Download the patch *jar file* from  `https://artifactory.corp.adobe.com/artifactory/maven-aem-release-local/com/adobe/granite/crx-auth-token/2.6.10/`.

1. Navigate to `/system/console/bundles` in AEM and click the `install/update` button.

1. Install the `crx-auth-token` jar file. You may need to shutdown and restart AEM after installing this jar because it is related to authentication.

1. After AEM restarts go to `/system/console/configMgr` and search for **Adobe Granite Token Authentication Handler**. Set the value for the SameSite setting to None.

1. You should see a new option *User agents to be exempted from samesite attribute*. Populate this with a regex corresponding to the user agent(s) that is(are) incompatible with the *SameSite=None* attribute.
   >[!NOTE]
   >See [SameSite=None: Known Incompatible Clients](https://www.chromium.org/updates/same-site/incompatible-clients) for more details.

1. For the Tizen player use the regex: `(.*)Tizen (4|5)(.*)` Register the Tizen player against your AEM 6.5.5 and above instance and it should register and show content normally.


## Setting up the Local Server and Extracting Zip Files {#setting-local-server}

Follow the steps below to setup the local server and copy the extracted files:

1. Get IP address of your local machine. 
   >[!NOTE]
   >Please review the official documentation to learn how to enable the local server on your platform.

1. From the Terminal, navigate to the same directory of the unzipped installer folder and verify if the localhost is working.

1. The Tizen player will download the installer from the local server.

1. Copy the two extracted files such as `AEMScreensPlayer.wgt` and `sssp_config.xml` to the root directory of your local Apache Web server.

   >[!NOTE]
   >The `AEMScreensPlayer.wgt`is the actual Tizen player application and `sssp_config.xml` contains information about this map that helps you to install it on Tizen device.

### Configuring Updates on the Samsung Device {#config-updates}

Follow the steps below on the Samsung device to complete the installation of the AEM Screens player on the device:

1. Navigate to your Samsung device and turn in on.

1. Click the **MENU** button from the device's remote and scroll down to **System** from the left navigation bar.

1. Scroll down and select the **Play via URL Launcher** option.
   ![image](/help/user-guide/assets/tizen/rms-2.png)

1. Press the **Home** button from your remote.

1. Enter the IP address of your localhost server.

1. Select **Remote** from the **Developer Mode**.

1. Click the **Home** button from the device's remote and select **URL Launcher**.

1. The AEM Screens Player should now automatically install and launch on your Samsung device.

## Bulk Provisioning of Tizen Player {#bulk-provisioning-tizen-player}

>[!NOTE]
>It can be a tedious effort to manually enter your AEM server's address in the admin UI of each and every device for a large number of devices. It is recommended to use Samsung Remote Management (RMS) solution for deploying and managing the solution. Refer to [Enrolling the Tizen Device to Samsung Remote Management Service (RMS)](#enroll-tizen-device-rm) for more details.

Follow the steps below steps to bulk provision the application to point to your AEM author instance when it launches:

1. Download and install the [Tizen Studio](https://developer.tizen.org/development/tizen-studio/download).
1. Open the `wgt` file using Tizen studio.
1. Open the file `firmware-platform.js` and search for `DEFAULT_PREFERENCES` and change the server URL to the AEM author URL and save.
1. Build the new `wgt` file.

   >[!NOTE]
   >You may need to create or setup a signing certificate.

1. Deploy this new `wgt` file RMS and when the player launches it should automatically point to your server so you do not need to manually enter it for every device.

### Enrolling the Tizen Device to Samsung Remote Management Service(RMS) {#enroll-tizen-device-rms}

Follow the steps below to enroll the Tizen device to Samsung Remote Management Service (RMS) and remotely configure the URL Launcher:

>[!NOTE]
>Verify the network settings and the monitor. 

1. Navigate to **Menu** -> **Network** -> **Server Network Settings** and press **Enter**.
 
   >[!NOTE]
   >Verify the screen is setup to Play Via URL Launcher.
   >![image](/help/user-guide/assets/tizen/rms-2.png)

1. Navigate to Server Address and type in the MagicInfo URL access and press Done.

1. Setup TLS, if required. Navigate to the port and select the port number from the server. Click on **Save**.

1. Navigate to the Device tab and look for the device you just configured.

1. Once a device its found, click on the check box and select **Approve**.

1. Fill the required information and select a device group. Click on **Ok** to complete the approval process.

   >![image](/help/user-guide/assets/tizen/rms-7.png)

1. Once Device is approved, it should appear on the Device List. Click on the *Information* button located on your device box **i**.

   >![image](/help/user-guide/assets/tizen/rms-6.png)

1. The device information dialog box displays. Select the **Device Info** tab and click on **Edit**.  

1. Edit Device options and select the **Setup** tab. Navigate to **URL Launcher** section and enter URL hosting the wgt and `SSSP config file` to install an `SSSP` application, as shown in the figure below.

   ![image](/help/user-guide/assets/tizen/rms-9.png)

1. Click on **Save** for the changes to appear on the display screen.




