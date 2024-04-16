---
title: Perpetual TakeOver Channel
description: Follow this Use Case for creating a Perpetual TakeOver Channel.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 5d112f33-a7cf-415e-9ea7-dc18a0356a8d
---
# Perpetual TakeOver Channel {#perpetual-takeover-channel}

The following page showcases a use case that emphasizes on setting up a project on how to create a Perpetual TakeOver channel that plays for a specific time day and time continuously.

## Use Case Description {#use-case-description}

This Use Case explains how to create a channel that *takes over* from the normal playing channel for a display or group of displays. The takeover occurs for a specific day and time perpetually.
For example, there is a Perpetual TakeOver channel that plays every Friday from 9:00 A.M. through 10:00 A.M. During this time, no other channel should play. The following example showcases creation of a perpetual takeover channel that plays allows the content to play every Wednesday for two hours from 2:00 P.M. through 4:00 P.M.

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

**Setting up the Channels and Display**

1. Create an AEM Screens Project titled as **PerpetualTakeOver**, as shown below.

   ![asset](assets/p_usecase1.png)

1. Create a **MainAdChannel** in the **Channels** folder.

    ![asset](assets/p_usecase2.png)

1. Click the **MainAdChannel** and click **Edit** from the action bar. Drag and drop some assets (images, videos, embedded sequences) to your channel.

   ![asset](assets/p_usecase3.png)


   >[!NOTE]
   >The **MainAdChannel** in this example demonstrates a sequence channel that plays content continuously.

1. Create a **TakeOver** channel that takes over the content in **MainAdChannel** and plays every Wednesday from 2:00 P.M. through 4:00 P.M.

1. Click the **TakeOver** and click **Edit** from the action bar. Drag and drop some assets to your channel. The following example showcases a single zone image added to this channel.

   ![asset](assets/p_usecase4.png)

1. Set up a location and display for your channels. For instance, the following location **MainLobby** and display **MainLobbyDisplay** are set up for this project.

   ![asset](assets/p_usecase5.png)

**Assigning Channels to a Display**

1. Click the display **MainLobbyDisplay** from the **Locations** folder. Click **Assign Channel** from the action bar so you can open the **Channel Assignment** dialog box.

   >[!NOTE]
   >To learn how to assign a channel to a display, see **[Channel Assignment](channel-assignment.md)**.

1. Populate the fields (**Channel Path**, **Priority**, and **Supported Events**) from the **Channel Assignment** dialog box and click **Save** to assign the **MainAdChannel** to your display.

    * **Channel Path**: Click the path to the **MainAdChannel** channel
    * **Priority**: Set the priority of this channel as 1.
    * **Supported Events**: Click the **Initial Load** and **Idle Screen**.

   ![asset](assets/p_usecase6.png)

1. Click the display **TakeOver** from the **Locations** folder. Click **Assign Channel** from the action bar so you can assign the takeover channel.

1. Assigning the **TakeOver** channel to your display at a scheduled time and populating the following fields from the **Channel Assignment** dialog box and selecting **Save**:

    * **Channel Path**: Click the path to the **TakeOver** channel
    * **Priority**: Set the priority of this channel greater than the **MainAdChannel**. For instance, the priority set in this example is 8.
    * **Supported Events**: Click the **Idle Screen** and **Timer**.
    * **Schedule**: Enter the text for the schedule that you want this channel to run the display. The text in the **Schedule** mentioned in this example is *on Wednesday after 14:00 and before 16:00*.

         >[!NOTE]
         >To learn more about the expressions you can add to the **Schedule**, see the [Example Expressions](#example-expressions) section below.
    * **active from**: Start date and time.
    * **active until**: End date and time.
    
       For example, the text in **Schedule** and **active from** and **active until** date and time here allows the content to play every Wednesday from 2:00 P.M. until 4:00 P.M..
    

        ![asset](assets/p_usecase7.png)

      Navigate to the display from **TakeOver** > **Locations** > **MainLobby** > **MainLobbyDisplay** and click **Dashboard** from the action bar so you can view the assigned channels with their priorities, as shown below.

      >[!NOTE]
      >It is mandatory to set the priority of the takeover channel as the highest.

      ![asset](assets/p_usecase8.png)
    Now, the **TakeOver** channel takes over the **MainAdChannel** at 2:00 P.M. for two hours until 4:00 P.M. every Wednesday and plays its content from January 09, 2020 until January 31, 2020.

## Example Expressions {#example-expressions}

The following table summarizes few example expressions that you can add to the schedule while assigning channel to a display.

| **Expression** | **Interpretation** |
|---|---|
| before 8:00 A.M. | the channel plays before 8:00 A.M. everyday |
| after 2:00 P.M. | the channel plays after 2:00 P.M. everyday |
| after 12:15 and before 12:45 | the channel plays after 12:15 P.M. everyday for 30 minutes |
| before 12:15 also after 12:45 | the channel plays before 12:15 P.M. everyday and then also after 12:45 P.M. |
| on the first day of January after 2:00 P.M. also on the second day of January also on the third day of January before 3:00 A.M. | the channel starts playing after 2:00 P.M. on January 1, continues playing for the whole day on January 2 all the way until 3:00 A.M. on January 3 |
| on the 1-2 days of January after 2:00 P.M. also on the 2-3 days of January before 3:00 a.m .| the channel starts player after 2:00 P.M. on January 1, continues playing until 3:00 A.M. on January 2, then it starts again on January 2 at 2:00 P.M. and continues playing until 3:00 A.M. on January 3 |

>[!NOTE]
>
>You can also use _military time_ notation (14:00) instead of *A.M./P.M.* (2:00 P.M.).
