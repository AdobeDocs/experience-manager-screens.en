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
TQID: https://experienceleague.adobe.com/4xxCtO5lD71kiS-dSbTjTgycZDiWkQlHPdJOCVDrv38
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
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Video Renditions {#video-renditions}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

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
