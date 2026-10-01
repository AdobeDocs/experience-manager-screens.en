---
title: MultiZone to SingleZone Transitions use case
description: Follow this page so you can learn about the MultiZone to SingleZone Transitions use-case.
contentOwner: Jyotika Syal
feature: Authoring Screens
role: Developer, User
level: Intermediate
exl-id: 15632f31-1e92-40e5-b567-8705e27bdc93
TQID: https://experienceleague.adobe.com/MTRkmtP5J3PL13VZWm9nalthBX-03nu-Z2OsbnMO1Q4
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
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
---
# Multi-Zone to Single-Zone Transition {#multizone-to-singlezone-use-case}

## Use case description {#use-case-description}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

This section describes a use-case example that emphasizes on how to set up a multi-zone layout channel that alternates with a single-zone layout channel. The multi-zone channel has sequencing image/video assets and it shows how you can set up a project that alternates from multi-zone to single-zone and conversely.

### Preconditions {#preconditions}

Before you start this use case, make sure you understand how to:

* **[Create and Manage Channels](managing-channels.md)**
* **[Create and Manage Locations](managing-locations.md)**
* **[Create and Manage Schedules](managing-schedules.md)**
* **[Device Registration](device-registration.md)**

### Primary Actors {#primary-actors}

Content Authors

## Setting up the Project {#setting-up-the-project}

Follow the steps below to set up a project:

1. Create an AEM Screens Project named as **TakeoverLoop**, as shown below.

   ![asset](assets/mz-to-sz1.png)


1. **Creating a Multi-Zone Screens Channel**

    1. Click the **Channels** folder and click **Create** from the action bar and opening the wizard so you can create a channel.
    1. Click **Left-L Bar Split Screen Channel** from the wizard and create the channel titled as **MultiZoneLayout**.
    1. Add content to the channel. Drag and drop the assets to each of the zones. The following example shows a **MultiZoneLayout** channel comprising a video, an image, and a text banner (in an embedded sequence), as shown below.

    ![asset](assets/mz-to-sz2.png)

    >[!NOTE]
    >
    >To learn more about creating a multi-zone layout in your channel, see [Multi-zone Layout](multi-zone-layout-aem-screens.md).

      
1. Create another channel titled as **TakeoverChannel** to your **Channels** folder.

   ![asset](assets/mz-to-sz3.png)

1. Click **Edit** from the action bar so you can add content to this channel. Add a **Channel** component and an image asset that you want to switch to for this channel, as shown in the figure below:

   ![asset](assets/mz-to-sz4.png)

1. Open the settings for the Channel component and point it to the **MultiZoneLayout** channel that you created in *step 2*.

   ![asset](assets/mz-to-sz5.png)

1. Set the duration from the **Sequence** field to **10000 milliseconds**.

   ![asset](assets/mz-to-sz6.png)   

1. Similarly, open the settings for the Image (asset you added) and set its duration from the **Sequence** field to **3000 milliseconds**.

   ![asset](assets/mz-to-sz7.png)   

## Checking the Preview {#checking-the-preview}

You can view the desired output from the player or just by selecting **Preview** from the editor.

The output demonstrates how a multi-zone layout plays for *10000 milliseconds*. Then, it switches to a single zone layout that has a playback duration of *3000 milliseconds*. And finally, it switches back to the multi-zone layout.

>[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>You can customize your channel transition (from multi-zone to single-zone layout or conversely), as per your requirements.

