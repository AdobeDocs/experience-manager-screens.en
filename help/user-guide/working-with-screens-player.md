---
title: Working with AEM Screens Player
description: Learn about working with the AEM Screens Player, the Admin UI, and the Channel Switcher.
contentOwner: jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 4faac090-ad8a-4d7e-a502-6fb63f6b2761
---
# Working with AEM Screens Player

You can manage the channel content and other settings on the AEM Screens Player.

>[!NOTE]
>
>Press ***Ctrl+Cmd+F*** so you can exit fullscreen mode for OS X AEM Screens Player.

After you assign a channel to a display, the AEM Screens Player displays the content. You can either configure settings for your player using the preferences for admin UI (from the dashboard) or from the player itself.

## Using the Device Dashboard {#using-the-device-dashboard}

You can configure preferences for your device from the Device Dashboard, accessible by way of your AEM authoring instance.

1. Navigate to the device dashboard from your project, for example, ***Test Project*** > ***Devices***.

   Click **Devices** and **Device Manager** from the action bar.

   ![chlimage_1-66](assets/chlimage_1-66.png)

1. Click the device so you can open the device dashboard.

   ![chlimage_1-67](assets/chlimage_1-67.png)

1. Check the **PREFERENCES** panel. You can enable/disable the **Admin UI** and **Channel Switcher** for your player from these two options.

   ![chlimage_1-68](assets/chlimage_1-68.png)

### The Admin UI {#the-admin-ui}

Enabling the **Admin UI** from the preferences panel allows the user to open the admin settings from the Screens Player. Also, if you disable this option from the device dashboard, the user cannot open the admin UI from the player.

To view the admin UI from the Screens player, long press the top-left corner to open the Admin menu, on your touch-enabled AEM Screens Player, or by using a mouse. Information is displayed after registration is complete and the channels are loaded.

>[!NOTE]
>
>Also, you can view the AEM Screens Player app uptime to check app health status.

![chlimage_1-3](assets/chlimage_1-3.gif)

#### Accessing the Configuration Menu Options {#configuration-options}

You can update your configurations if you click the **Configuration** option from the side menu, as shown in the figure below:

![screen_shot_2018-10-15at101257am](assets/screen_shot_2018-10-15at101257am.png)

The Configuration menu lets you modify the following settings:

* Reset **Firmware**, **Preferences**, or **To Factory** from this dialog box.

* Specify the number of maximum log files that you want to keep for an AEM Screens Player in **Max No. of log files to keep**.

* Enable or disable **Admin Menu**, **Channel Switcher**, and **Activity UI** for the Screens player.

   If the **Activity UI** is enabled from the **Configuration** menu, the AEM Screens Player displays the *player activity notifications* in the top right-hand corner of the player, as shown in the figure below.

   ![image](/help/user-guide/assets/activity_ui.png)

>[!NOTE]
>
>The **Update Firmware** option only works on the Cordova, such as Android&trade; players.

>[!NOTE]
>
>It is recommended that the **Admin UI** be disabled in Production Deployments.

#### Accessing the Content Cache Menu Options {#content-cache-options}

You can clear cache for channels and applications from the Admin UI in AEM Screens Player.

Click the **Content Cache** from the side rail so you can update the cache.

![screen_shot_2018-10-15at105717am](assets/screen_shot_2018-10-15at105717am.png)

### The Channel Switcher {#the-channel-switcher}

Enabling the **Channel Switcher** from the preferences panel allows the user to open the channel selection/settings from the Screens Player.

Also, if you disable this option from the device dashboard, the user cannot control channel preferences from the Screens Player.

You can switch and control settings for your channel from your Screens Player.

To view the channel switcher from the player, long press the lower left corner to open the channel switcher that allows switching channels and other features.

![chlimage_1-69](assets/chlimage_1-69.png)

>[!NOTE]
>
>You can also enable or disable the admin menu and the channel switcher for the player from the Screens player.
>
>(See *Change Preferences from Screens Player* as mentioned in the section below).

### Managing Preferences from the AEM Screens Player

You can also change the settings for admin UI and channel switcher from the player itself.

To change preferences from your Player:

1. Long-press on the top-left corner on the idle channel to open the admin panel.
1. Navigate to **Configuration** from the left action menu.
1. Enable/disable configuration for **Admin UI** or **Channel Switcher**.

