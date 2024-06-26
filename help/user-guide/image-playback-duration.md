---
title: Image Playback Duration
description: Learn about image playback duration in AEM Screens.
contentOwner: jsyal
---

# Image Playback Duration {#image-playback-duration}

## Overview {#overview}

After you create a sequence channel and add images to it, by default, all images assume the playback duration defined in the Channel level configuration. Any individual image can still override the default and have a different playback duration. This ability is accomplished by editing the playback duration of the specific image component.

### Prerequisites {#prerequisites}

Before implementing this functionality, make sure you have set up a project as a prerequisite to start implementing this functionality. For example,

1. Create an AEM Screens project (in this example, **ChannelLevelPlayback**)  
1. Create a sequence channel as **PlaybackChannel** under the **Channels** folder
1. Add content to **PlaybackChannel**

## Editing Channel Level Image Playback Duration Assignment {#editing-channel-level-image-playback-duration-assignment}

The section below explains how to edit the playback duration of content in an AEM Screens channel.

### Updating the Playback Duration for Images in a Channel {#updating-the-playback-duration-for-images-in-a-channel}

Follow the steps below to learn how to update Channel Level Image Playback Duration Assignment:

1. Navigate to the sequence channel **PlaybackChannel**.

   ![screen_shot_2019-06-24at62818pm](assets/screen_shot_2019-06-24at62818pm.png)

1. Click **Edit** from the action bar.

   ![screen_shot_2019-06-24at70141pm](assets/screen_shot_2019-06-24at70141pm.png)

1. Add two or more images in the channel editor, as shown in the figure below.

   ![screen_shot_2019-06-24at90534pm](assets/screen_shot_2019-06-24at90534pm.png)

1. Click all the images in the channel and click the wrench icon on the top-left (as shown in the figure below). The Channel level Configure dialog box is opened.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. The **Page** dialog box opens.

   >[!NOTE]
   >
   >By default, the images in a channel are set to a playback duration of 8 seconds.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Edit the **Duration** from 8000 (milliseconds) to 3000 (milliseconds), that is, 3 seconds. Click the check mark on the top-right of the **Page** dialog box so you can save your changes.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Viewing the Result {#viewing-the-result}

When you have updated the channel playback duration (in this example, all three images), notice that the images now play for 3 seconds rather than 8 seconds (the default value).

![channel_preview](assets/channel_preview.gif)

