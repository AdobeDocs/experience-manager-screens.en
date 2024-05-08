---
title: Using Chrome Player as an Extension
description: Learn about installing the Chrome player as a browser extension for AEM Screens.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 53d5bd81-0853-47b0-9798-01d8fd5612e6
---
# Using Chrome player as an Extension {#using-chrome-player}

ChromeOS player can be installed as a Chrome browser plugin in developer mode without requiring an actual Chrome player device. 

 >[!CAUTION]
 >
 > Using the Chrome player as an extension for troubleshooting is recommended for quick demos, debugging and also to troubleshoot customer issues. Do not use this mechanism for production deployments that would require kiosk mode and central management.

Follow this page for information about installing the Chrome player as a browser extension.

1. Click [here](https://download.macromedia.com/screens/) to download the latest Chrome player.

1. Unzip and save it on disk.

1. Open Chrome browser and click the 3-dots menu and click **More Tools** from **Extensions** in the top-right corner or directly navigate to `chrome://extensions`.

1. Switch on the **Developer** mode from the top-right corner.

1. Click **Load Unpacked** from the top-left corner and load the unzipped Chrome player.

1. Check AEM Screens Chrome player plugin if it is available in the list of extensions.

1. Open a new tab and click the Apps icon from the top-left corner, or directly navigate to `chrome://apps`.

1. Click **AEM Screens Plugin** so you can launch the Chrome player.

   >[!NOTE]
   >
   > By default, the player is launched in full screen mode. Press **Esc** to exit full screen mode.


## Advanced Debugging Tips {#advanced-debugging-tips}

1. When the player has downloaded content locally, you can browse locally downloaded content by going to `http://localhost:24502`.

   >[!NOTE]
   >
   > If the above mentioned URL does not work, it means that either the player is not assigned a display, or the content has not successfully downloaded. Check the network tab for the player config JSON to see if the player obtains the correct details and for any network issues in download.

1. Right-click and inspect three layers of the Chrome player.
   **Debug content**: Right-click and inspect on the content to debug the running content (There should be a single item called "Inspect" in the context menu)

   **Debug firmware**: Bring up the admin UI and then right-click and inspect to debug the firmware(player) code. (There should be an option to inspect and inspect the background page and to simulate a browser restart.)

   **Debug background page**: Bring up the admin UI and then right-click and inspect the background page (for background services such as http server).

## Upgrading the Player Extension {#upgrading-player}

Follow the steps below to upgrade the player extension if a new version of the player is released. You can also follow the instructions below to test upgrade scenarios:

1. Close any running chrome and player instances
1. Rename the old folder with player files
1. Extract the new zip in the same location as the old folder
1. Launch Chrome and navigate to `chrome://extensions`
1. Check the player icon and click the refresh or reload button
