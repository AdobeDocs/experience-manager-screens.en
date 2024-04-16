---
title: Project Level Image Playback Duration
description: Learn how you define image playback duration at the project level. 
contentOwner: jsyal
---

# Project Level Image Playback Duration {#project-level-image-playback}

## Overview {#overview}

This feature lets you define image playback duration at the project level. All images inherit this playback duration by default. If no duration is defined at the project level, the default playback of 8 seconds continues.

### Prerequisites {#prerequisites}

Before using this feature, set up a project as a prerequisite to start implementing this functionality. For example,

1. Create an AEM Screens project (in this example, **ProjectLevelPlayback**).
1. Create a sequence channel as **PlayBackChannel** under **Channels** folder.
1. Add content to **PlayBackChannel**.

   ![assets](assets/image_playback1.png)

   For instance, the following image showcases the images added to the **PlayBackChannel** editor:

   ![assets](assets/image_playback2.png)

## Editing Project Level Image Playback Duration Assignment {#editing-project-level-image-playback-duration-assignment}

The section below explains how to edit the playback duration of content in an AEM Screens project.

### Updating the Playback Duration for Images at a Project Level {#updating-the-playback-duration-for-images-in-a-project}


>[!NOTE]
>
>If you want to update an image or channel level playback duration, see [Channel Level Image Playback Duration](channel-level-image-playback.md).

Follow the steps below to learn how to update Project Level Image Playback Duration:

1. Navigate to your project **ProjectLevelPlayback** and click **Properties** from the action bar.
    ![assets](assets/image_playback3.png)

1. Click all the images in the channel and click the wrench icon on the top-left (as shown in the figure below) so you can open the Channel level Configure dialog box.

   ![screen_shot_2019-06-25at95945am](assets/screen_shot_2019-06-25at95945am.png)

1. The **Page** dialog box opens.

   >[!NOTE]
   >
   >By default, the images in a channel are set to a playback duration of 8 seconds and the videos play at their default length of duration.

   ![screen_shot_2019-06-25at100343am](assets/screen_shot_2019-06-25at100343am.png)

   Edit the **Duration** from 8000 (milliseconds) to 3000 (milliseconds), that is, 3 seconds. Select the check mark on the top-right of the **Page** dialog box so your changes are saved.

   ![screen_shot_2019-06-25at101527am](assets/screen_shot_2019-06-25at101527am.png)

### Viewing the Result {#viewing-the-result}

After you have updated the channel playback duration (in this example, all three images), notice that the images now play for 3 seconds rather than 8 seconds (default value).

![channel_preview](assets/channel_preview.gif)