![screen_shot_2018-10-15at101257am-1](assets/screen_shot_2018-10-15at101257am-1.png)

## Troubleshooting AEM Screens Player

You can troubleshoot various issues associated with the AEM Screens Player (hardware and software):

| **Issues** |**Recommendations** |
|---|---|
| Player storage is full |Eliminate unnecessary files |
| Player lost network |Use Cat-5/Cat-6 cable. For wifi, reduce the distance from the router to the player device |
| AEM Screens Player crashed |It is recommended to have a watchdog app that makes sure the AEM Screens Player always runs |
| AEM Screens Player lost settings |Check connection to AEM server |
| AEM Screens Player does not auto-start after Player restart/reboot |Check OS start folder or initialization procedure |
| AEM Screens Player shows wrong/old content |Check network connection |

### Updates for AEM Screens Player

There are two types of updates for the AEM Screens Player:

| **Method** |**Details** |**by way of Remote** |**Automated** |**0 Downtime** |
|---|---|---|---|---|
| Firmware Update |Applied on existing installed Players by way of remote command. After the update, the Player auto-reloads with the existing content. |Yes |Custom |Almost - 1-3 seconds |
| Player Shell Updates |This is a new executable to be deployed on the Player. This requires to remote copy new binary on the player and stop the currently running and start the new version. This might require downloading the pre-load of the packages again. |Yes (by way of remote shell) |Custom |No |

## Hardware Selection Guidelines for Player Device {#hardware-selection-guidelines-for-player-device}

The following section provides the hardware selection guidelines for a Screens Project:

* Always source ***Commercial*** or ***Industrial*** Grade components for both PC player and Display Panel or Projector.

* Always engage with vendors who serve the digital signage market.
* Always consider environmental factors such as ambient temperature and relative humidity.
* Always review power requirements and power conditioning.
* Carefully review performance needs and I/O ports required for application.

The following table summarizes the hardware configurations with typical use cases for an AEM Screens project:

<table>
 <tbody>
  <tr>
   <td>Player Configuration</td>
   <td>Processor</td>
   <td>Memory</td>
   <td>Storage SSD</td>
   <td>GPU</td>
   <td>Display</td>
   <td>I/O</td>
   <td>Typical Use Cases</td>
  </tr>
  <tr>
   <td>Basic</td>
   <td>Dual Core, i3, or entry-level quad core Intel&reg; Atom Processor</td>
   <td><p>4 GB of memory</p> <p>2 MB of cache</p> </td>
   <td><p>*ChromeOS 32 GB</p> <p>*Windows 128 GB</p> </td>
   <td>OnBoard</td>
   <td>1920 x 1080</td>
   <td>DVI<br /> Ethernet / Wireless<br /> 2xUSB</td>
   <td>
    <ul>
     <li>Standard Full Screen Looping<br /> </li>
     <li>Day Parting</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Standard</td>
   <td>Quad Core, Intel&reg; Core&trade; i5 processor</td>
   <td><p>8 GB of memory</p> <p>4 MB of cache</p> </td>
   <td>128 GB</td>
   <td>OnBoard</td>
   <td>3840x2160 (<code>4K</code>)</td>
   <td>DVI, HDMI<br /> Ethernet / Wireless,<br /> 2xUSB</td>
   <td>
    <ul>
     <li>Single Source Dynamic Content</li>
     <li>Simple Interactive</li>
     <li>1-3 Zone layouts</li>
    </ul> </td>
  </tr>
  <tr>
   <td>Advanced</td>
   <td>Quad Core with hyperthreading, Intel&reg; Core&trade; i7 processor</td>
   <td><p>16 GB of memory</p> <p>8 MB of cache</p> </td>
   <td>256 GB</td>
   <td>Dedicated Graphics GPU</td>
   <td>3840x2160 (<code>4K</code>)</td>
   <td>DVI, HDMI<br /> Ethernet / Wireless,<br /> 4xUSB</td>
   <td>
    <ul>
     <li>4 or more Content Zones, Concurrent Video Playback</li>
     <li>Multi-Page Interactive</li>
     <li>Multi-Source Data Triggers</li>
    </ul> </td>
  </tr>
 </tbody>
</table>
