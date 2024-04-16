---
title: On-Demand Content Update
description: Learn about On-Demand Content Update for managing publications.
contentOwner: Jyotika Syal
feature: Authoring Screens
role: Developer
level: Intermediate
exl-id: 9ffdb1eb-a1ba-42ac-a30f-260004e5b165
---
# On-Demand Content Update {#on-demand}

This section describes On-demand content for managing publications. 

## Managing Publication: Delivering Content Updates from Author to Publish to Device {#managing-publication-delivering-content-updates-from-author-to-publish-to-device}

You can publish and unpublish content from AEM Screens. The Manage Publication feature lets you deliver content updates from author to publish to device. You can publish/unpublish content for your entire AEM Screens project or only for one of your channels, location, device, application, or a schedule.

### Managing Publication for an AEM Screens Project {#managing-publication-for-an-aem-screens-project}

Follow the steps below to deliver content updates from author to publishing to device for an AEM Screens Project:

1. Navigate to your AEM Screens project.
1. Click **Manage Publication** from the action bar so you can publish the project to your Publish instance.

   ![screen_shot_2019-02-25at21420pm](assets/screen_shot_2019-02-25at21420pm.png)

1. The **Manage Publication** wizard opens. You can click the **Action** and also schedule the publishing time for now or later. Click **Next**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Check the box so you can click the entire project from the **`Manage Publication`** wizard.

   ![screen_shot_2019-02-25at22712pm](assets/screen_shot_2019-02-25at22712pm.png)

1. Click **+ Include Children** from the action bar and uncheck all the options so you can publish all the modules in your project and click **Add** to publish.

   >[!NOTE]
   >
   >By default, all the boxes are checked and you have to manually uncheck the boxes to publish all the modules in your project.

   ![screen_shot_2019-02-25at23116pm](assets/screen_shot_2019-02-25at23116pm.png)

   **Understanding Include Children dialog box**
 
     The steps mentioned above shows how you can publish the entire content. In case you want to use the other three alternatives available, you have to check that particular option.
     For example, the following image show how you can manage and update only the modified pages in your project:
     ![image](assets/author-publish-manage.png)

     Follow the explanations below so you understand the options that are available:

    1. **Include only immediate children**:
       This option lets you manage updates only to the subnodes in your project structure.
    1. **Include only modified pages**:
       This option lets you manage updates only to the modified pages of the project where the changes are found in your project structure.
    1. **Include only already published pages**:
       This option lets you manage updates only to the pages that were published before.


1. From the **`Manage Publication wizard`**, click **Publish**.

   ![screen_shot_2019-02-25at23341pm](assets/screen_shot_2019-02-25at23341pm.png)

   >[!NOTE]
   >
   >Wait for a few seconds/minutes so that the content reaches publish instance.
   >
   >
   >    1. The workflow does not work if there are no changes in the project and nothing for **Update Offline Content**.
   >    1. The workflow will not work if author does not complete the replication process (contents are still uploading to publish instance) after selecting the **Publish** button in the managing publication workflow.

   >[!CAUTION]
   >If as an author or content creator, you want to see the changes in the devices that are attached to the author instance, click **Update Offline Content** from channel dashboard or by selecting the project. In this case, the update offline content is only performed in the author instance.

1. Navigate to the project and click **Update Offline Content** from the action bar. This action forwards the same command to publish instance, so that the offline zips are created on your Publish instance too.

   ![screen_shot_2019-02-25at23451pm](assets/screen_shot_2019-02-25at23451pm.png)


   >[!NOTE]
   >
   >After you have completed the managing publication workflow, and if there is a player pointing to Author instance, trigger the update offline content in author. Doing so creates the update offline on the Author instance.

   >[!CAUTION]
   >
   >Trigger the update offline content in Author instance, if you have a player registered to the author server. Update offline content is not required for the player registered to the Publishing instance.

### Managing Publication for a Channel {#managing-publication-for-a-channel}

Follow the steps below to deliver content updates from Author > Publish > device for a Channel in an AEM Screens Project:

>[!NOTE]
>
>Follow this section only if there are changes in a channel. If a channel does not have any changes after the previous update offline content, then the managing publication workflow for an individual channel will not work.

1. Navigate to your AEM Screens project and click the channel.
1. Click **Manage Publication** from the action bar so you can publish the channel to your Publish instance.

   ![screen_shot_2019-02-07at115800am](assets/screen_shot_2019-02-07at115800am.png)

1. The **Manage Publication** wizard opens. You can click the **Action** and also schedule the publishing time for now or later. Click **Next**.

   ![screen_shot_2019-02-07at120304pm](assets/screen_shot_2019-02-07at120304pm.png)

1. Click **Publish** from the **`Manage Publication`** wizard.

   ![screen_shot_2019-02-07at120507pm](assets/screen_shot_2019-02-07at120507pm.png)

   >[!NOTE]
   >
   >Wait for a few seconds/minutes so that the content reaches publish instance.

1. Triggering **Update Offline Content** in the channel dashboard only pushes the offline content to the Author instance but not the Publishing instance. Steps 1-4 are for pushing offline content to Publish instance.

   ![screen_shot_2019-02-07at21608pm](assets/screen_shot_2019-02-07at21608pm.png)

   >[!CAUTION]
   >
   >Publish first, then trigger the update offline content as summarized in the preceding steps.

### Channel and Device Reassignment: {#channel-and-device-re-assignment}

If you have reassigned a device, publish both the initial display and the new display, once the device has been reassigned to the new display.

Similarly, if you have reassigned a channel, publish both the initial display and the new display, once the channel has been reassigned to the new display.
