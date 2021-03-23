---
title: Using Chrome Player as an Extension
seo-title: Using Chrome Player as an Extension
description: Follow this page to learn about installing the chrome player as a browser extension.
seo-description: null
feature: Administering Screens
role: Administrator
level: Intermediate
---

# Using Chrome Player as an Extension {#using-chrome-player}

ChromeOS player can be installed as Chrome Browser plugin in developer mode without requiring actual chrome player device. 

 >[!CAUTION]
 >
 > Using the Chrome Player as an extension for troubleshooting is recommended for quick demos, debugging and also to troubleshoot customer issues. This mechanism should not be used for production deployments that would require kiosk mode and central management.

Follow this page to learn about installing the chrome player as a browser extension.

1. Click [here](https://download.macromedia.com/screens/) to download the latest Chrome Player.

1. Unzip and save it on disk.

1. Open Chrome browser and click the 3-dots menu and select **More Tools** from **Extensions** located at the top right corner or directly navigate to `chrome://extensions`.

1. Switch on the **Developer** mode from top right corner.

1. Click on **Load Unpacked** from top left corner and load unzipped Chrome Player.

1. Check AEM Screens Chrome Player plugin if is available in the list of extensions.

1. Open a new tab and click the Apps icon from the top left corner, or directly navigate to `chrome://apps`.

1. Click on **AEM Screens Plugin** to launch Chrome Player. 
   >[!NOTE]
   >
   > By default, the player is launched in full screen mode. Press **esc** to exit full screen mode.


## Advanced Debugging Tips {#advanced-debugging-tips}

1. Once the player has downloaded content locally, you can browse locally downloaded content by going to `http://localhost:24502`.

   >[!NOTE]
   >
   > If the above mentioned URL does not work it means either the player is not assigned a display or the content has not successfully downloaded. Check the network tab for the player config JSON to see if the correct details are obtained by the player and for any network issues in download.

1. You can right click and inspect three layers of the chrome player
   **Debug content**: Right click and inspect on the content to debug the running content (There should be a single item called "Inspect" in the context menu)

   **Debug firmware**: Bring up the admin UI and then right click and inspect to debug the firmware (player) code (There should be an option to inspect and inspect background page and to simulate browser restart)

   **Debug background page**: Bring up the admin UI and then right click and inspect background page (for background services such as http server)

## Upgrading the Player Extension {#upgrading-player}

Follow the steps below to upgrade the player extension if a new version of the player is released. You can also follow the instructions below to test upgrade scenarios:

1. Close any running chrome and player instances
1. Rename the old folder with player files
1. Extract the new zip in the same location as the old folder
1. Launch Chrome and navigate to `chrome://extensions`
1. Check the player icon and click refresh or reload button