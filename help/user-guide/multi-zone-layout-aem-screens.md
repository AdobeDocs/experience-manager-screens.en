---
title: Multi-zone Layout
description: Learn how to create multiple zone content and use various assets such as videos, images, and text that can be combined in a single screen in AEM Screens.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 901ed50e-d3f0-4c85-ad79-6c4595382759
---
# Multi-zone Layout {#multi-zone-layout}

The following page describes the usage of multi-zone layout and covers the following topics:

* Overview
* Creating Multi-zone Layout
* Prerequisites
* Using Single Assets in one or more Zones
* Using Sequenced Content in one or more Zones

## Overview {#overview}

***Multi-zone Layout*** lets you create multiple zone content and use various assets such as videos, images, and text that can be combined in a single screen. You can pull in images, videos, and text allowing it all to blend together and create an intuitive digital experience.

As per the project requirements, sometimes you need multiple zones in a channel and edit them as one comprehensive unit. For example, a product sequence with a related social media feed that runs in three separate zones on a single channel.

   >[!NOTE]
   >In multi-zone channels, asset-level scheduling is not recommended due to potential conflicts and unintended behavior. If asset-level scheduling is necessary, it's advised to create a separate sequence channel and apply scheduling logic within that channel. Next, embed the sequence channel into the multi-zone channel.

### Prerequisites {#prerequisites}

Before you start implementing this functionality, make sure you have the conceptual knowledge on:

* [Creating an AEM Screens Project](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/creating-a-screens-project)
* [Creating a Display](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/setting-up-projects/managing-displays)
* [Assigning a Channel to a Display](/help/user-guide/channel-assignment.md)

## Creating Multi-zone Layout {#creating-multi-zone-layout}

While creating a channel, you can use different templates to create zones in your channel. You can add a single image, video, or an embedded channel which allows for multiple assets to be shown in a sequence.

**Creating a Channel**

1. Click the Adobe Experience Manager link (top left) and then **Screens**. Alternatively, you can ﻿go directly to: `http://localhost:4502/screens.html/content/screens`.
1. Navigate to **Channels** folder and click **Create** from the action bar.

1. Click **1x2 Split Screen Channel** from the **Create** wizard.

1. Click **Next** and enter the **title** as **MultiZone**.

1. Click **Create** to complete the channel creation.

### Using Single Assets in one or more Zones {#using-single-assets-in-one-or-more-zones}

You can use single assets such as an image or a video in all individual zones. Follow the steps below for implementation:

1. **Adding Content to the Channel**

    1. Navigate to **Zones** > **Channels**> **MultiZone**.
    1. Click the **MultiZone** channel and click **Edit** from the action bar.

1. **Adding Images to the Channel**

   To play a single image or a video in two zones, simply drag and drop an image to each zone in the channel editor, as shown in the figure below:

   ![image](/help/user-guide/assets/multi-zone/multizone-img3.png)

### Using Sequenced Content in one or more Zones {#using-sequenced-content-in-one-or-more-zones}

If you want the zones to display sequence of images and a video in the different zones, follow steps below for details.

1. **Creating a Channel Folder**

    1. Navigate to **Zones** > **MultiZone** > **Channels** and click **Create** from the action bar.
    1. Click **Channels Folder** from the **Create** wizard and click **Next**.
    1. Enter the title as **EmbeddedChannels** and click **Create**.

   ![screen_shot_2018-12-19at125428pm](assets/screen_shot_2018-12-19at125428pm.png)

1. **Adding two more channels to Channel Folder**

    1. Navigate to **Zones** > **Channels** > **EmbeddedChannels** and click **Create** from the action bar.
    1. Click **Sequence Channel** from the **Create** wizard to create a channel titled as **`Zone1`**.
    1. Click **`Zone1`** and click **Edit** from the action bar.
    1. Drag and drop few images to this channel.
    1. Similarly, create another sequence channel titled as **`Zone2`** in **EmbeddedChannels** folder.
    1. Drag and drop a video to this channel.

    The following figure shows the channels **`Zone1`** and **`Zone2`**:
   
   ![screen_shot_2018-12-19at125930pm](assets/screen_shot_2018-12-19at125930pm.png)

   The images added to editor of **`Zone1`** sequence channel are shown below:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img4.png)

   The video added to editor of **`Zone2`** sequence channel is shown below:

   ![screen_shot_2018-12-19at125930pm](/help/user-guide/assets/multi-zone/multizone-img5.png)

