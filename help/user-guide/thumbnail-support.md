---
title: Thumbnail Support for Videos in AEM Screens
description: Learn how to add Thumbnail Support for Videos in AEM Screens.
exl-id: d2d87807-1699-47e3-b241-07c5b7e56f15
---
# Thumbnail Support for Videos {#thumbnail-support-videos}

## Introduction {#introduction}

A content author can define a thumbnail for videos so that the image is used as a placeholder and properly test content playback and targeting, while the actual video is being finalized by the appropriate team. The image can also be used in case the playback of the video fails.

Adding support for a thumbnail image on the video component lets the customer properly add a valid component in the channel, with actual content, and perform any targeting configurations before the video is delivered. 

>[!NOTE]
>The thumbnail image, if set on the video component, is played if there is video playback failure on the player. This lets you deliver the desired message to the audience (by playing  content) instead of completely skipping it.

Thumbnail Support allows you to:

* Prepare a channel experience when the videos are not yet ready, or when you do not necessarily want to test a large asset download on the players

* Set a fallback mechanism, in case there are playback issues on the device.

## Using Thumbnails in Videos {#using-thumbnails}

Follow the steps below to use thumbnail in videos:

1. Navigate to an existing AEM Screens channel or create a channel.

1. Click the channel and click **Edit** from the action bar.

   ![image](/help/user-guide/assets/thumbnails/thumbnail-1.png)

1. Add or edit an existing video component, as shown in the figure below.

   ![image](/help/user-guide/assets/thumbnails/thumbnail-2.png)

1. Click the video and click the *wrench* icon.

   ![image](/help/user-guide/assets/thumbnails/thumbnail-3.png)

1. The **Video** dialog box opens where you can view the **Thumbnail** drop zone.

   ![image](/help/user-guide/assets/thumbnails/thumbnail-4.png)

1. Drag and drop an image from the asset picker to the **Thumbnail** drop zone and click **Done**.

   ![image](/help/user-guide/assets/thumbnails/thumbnail-5.png)

1. Click **Preview**.

1. If a video is set on the component, the video plays. If not, and the thumbnail is set, then the thumbnail plays. Otherwise, the component is considered not configured and is skipped.

## Supported Use Cases while using Thumbnail in Videos {#understand-use-case}

Thumbnail in videos supports the following use cases:

* A video component with nothing setup is skipped.

* A video component with only the thumbnail set plays the thumbnail.

* A video component with both the video (if the video has correct rendition) and thumbnail set plays the video.

* A video component with the video set plays the thumbnail, if there is a playback error, or skips to the next item in case the thumbnail is not configured.
