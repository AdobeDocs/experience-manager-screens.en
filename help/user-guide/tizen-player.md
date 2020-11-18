---
title: Tizen Player
description: This page describes the installation and working of Tizen Player.
---

# Implementing Tizen Player {#tizen-player}

## Installing Tizen Player {#installing-tizen-player}

Follow the steps below to implement Tizen Player for AEM Screens:

1. Navigate to the [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/) page to download the Tizen Player.

1. Install the Tizen player (.zip) file from local machine.

## Setting up the Local Server and Extracting Zip Files {#setting-local-server}

Follow the steps below to setup the local server and copy the extracted files:

1. Get IP address of your local machine. 

    >[!NOTE]
    >You can get the IP address from the Terminal of your machine using the following commands:
    >* **Mac**: `ifconfig`
    >* **Windows**: `ipconfig`

1. From the Terminal, navigate to the same directory of the unzipped installer folder and verify if the localhost is working.

   >[!NOTE]
   >For **Mac**, type `http://localhost` and verify if the `http` server is running.

1. The Tizen player will download the installer from the local server.

1. Copy the two extracted files `AEMScreensPlayer.wgt` and `sssp_config.xml` to `/Library/WebServer/Documents`.

### Configuring Updates on the Samsung Device {#config-updates}

Follow the steps below on the Samsung device to complete the installation of the AEM Screens player on the device:

1. Go to your Samsung device and point to your localhost server.
1. Select **URL Launcher Settings** and enter the IP address of your localhost server.
1. Install Web App.
1. Select **Remote** from the **Developer Mode**.
1. The AEM Screens Player should now automatically start the installation on your Samsung device.


