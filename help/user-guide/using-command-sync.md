---
title: Using Command Sync
seo-title: Using Command Sync
description: Follow this page to learn about how to use Command Sync.
seo-description: Follow this page to learn about how to use Command Sync.
---

# Command Sync {#command-sync}

The following page describes how to use Command Sync. Command Sync allows synchronized playback across different players. The players can play different content but each asset needs to have the same duration.

>[!IMPORTANT]
>
>This feature does not support Embedded Sequences, Dynamic Embedded Sequences, Application Channels, or Transitions.

## Overview {#overview}

Digital signage solutions need to support video walls and synchronized playback to support scenarios like New Year countdowns or large video sliced up to play across multiple screens and this is where Command Sync comes into play.

To use Command Sync, one player acts as a *master* and sends command and all the other players act as *clients* and play when they receive the command. 

The *master* sends a command to all registered clients when it is about to start playback of an item. The payload of this can be the index of the item to be played and/or the outer html of the element to be played.

## Implementing Command Sync {#using-command-sync}

The following section describes how you can use Command Sync in an AEM Screens project.

>[!NOTE]
>
>For synchronized playback, it is required that all the hardware devices have the same hardware specifications and preferably the same operating system. Synchronizing between different hardware and operating systems is not recommended.

### Setting up the Project {#setting-up}

Before you use Command Sync feature, make sure you have a project and a channel with content set up for your project.

1. The following example showcases a demo project named **CommandSyncDemo** and a sequence channel **ChannelLobby**.

   ![image1](assets/command-sync/command-sync1-1.png)

   >[!NOTE]
   >
   >To learn how to create a channel or add content to a channel, refer to [Creating and Managing Channels](/help/user-guide/managing-channels.md)

   The channel contains the following content, as shown in the figure below.

   ![image1](assets/command-sync/command-sync2-1.png)

1. Create a location **Lobby** and subesequently a display titled as **LobbyDisplay** in the **Locations** folder, as shown in the figure below.
   ![image1](assets/command-sync/command-sync3-1.png)

1. Assign the channel, **ChannelLobby** to your **LobbyDisplay**. You can now view the assigned channel to the display from the display dashboard.
    ![image1](assets/command-sync/command-sync4-1.png)

   >[!NOTE]
   >
   >To learn how to assign a channel to a display, refer to [Creating and Managing Displays](/help/user-guide/managing-displays.md).

1. Navigate to **Devices** folder and click **Device Manager** from the action bar to register the devices.

   ![image1](assets/command-sync5.png)

   >[!NOTE]
   >
   >To learn how to register a device, refer to [Device Registration](/help/user-guide/device-registration.md)

1. For demo purposes, this example showcases a chrome device and a windows player as two separate devices. Both the devices point to the same display.
   ![image1](assets/command-sync6.png)

### Updating Channel Settings

1. Navigate to **ChannelLobby** and click **Edit** from the action bar to update the channel settings.

1. Select the entire channel as shown in the figure below.
   ![image1](assets/command-sync/command-sync7-1.png)

1. Click the wrench icon to open the **Page** dialog box.
   ![image1](assets/command-sync/command-sync8-1.png)

1. Enter the *synced* keyword in the **Strategy** field.

   ![image1](assets/command-sync/command-sync9-1.png)


### Setting up a master {#setting-up-master}

1. Navigate to the display dashboard from **CommandSyncDemo** --> **Locations**  --> **Lobby** --> **LobbyDisplay** and click on **Dashboard** from the action bar.
You will see the two devices (chrome and windows player) in **DEVICES** panel, as shown in the figure below.
      ![image1](assets/command-sync/command-sync10-1.png)

1. From the **DEVICES** panel,select the device you want to set as master. The following example demonstrates setting up the Chrome device as the master. Click on **Set as master device**.

    ![image1](assets/command-sync/command-sync11-1.png)

1. Enter the IP address in **Set as master device** and click on **Save**. 

   ![image1](assets/command-sync/command-sync12-1.png)

>[!NOTE]
>
>You can set up multiple devices as master.

### Syncing up with Master {#sync-up-master}

1. Once you have set the Chrome device as master, you can sync the other device (in this case, the windows player) to sync with the master.
Select the other device (in this case, windows player) from the **DEVICES** panel and click on **Sync to master device**, as shown in the figure below.

   ![image1](assets/command-sync/command-sync13-1.png)

1. Select the device from the list and click **Save**.

   >[NOTE:]
   > The **Sync to master device** dialog will show the list of master devices. You can select the desired one of your preference.

1. Once the device (Windows player) is synced to the master (Chrome player), you will see the device synced in the **DEVICES** panel.

   ![image1](assets/command-sync/command-sync14-1.png)

### De-Syncing with the Master {#desync-up-master}

Once you have synced a device or devices to a master, you can de-sync the assignment from that device. 

>[!NOTE]
>
>If you de-sync a master device, it will also unlink all client devices associated with that master device.

In order to remove the syncing from the master device, follow the steps below:

1. Navigate to the **DEVICES** panel  and select the device.

1. Click on **Desync device(s)** to de-sync the client from the master device.

   ![image1](assets/command-sync/command-sync15-1.png)

1. Click **Confirm** to de-sync the selected device from the master.

   >[NOTE:]
   > If you select the master device and use the de-sync option, then all the devices connected to the master, will be de-synced in one step.
