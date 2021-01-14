---
title: Tizen Player
description: This page describes the installation and working of Tizen Player.
---

# Implementing Tizen Player {#tizen-player}

## Installing Tizen Player {#installing-tizen-player}

Follow the steps below to implement Tizen Player for AEM Screens:

1. Navigate to the [AEM 6.5 Player Downloads](https://download.macromedia.com/screens/) page to download the Tizen Player.

1. Install the Tizen player *(.zip)* file from local machine.

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
   ![image](/help/user-guide/assets/tizen/url-launcher.png)

1. Press the **Home** button from your remote.

1. Enter the IP address of your localhost server.

1. Select **Remote** from the **Developer Mode**.

1. Click the **Home** button from the device's remote and select **URL Launcher**.

1. The AEM Screens Player should now automatically install and launch on your Samsung device.

## Bulk Provisioning of Tizen Player {bulk-provisioning-tizen-player}

>[!NOTE]
>It can be a tedious effort to manually enter your AEM server's address in the admin UI of each and every device for a large number of devices. It is recommended to use Samsung Remote Management (RMS) solution for deploying and managing the solution. Refer to [Enrolling the Tizen Device to Samsung Remote Management Service (RMS)](#enroll-tizen-device-rm) for more details.

Follow the steps below steps to bulk provision the application to point to your AEM author instance when it launches:

1. Download and install the [Tizen Studio]( https://developer.tizen.org/development/tizen-studio/download).
1. Open the `wgt` file using Tizen studio.
1. Open the file `firmware-platform.js` and search for `DEFAULT_PREFERENCES` and change the server URL to the AEM author URL and save.
1. Build the new `wgt` file.

   >[!NOTE]
   >You may need to create or setup a signing certificate.

1. Deploy this new `wgt` file RMS and when the player launches it should automatically point to your server so you do not need to manually enter it for every device.

### Enrolling the Tizen Device to Samsung Remote Management Service(RMS) {enroll-tizen-device-rms}

Follow the steps below to enroll the Tizen Device to Samsung Remote Management Service (RMS) and remotely configuring URL Launcher:

>[!NOTE]
>Verify the network settings and the monitor.

1. Press Menu on your remote and go System and then press enter on Play Via. 

   >[!NOTE]
   >Verify the screen is setup to Play Via URL Launcher
1. Navigate to **Menu** -> **Network** -> **Server Network Settings** and press **Enter**.

1. Navigate to Server Address and type in the MagicInfo URL access and press Done.

1. Navigate to the Device Tab once logged in to MIS
1. Look for the device you just configured by looking at the IP address and/or its Mac Address. 
1. Once a device its found, click on the check box and select Approve
1. Please verify that the screen is setup to Play Via URL Launcher
1. Press Menu on your remote and go System and then press enter on Play Via
1. Navigate to Menu -> Network -> Server Network Settings and press Enter
1. Go to Server Address and type in the MagicInfo URL access and press Done
1. Setup TLS to Use or Don’t Use depending the case
1. Go to port and select the port number from the server.
1. Hit Save once the options are ready.



