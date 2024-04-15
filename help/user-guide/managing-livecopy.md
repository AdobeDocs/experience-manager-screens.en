---
title: Creating and Managing a Live Copy
description: Learn how to create and manage Live Copies of channels in AEM Screens.
contentOwner: jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 4a4b3a83-2b02-42a0-86a7-fce6bbf47c7d
---
# Creating and Managing a Live Copy {#creating-and-managing-a-live-copy}

This page describes creating and managing Live Copies of channels.

A ***Live Copy*** is a copy of specific site content for which a live relationship with the original source is maintained. This live relationship allows the live copy to inherit content and page properties from the source.

This page describes creating live copy of a channel, viewing properties, checking status, and propagating changes from a channel to its live copy.


## Creating a Live Copy {#creating-a-live-copy}

Follow the steps below to create a live copy of a channel in your project folder.

1. Select the Adobe Experience Manager link (top left) and then **Screens**. Alternatively, you can ﻿go directly to: `http://localhost:4502/screens.html/content/screens`.

1. Navigate to Screens project and select **Channels**.
1. Select **Create** and select **Live Copy** so you can create a live copy of the channel.
1. Select the destination and select **Next**.
1. Select the location where the live copy can reside.
1. Enter the **Title** and **Name** in the **Create Live Copy** page.

1. Select **Open** to view the contents of new live copy or **Done** to return to the main page.

Alternatively, see the steps below for visual representation for creating a new live copy of a channel.

The following example shows the creation of a live copy (***IdleLiveCopy***) for ***Idle Channel*** with destination folder as ***Channels***.

![chlimage_1-2](assets/chlimage_1-2.gif)

## Viewing Content of the Live Copy Channel {#viewing-content-of-the-live-copy-channel}

A Live copy is a copy of a channel that exists.

To view the content of your live copy, see the steps below:

1. Navigate to Screens project and select the location where you originally created live copy as shown in the section above. (Here, the location was chosen as **Channels** folder)

   ![chlimage_1-18](assets/chlimage_1-18.png)

1. Select **Edit** from the action bar.

   ![chlimage_1-19](assets/chlimage_1-19.png)

   >[!NOTE]
   >
   >When viewing content for a live copy channel, you view an extra item in the menu as **Live Copy Status**. See the section below for more details.

### Viewing Properties of a Live Copy {#viewing-properties-of-a-live-copy}

Also, you can view the properties of your live copy channel.

1. Navigate to your live copy channel and select **Properties** from the action bar.

   ![chlimage_1-20](assets/chlimage_1-20.png)

1. Select the **Live Copy** tab so you can view details of your channel.

   ![chlimage_1-21](assets/chlimage_1-21.png)

### Live Copy Status {#live-copy-status}

The mode **Live Copy Status**, as shown in the figure below, lets you view the relationship status of all the assets in the channel.

1. Select **Edit** so you can choose the **Live Copy Status** and view the association of your channel content to the original channel (from which the live copy is generated).

   ![chlimage_1-22](assets/chlimage_1-22.png)

1. Select **Live Copy Status** so you can display the preview page.

   All the resources with green border show that the content is inherited from the original channel.

   ![chlimage_1-23](assets/chlimage_1-23.png)

### Breaking the Inheritance {#breaking-the-inheritance}

You can also cancel the inheritance from the live copy, so the content becomes independent of the original branch.

The following example shows that you select the image in the edit mode and select the cancel inheritance symbol on the top right.

![chlimage_1-24](assets/chlimage_1-24.png)

### Propagating Changes to the Live Copy Channel {#propagating-changes-to-the-live-copy-channel}

If you make changes or updates in the original channel, propagate those changes to your Live Copy channel too.

Follow the steps below to ensure that your changes are propagated from the original channel to the live copy channel:

1. Select the original channel (***Idle Channel***) and select **Edit** from the action bar.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Make edits to this channel content. For example, delete an image from this channel.

   ![chlimage_1-26](assets/chlimage_1-26.png)

1. Select the live copy of the channel (***IdleLiveCopy***) and select **Edit** from the action bar. Notice that the image you deleted is still visible in the live copy.

   To propagate the changes, synchronize the channel.

   ![chlimage_1-27](assets/chlimage_1-27.png)

1. To propagate changes to the live copy channel, navigate to the AEM dashboard and select the live copy channel and select **Properties** from the action bar.

   ![chlimage_1-28](assets/chlimage_1-28.png)

1. Select the **Live Copy** tab and select **Synchronize** from the action bar.

   ![chlimage_1-29](assets/chlimage_1-29.png)

1. Select **Sync**, then select **Save & Close** to navigate back to the AEM dashboard.

   ![chlimage_1-30](assets/chlimage_1-30.png)

   Notice that the image is now deleted from the live copy channel too.
