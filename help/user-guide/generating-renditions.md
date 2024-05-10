---
title: Video Renditions
description: Learn about generating full HD renditions for your AEM Screens project.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 752c74d7-5d6d-4363-97ef-b96e97d2f6b1
---
# Video Renditions {#video-renditions}

You can generate manual and automatic full HD renditions. The following section describes the workflow to add renditions to your assets.

## Automatically Generating Full HD Renditions {#automatically-generating-full-hd-renditions}

>[!NOTE]
>
>In case the AEM Screens video renditions do not play optimally on your device, contact the hardware vendor for the specifications of the video. Doing so helps you to get the best performance on the device. It helps you to create your own custom video profile where you provide the appropriate parameters for FFMPEG to generate your rendition. Then, use the steps below to add your custom video profile to the list of profiles.
>
>Also, see [Troubleshooting Videos](troubleshoot-videos.md) to debug and troubleshoot video playing in your channel.

Follow the steps below to generate full HD renditions automatically:

1. Click the Adobe Experience Manager link (top-left) and click the hammer icon so you can click **Workflow**.

   Click **Models**.

   ![screen_shot_2018-02-01at123407pm](assets/screen_shot_2018-02-01at123407pm.png)

1. In the workflow model management, click the **DAM Update Asset** model and click **Edit** from the action bar.

   ![step5_-_edit_thedamupdateassetmodel](assets/step5_-_edit_thedamupdateassetmodel.png)

1. In the **DAM Update Asset** window, double-click the **FFmpeg transcoding** step.

   ![screen_shot_2018-02-01at124454pm](assets/screen_shot_2018-02-01at124454pm.png)

1. Click the **Process** tab.
1. Enter the full HD profiles to the list in **Arguments** as the following:
   ***`,profile:fullhd-bp,profile:fullhd-hp`***
1. Click **OK**.

   ![screen_shot_2018-02-02at103340am](assets/screen_shot_2018-02-02at103340am.png)

1. Click **Save** on the top-left of the **DAM Update Asset** screen.

   ![screen_shot_2018-02-02at101830am](assets/screen_shot_2018-02-02at101830am.png)

1. Navigate to **Assets** and upload a new video. Click the video and open the Renditions side rail. Notice the two full HD videos.

   ![step10_-_open_thevideoasset](assets/step10_-_open_thevideoasset.png)

1. Open **Renditions** from the side rail.

   ![step11_-_open_therenditionssiderail](assets/step11_-_open_therenditionssiderail.png)

1. Notice two new full HD renditions.

   ![step12_-_2_new_renditionsareaddedtothevideo](assets/step12_-_2_new_renditionsareaddedtothevideo.png)

## Manually Generating Full HD Renditions {#manually-generating-full-hd-renditions}

Follow the steps below to generate full HD renditions manually:

1. Click the Adobe Experience Manager link (top left) and click the hammer icon so you can click tools and click **Workflow**.

   Click **Models**.

   ![screen_shot_2018-02-01at123407pm-1](assets/screen_shot_2018-02-01at123407pm-1.png)

1. In workflow model management, click the **Screens Update Asset** model, and click the **Start Workflow** to open the **Run Workflow** dialog box.

   ![step5_-_start_a_newscreensupdateassetworkflow](assets/step5_-_start_a_newscreensupdateassetworkflow.png)

1. Click the desired video in the **Payload** and click **Run**.

   ![step6_-_select_thedesiredvideo](assets/step6_-_select_thedesiredvideo.png)

1. Navigate to **Assets**, drill down to your asset, and click it.

   ![step7_-_open_thevideoasset](assets/step7_-_open_thevideoasset.png)

1. Open the **Renditions** side rail. Notice the new full HD renditions.

   ![step8_-_open_therenditionssiderail](assets/step8_-_open_therenditionssiderail.png)
