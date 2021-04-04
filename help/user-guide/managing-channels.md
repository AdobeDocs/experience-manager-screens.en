---
title: Creating and Managing Channels
seo-title: Managing Channels
description: Follow this page to learn about creating and managing channels. It also explains channel dashboard and editing content for a channel.
seo-description: Follow this page to learn about creating and managing channels. It also explains channel dashboard and editing content for a channel.
feature: Authoring Screens
role: Administrator, Developer
level: Intermediate
exl-id: 7bbd211a-f54f-42b9-a1b3-516efe6fb579
---
# Creating and Managing Channels {#creating-and-managing-channels}

A Channel displays a sequence of content (images and videos) and also displays a website or a single-page application.

This page shows creating and managing channels for AEM Screens.

**Pre-requisites**:

* [Configuring and Deploying Screens](configuring-screens-introduction.md)
* [Create and Manage Screens Project](creating-a-screens-project.md)

## Creating a New Channel {#creating-a-new-channel}

Once you create your project for AEM Screens, follow the steps below to create a new Channel for your project:

1. Select the Adobe Experience Manager link (top left) and then Screens. Alternatively, you can navigate directly to `https://localhost:4502/screens.html/content/screens`.

1. Navigate to your Screens project and select **Channels** folder.

1. Click **Create** from the action bar.

   ![demochannel](assets/create-channel1.png)

1. Select the **Sequence Channel** template from the **Create** wizard and click **Next**.

   ![demochannel](assets/create-channel2.png)

1. Enter the Title as **ScreensChannel** and click **Create**.

   ![demochannel](assets/create-project4.png)

1. A Sequence channel is is now added to your **Channels** folder.

### Channel Types {#channel-types}

The following template options are available while using the wizard such as:

| **Template option** |**Description** |
|---|---|
| Channels Folder |Allows to create a folder to store collection of channels. |
| Sequence Channel |Allows to create a channel that plays the components sequentially (one by one in a slide show). |
| Application Channel |Allows to showcase your custom web application in Screens player. |
| 1x1 Split Screen Channel |Allows to view the component in a single zone. |
| 1x2 Split Screen Channel |Allows to view the assets in two zones (split horizontally). |
| 2X1 Split Screen Channel |Allows to view the assets in two zones (split vertically). |
| 2x2 Split Screen Channel |Allows to view the assets in four zones (split horizontally and vertically in a matrix). |
| 2 to 3 Split Screen Channel |Allows to view the assets in two zones (split horizontally) with one of the zones being larger than the other one. |
| Left or Right L-Bar Split Screen Channel |Allows content authors to view different types of assets in appropriately sized zones. |

>[!NOTE]
>
>The Split Screen channels split the display into multiple zones so you can play several experiences at the same time, side-by-side. The experiences can either be static assets/text or embedded sequences.

>[!IMPORTANT]
>
> Once you create and add content to your channel, the next step is to create a location followed by creating a display. Furthermore you need to assign that channel to a display. See the resources below at the end of the section to learn more.

## Working with Channels {#working-with-channels}

You can edit, view properties and dashboard, copy, preview, and delete a channel.


![screen_shot_2019-07-24at103723am](assets/screen_shot_2019-07-24at103723am.png)

### Adding/Editing Content to a Channel {#adding-editing-content-to-a-channel}

To add or edit content in a channel, follow the steps below:

1. Select the channel you want to edit (as shown in the figure above).
1. Click **Edit** from the top left corner of the action bar to edit the channel properties. The editor opens that allows you to add assets/components to your channel that you want to publish.

>[!NOTE]
>You can add components to your channel. Refer to **[Adding Components to a Channel](adding-components-to-a-channel.md)** for more details.

![demochannel1](assets/demochannel1.gif)

**Uploading Videos to the Channel** 

Follow the steps below to upload videos to your channel:

1. Select the channel where you want to upload the video.
1. Click **Edit** from the action bar to open the editor.
1. Select **Videos** under Assets and drag and drop the required videos.

>[!NOTE]
>If you encounter issues uploading videos in your channel, see [Troubleshooting Videos](troubleshoot-videos.md).

### Viewing Properties {#viewing-properties}

To view or edit properties of a channel, follow the steps below:

1. Click on the Channel you want to edit.
1. Click **Properties** from the action bar to view/edit the channel properties. The following tabs allow you to change the options.

![properties](assets/properties.gif)

### Viewing Dashboard {#viewing-dashboard}

To view dashboard of a channel, follow the steps below:

1. Select the channel you want to edit.
1. Click **Dashboard** from the action bar to view the dashboard. The **CHANNEL INFORMATION**,**ASSIGNED DISPLAYS**, and **PENDING LAUNCHES** panel opens, as shown in the figure below:

![dashboard](assets/dashboard.gif)

### Channel Information {#channel-information}

The Channel Information panel describes the Channel properties, along with the preview to the channel. Also, it provides you the information on whether the channel is offline or online.

Click on the (**...**) from the **CHANNEL INFORMATION** action bar to view properties, edit the content, or to update cache (offline content) for the channel.

![screen_shot_2017-12-20at82048am](assets/screen_shot_2017-12-20at82048am.png)

#### Viewing the Manifest {#view-manifest}

You can view the manifest from the channel dashboard.

