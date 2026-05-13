---
title: Channel Level Bulk Image Playback Duration
description: Learn how you can edit the playback duration of a specific image component in AEM Screens.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 95aa761a-1449-4e18-8115-3b151036dc54
TQID: https://experienceleague.adobe.com/6Cq6n8lfTfRC685rE4jWmnAQDPLsDJ4ptNTNjt-qmHc
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a5fd0e22-1a77-4f49-a6af-7a57fff19aed
    internal-label: Authoring Screens
subfeature_v2:
  - id: f5973e90-a5a3-4b84-8602-ee120d4ce9b1
    internal-label: Content
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# Channel Level Bulk Image Playback Duration {#channel-level-bulk-image-playback-duration}

## Overview {#overview}

When you create a sequence channel and add images to it, by default, all images assume the playback duration defined in the Channel level configuration. Any individual image can still override the default and have a different playback duration. This ability is accomplished by editing the playback duration of the specific image component.

### Prerequisites {#prerequisites}

Before beginning to implement this functionality, make sure you have set up a project as a prerequisite to start implementing this functionality. For example,

1. Create an AEM Screens project example, **ChannelLevelPlayback**. 

1. Create a sequence channel as **PlaybackChannel** under the **Channels** folder.

1. Add content to **PlaybackChannel**.

## Editing Channel Level Image Playback Duration Assignment {#editing-channel-level-image-playback-duration-assignment}

The section below explains how you can edit the playback duration of content in an AEM Screens channel.

### Updating the Playback Duration for Images in a Channel {#updating-the-playback-duration-for-images-in-a-channel}

Follow the steps below to learn how to update Channel Level Image Playback Duration Assignment:

1. Navigate to the sequence channel **PlaybackChannel**.

   ![screen_shot_2019-06-24at62818pm](assets/screen_shot_2019-06-24at62818pm.png)

1. Click **Edit** from the action bar.

   ![screen_shot_2019-06-24at70141pm](assets/screen_shot_2019-06-24at70141pm.png)

1. Add two or more images in the channel editor, as shown in the figure below.

   ![screen_shot_2019-06-24at90534pm](assets/screen_shot_2019-06-24at90534pm.png)

1. Click all the images in the channel and click the wrench icon on the top-left (as shown in the figure below) so you can open the Channel level Configure dialog box.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. The **Page** dialog box opens.

   >[!NOTE]
   >By default, the images in a channel are set to a playback duration of 8 seconds.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Edit the **Duration** from 8000 (milliseconds) to 3000 (milliseconds), that is, 3 seconds. Click the check mark on the top right of the **Page** dialog box so you can save your changes.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Viewing the Result {#viewing-the-result}

After you have updated the channel playback duration (in this example, all three images), notice that the images now play for 3 seconds rather than 8 seconds (the default value).

![channel_preview](assets/channel_preview.gif)
