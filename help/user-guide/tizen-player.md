---
title: Tizen Player
description: This page describes the installation and working of Tizen Player.
---

# Implementing Tizen Player {#tizen-player}

## Installing Tizen Player {#installing-tizen-player}

Follow the steps below to implement Tizen Player for AEM Screens:

1. Navigate to the [**AEM 6.5 Player Downloads**](https://download.macromedia.com/screens/) page to download the Tizen Player.

1. Install the Tizen player (.zip) file from local machine.

1. Get IP address of your local machine. 

    >[!NOTE]
    >In the Terminal of your machine type the following commands for:
    >**Mac** use command `ifconfig`
    >**Windows**, use command `ipconfig`

1. From the Terminal, navigate to the same directory of the unzipped installer folder and verify if the localhost is working.

   >[!NOTE]
   >For **Mac**, type `http://localhost` and verify if the `http` server is running.

1. The Tizen player will download the installer from the local server.

1. Copy the two extracted files `AEMScreensPlayer.wgt` and `sssp_config.xml` to `/Library/WebServer/Documents`.

### Configuration Updates on the SamSung Device {#config-updates}

Follow the steps below on the Samsung device to complete the installation of the AEM Screens player on the device:

1. Click on the **Home** button from the Samsung Remote.
1. Select **URL Launcher** from the **Settings**.
1. Select **Remote** from the Developer Mode.
1. Install Web App and enter your machine's IP address.
   The AEM Screens Player should automatically install on Samsung device.