1. **Adding Embedded Sequences (component) to main channel (MultiZone)**

    1. Navigate to **Zones** > **Channels** > **MultiZone**.
    1. Click **Edit** from the action bar.
    1. Drag and drop the **Embedded Sequence** component to both the zones.
    1. Click the embedded sequence in one of the zones.
    1. Click the **Configure** (wrench) icon to one of the embedded sequences in the editor.
    1. Click the channel path as **Zones** > **Channels** > **EmbeddedChannels** > **`Zone1`**, as shown in the figure below.
    1. Similarly, add the **`Zone2`** to another embedded sequence component in the editor. 

       ![image](/help/user-guide/assets/multi-zone/multizone-3.png)

### Creating a Location and a Display {#creating-location}

Create a location and a display so you can view the content in the AEM Screens Player.

1. **Creating a Location**

   1. Navigate to **Zones** > **Locations** folder.
   1. Click the **Locations** folder and click **Create** from the action bar.
   1. Click **Location** from the **Create** wizard and click **Next**.
   1. Enter the **Title** as **SanJose** and click **Create**.

1. **Creating a Display**

   1. Navigate to **Zones** > **Locations** folder.
   1. Click the **SanJose** location and click **Create** from the action bar.
   1. Click **Display** from the **Create** wizard and click **Next**.
   1. Enter the **Title** as **Lobby** and click **Create**.

### Assigning Channels to the Display {#channel-channel}

Assign the channels to the display to view the content. Follow the steps below to assign the channel to the display.

1. **Assigning Channel to the Display**

   1. Navigate to **Zones** > **Locations** > **SanJose**> **Lobby**.
   1. Click the **Lobby** display and click **Assign Channel** from the action bar.
   1. Enter the path to the **MultiZone** channel in **Channel Path**.
   1. Set the **Supported Events** as **Initial Load**, **Idle Screen**, and **Timer**.
   1. Click **Save**.

      ![image](/help/user-guide/assets/multi-zone/multizone-img9.png)
   1. Similarly, assign the other two embedded channels (**`Zone1`** and **`Zone2`**) to this display.
   1. After you assign all three channels to the **Lobby** display, you should be able to view the assigned channels from the display dashboard.

      ![image](/help/user-guide/assets/multi-zone/multizone-img8.png)

  
      >[!IMPORTANT]
      >
      >After you assign the main channel (in this case, **MultiZone**) to the display, it is mandatory to assign the other two embedded channels **`Zone1`** and **`Zone2`** also to the same display.

### Registering the Device {#registering-device}

When you have set up a location and a display, follow the steps below to register the device and assign display to the device.

1. **Registering the Device**

   1. Navigate to **Zones** > **Devices** folder.
   1. Click the **Devices** folder and click **Device Manager** from the action bar.
   1. Click **Device Registration** and click the pending device from the list.

      >[!NOTE]
      > The title of the device must match the device token (**Token** field) displayed in the **Device Registration** tab.
   
   1. If the title matches the device token, then click the device and click **Register Device** from the action bar.
   1. If the registration code matches the code in the Screens player **Device Registration** tab, click **Validate** from the action bar.
      ![image](/help/user-guide/assets/multi-zone/multizone-img6.png)
   1. Enter the **Title** as **`Chrome-Device1`** and click **Register**.
   1. Click **Assign Display** and click the path to the device config.

    >[!NOTE]
    >If you are trying to view the content in the Screens player, make sure you click **Update Offline Content** from the channel dashboard for each of the channels assigned to the display.

### Viewing the Result {#viewing-the-result}

When you implement multi-zone layouts using the preceding steps, the following output displays.

Check the Screens player so you can view the output that displays the content in two different zones. The left and the right zones (both use an embedded sequence as a component).

The left zone is a sequence channel and the right zone includes a video.

![new2-1](/help/user-guide/assets/multi-zone/Multi-gif.gif)
