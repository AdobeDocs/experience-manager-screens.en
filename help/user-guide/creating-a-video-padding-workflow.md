---
title: Creating a Video Padding Workflow
description: Learn more about creating a video padding in the workflow for your assets.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
content-type: reference
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 16180f96-2855-4250-9d55-24ed77a908b7
---
# Creating a Video Padding Workflow {#creating-a-video-padding-workflow}

This section covers the following topics:

* **Overview**
* **Prerequisites**
* **Creating a Video Padding Workflow**
    * **Creating a Workflow**
    * **Using the Workflow in AEM Screens Project**

* **Validating the Output for the Workflow**

## Overview {#overview}

The following use case involves placing a video (example: 1280 x 720) in a channel where the display is 1920 x 1080 and having the video be placed at 0x0 (upper left). The video should not be stretched or modified in any way and do not use **Cover** in the video component.

The video is displayed as an object from pixel 1 to pixel 1280 across and from pixel 1 to pixel 720 down and the rest of the channel is the default color.

## Prerequisites {#prerequisites}

Before you create a workflow for video, complete the following prerequisites:

1. Upload a video in **Assets** folder in your AEM instance
1. Create an AEM Screens project (for example, **TestVideoRendition**) and a channel named (**VideoRendering**), as shown in the figure below:

![screen_shot_2018-10-17at85307pm](assets/screen_shot_2018-10-17at85307pm.png)

## Creating a Video Padding Workflow {#creating-a-video-padding-workflow-1}

To create a video padding workflow, you must create a workflow for your video and then use the same in your AEM Screens project channel.

Follow the steps below to create and use the workflow:

1. Creating a Workflow
1. Using the Workflow in an AEM Screens Project

### Creating a Workflow {#creating-a-workflow}

Follow the steps below to create a workflow for your video:

1. Navigate to your AEM instance.
1. Click tools from side rail. 
1. Select **Workflow** > **Models** so you can create a model.

   ![screen_shot_2018-10-17at90025pm](assets/screen_shot_2018-10-17at90025pm.png)

1. Click **Models** > **Create** > **Create Model**. Enter the **Title** (as **VideoRendition**) and **Name** in the **Add Workflow Model**. Click **Done** to add the workflow model.

   ![screen_shot_2018-10-17at90747pm](assets/screen_shot_2018-10-17at90747pm.png)

1. Once you create the workflow model, select the model (**VideoRendition**), and click **Edit** from the action bar.

   ![screen_shot_2018-10-17at91256pm](assets/screen_shot_2018-10-17at91256pm.png)

1. Drag and drop the **`Command Line`** component to your workflow.

   ![screen_shot_2018-10-22at14846pm](assets/screen_shot_2018-10-22at14846pm.png)

1. Select the **`Command Line`** component and open the properties dialog box.

   ![screen_shot_2018-10-17at95752pm](assets/screen_shot_2018-10-17at95752pm.png)

1. Select the **Arguments** tab.
1. In the **Command Line - Step Properties** dialog box, enter the format in the **Mime Types** (as ***video/mp4***) and the command as (***/usr/local/Cellar/ffmpeg -i ${filename} -vf "pad=1920:height=1080:x=0:y=0:color=black" cq5dam.video.fullhd-hp.mp4***). This command starts the workflow in the **Commands** field.

   See the details on **Mime Types** and **Commands** in the note below.

   ![screen_shot_2018-10-18at105300am](assets/screen_shot_2018-10-18at105300am.png)

1. Select the workflow (**VideoRenditions**).
1. Click **Start Workflow** from the action bar.

   ![screen_shot_2018-10-18at105335am](assets/screen_shot_2018-10-18at105335am.png)

1. In the **Run Workflow** dialog box, select the path of your asset in the **Payload** (as ***/content/dam/huseinpeyda-crossroads01_512kb 2.mp4***) and enter the **Title** as ***RunVideo*** and click **Run**.

   ![screen_shot_2018-10-18at112043am](assets/screen_shot_2018-10-18at112043am.png)

### Using the Workflow in an AEM Screens Project {#using-the-workflow-in-an-aem-screens-project}

Follow the steps below to use the workflow in your AEM Screens project:

1. Navigate to an AEM Screens project (**TestVideoRendition** > **Channels** >**VideoRendition**).

   ![screen_shot_2018-10-17at100715pm](assets/screen_shot_2018-10-17at100715pm.png)

1. Click **Edit** from the action bar. Drag and drop the video that you initially uploaded to **Assets**.

   ![screen_shot_2018-10-17at102806pm](assets/screen_shot_2018-10-17at102806pm.png)

1. Once you have uploaded the video, click **Preview** to view the output.

   ![screen_shot_2018-10-22at15151pm](assets/screen_shot_2018-10-22at15151pm.png)

## Validating the Output for the Workflow {#validating-the-output-for-the-workflow}

You can validate your output by:

* Check preview of the video in the channel
* Navigate to the ***/content/dam/testvideo.mp4/jcr:content/renditions/cq5dam.video.fullhd-hp.mp4*** in CRXDE Lite, as shown in the figure below:

![screen_shot_2018-10-22at14326pm](assets/screen_shot_2018-10-22at14326pm.png)