>[!IMPORTANT]
>This option is only available with AEM 6.4 Feature Pack 8 or AEM 6.5 Feature Pack 4.

Follow these steps to enable this option from the channel dashboard:

1. **Set the Channel to Offline**
   1. Select the channel and select **Properties** from the action bar
   1. Navigate to **Channel** tab and make sure that you un-check **Developer Mode (force channel to be online)** option
   1. Click **Save & Close**
1. **Update Offline Content**
   1. Select the channel and select **Dashboard** from the action bar
   1. Navigate to **CHANNEL INFORMATION** panel and click *...*
   1. Click **Update Offline Content**

You should see the **View Manifest** option from the **CHANNEL INFORMATION** panel in the Channel dashboard.

![image1](assets/channel-one.png)


### Online and Offline Channels {#online-and-offline-channels}

>[!NOTE]
>By default, when you create a channel, it is Offline.

When you create a channel, it can either be defined as an online or an offline channel.

An ***Online Channel***, will show the updated content in the real time environment whereas an ***Offline Channel***, shows the cached content.

Follow the steps below to make the channel online:

1. Navigate to the channel as **TestProject** --&gt; **Channels** --&gt; **TestChannel**.

   Select the channel.

   ![screen_shot_2019-08-01at31406pm](assets/screen_shot_2019-08-01at31406pm.png)

   Click **Dashboard** from the action bar to view the status of the player. The **CHANNEL INFORMATION** panel provides information on whether the channel is online or offline.

   ![screen_shot_2019-08-01at31458pm](assets/screen_shot_2019-08-01at31458pm.png)

1. Click **Properties** from the action bar and navigate to the **Channel** tab as shown below:

   ![screen_shot_2019-08-01at31542pm](assets/screen_shot_2019-08-01at31542pm.png)

1. Check the **Developer** **mode (force channel to be online)** to make the channel as online.

   Click **Save & Close** to save your option.

   ![screen_shot_2019-08-01at31658pm](assets/screen_shot_2019-08-01at31658pm.png)

   Navigate back to the channel dashboard and now the **CHANNEL INFORMATION** panel shows the online status of the player.

   ![screen_shot_2019-08-01at31821pm](assets/screen_shot_2019-08-01at31821pm.png)

>[!NOTE]
>If you want to configure your channel again as offline, un-check the Developer mode option from the **Properties** tab (as shown in step (3)) and then from the **CHANNEL INFORMATION** panel click **Update Offline Content**, as shown in the figure below.

![dashboard2](assets/dashboard2.gif)

#### Automatic versus Manual Updates from the Device Dashboard {#automatic-versus-manual-updates-from-the-device-dashboard}

The following table summarizes the events associated with the automatic and manual updates from the device dashboard.

<table>
 <tbody>
  <tr>
   <td><strong>Event</strong></td>
   <td><strong>Device Auto Update</strong></td>
   <td><strong>Device Manual Update</strong></td>
  </tr>
  <tr>
   <td>Change in Online Channel</td>
   <td>Content updated automatically</td>
   <td><p>Content updated on "Device: Push Config"</p> <p>Or,</p> <p>Content updated on <strong><i>Device: Restart</i></strong></p> </td>
  </tr>
  <tr>
   <td>Change in Offline channel but Channel "Push Content" is NOT triggered (no offline package re-creation)</td>
   <td>No content update</td>
   <td>No content update</td>
  </tr>
  <tr>
   <td>Change in Offline Channel and Channel "Push Content" is triggered (new offline package)</td>
   <td>Content updated automatically</td>
   <td><p>Content updated on <strong><i>Device: Push Config</i></strong></p> <p>Or,</p> <p>Content updated on <strong><i>Device: Restart</i></strong></p> </td>
  </tr>
  <tr>
   <td><p>Change in Config</p>
    <ul>
     <li>Display (forced channel)</li>
     <li>Device</li>
     <li>Channel assignments (new channel, removed channel)</li>
     <li>Channel assignment (role, event, scheduling)</li>
    </ul> </td>
   <td>Config updated automatically</td>
   <td><p>Config updated on <strong><i>Device: Push Config</i></strong></p> <p>Or,</p> <p>Config updated on <strong><i>Device: Restart</i></strong></p> </td>
  </tr>
 </tbody>
</table>

### Assigned Displays {#assigned-displays}

The assigned displays panel shows the display associated to the channel. It provides a snapshot of the assigned display along with the resolution.

The associated displays will list in the **Assigned Displays** panel, as shown below:

![chlimage_1-27](assets/chlimage_1-27.png)

>[!NOTE]
>To learn about creating a display in a location, refer to:
>
>* [Create and Manage Locations](managing-locations.md)
>* [Create and Manage Displays](managing-displays.md)
>

Additionally, click on the display in the **ASSIGNED DISPLAYS** panel, to view the display information, as shown below:

![chlimage_1-28](assets/chlimage_1-28.png)

### The Next Steps {#the-next-steps}

The next step after creating a channel and adding/editing content in your channel is to learn how to create a location and display. Furthermore, then assign a channel to that display.

See the following resources, for next steps:

* [Create and Manage Channels](managing-channels.md)
* [Create and Manage Locations](managing-locations.md)
* [Create and Manage Displays](managing-displays.md)
