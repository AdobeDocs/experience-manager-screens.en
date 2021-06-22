---
title: MultiZone to SingleZone Transitions Use Case
description: Follow this page to learn about MultiZone to SingleZone Transitions use case.
seo-description: MultiZone to SingleZone Transitions use case.
contentOwner: Jyotika Syal
feature: Authoring Screens
role: Developer, Business Practitioner
level: Intermediate
exl-id: 15632f31-1e92-40e5-b567-8705e27bdc93
---
# Multi-Zone to Single-Zone Transition {#multizone-to-singlezone-use-case}


## Use Case Description {#use-case-description}

This section describes a use case example that emphasizes on how to set up a multi-zone layout channel that alternates with a single-zone layout channel. The multi-zone channel has sequencing image/video assets and it shows how you can set up project that alternates from multi-zone to single-zone and vice-versa.

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

    1. Select the **Channels** folder and click **Create** from the action bar to open the wizard to create a channel.
    1. Select **Left-L Bar Split Screen Channel** from the wizard and create the channel titled as **MultiZoneLayout**.
    1. Add content to the channel. Drag and drop the assets to each of the zones. The following example shows a **MultiZoneLayout** channel comprising of a video, an image and a text banner (in an embedded sequence), as shown below.

    ![asset](assets/mz-to-sz2.png)

    >[!NOTE]
    >
    >To learn more about creating a multi-zone layout in your channel, refer to [Multi-zone Layout](multi-zone-layout-aem-screens.md).

      
1. Create another channel titled as **TakeoverChannel** to your **Channels** folder.

   ![asset](assets/mz-to-sz3.png)

1. Click **Edit** from the action bar to add content to this channel. Add a **Channel** component and an image asset that you want to switch to, to this channel, as shown in the figure below:

   ![asset](assets/mz-to-sz4.png)

1. Open the settings for the Channel component and point it to the **MultiZoneLayout** channel that you created  in *step 2*.

   ![asset](assets/mz-to-sz5.png)

1. Set the duration from the **Sequence** field to **10000 ms**.

   ![asset](assets/mz-to-sz6.png)   

1. Similarly, open the settings for the Image (asset you added)  and set its duration from the **Sequence** field to **3000 ms**.

   ![asset](assets/mz-to-sz7.png)   

## Checking the Preview {#checking-the-preview}

You can view the desired output from the player or just by clicking on the **Preview** from the editor.

The output will demonstrates how a multi-zone layout plays for *10000 ms* and then switches to single zone layout that has playback duration of *3000 ms* and then switches back to the multi-zone layout.

   >[!VIDEO](https://video.tv.adobe.com/v/30366)

>[!NOTE]
>
>You can customize your channel transition (from multi-zone to single-zone layout or vice-versa), as per your requirements.
