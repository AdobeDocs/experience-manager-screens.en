---
title: Channel Assignment - Latest FP
description: Learn about Channel Assignment and Day Parting.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 346eec9a-e291-4b0d-9686-fee1d5a0e7dd
---
# Channel Assignment {#channel-assignment}

>[!IMPORTANT]
>
>This section highlights the channel assignment and scheduling of channels for AEM 6.5.5 Screens Feature Pack and later.

When you have set up a display, assign a channel to a display to view your content.

This page shows assigning a channel to your display, understand channel properties, and DayParting.

>[!NOTE]
>
>You can assign multiple channels to a display.


## Assigning a Channel {#assign-a-channel-new-release}

Follow the sections below to create an AEM Screens project and assign a channel to a display.

### Creating an AEM Screens Project and Channels {#creating-project}

Follow the steps below to set up a project and a channel:

1. Create an AEM Screens Project titled as **DemoScreens**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp1.png)

   >[!NOTE]
   >To learn how to create an AEM Screens project, see [Creating and Managing Projects](creating-a-screens-project.md).

1. Create a sequence channel titled as **Cafeteria** in the **Channels** folder.

1. Select the channel, then select **Edit** from the action bar.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   For example, the **Cafeteria** channel now displays the following images:

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Create a Location titled as **SanJose** and a display as **Lobby**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Assigning Channel to a Display {#assigning-channel-to-display}

When the project setup is complete, you must assign the channel to a display to view the content.

1. Navigate to the required display, for example, **DemoScreens** > **Locations** > **SanJose** > **Lobby**.

1. Tap/click **Assign Channel** from the action bar.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Or,

   Tap/click **Dashboard** from the action bar and click **+Assign Channel** from the **ASSIGNED CHANNELS & SCHEDULES** panel.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)

1. The **Channel Assignment** dialog box opens.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. From the **Settings** option, you can choose the channel **by path** or **by name**, enter the **Channel Role**, **Priority**, **Supported Events**, and **Interruption Methods**. Also, you can enable the attraction tooltip from this dialog box.

    ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >
   >To learn more about channel assignment properties, see [Channel Properties](#channel-properties) section.

1. From the **Schedule** option, select the **Activation Window** and **Recurrence Schedule**.
   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

   >[!NOTE]
   >
   >To learn more about channel assignment properties, see [Channel Properties](#channel-properties) section.

1. Click **Save** once you have configured your preferences.

### Viewing the Content in Chrome Player {#viewing-content-output}

This example showcases the output on a Chrome Player. When you have assigned the channel to your display, register the device to a player.

To learn how to register a device on an AEM Screens player, see [Device Registration](device-registration.md).

You can view the following output on your choice of player:

 ![new1](assets/channel-assignment/channel-assign-output.gif)

## Timeline View {#timeline-view}

Once you have assigned a channel to a display and set up a recurrence schedule, you can view the timeline from the **ASSIGNED CHANNELS & SCHEDULES** panel.

Follow the steps below to navigate to the timeline view:

1. Navigate to the required display, for example, **DemoScreens** > **Locations** > **SanJose** > **Lobby**.

1. Tap/click **Assign Channel** from the action bar.

   Or,

   Tap/click **Dashboard** and click **Timeline** from the **ASSIGNED CHANNELS & SCHEDULES** panel.

   ![image](/help/user-guide/assets/channel-assignment/timeline-1.png)

## Understanding Channel Properties from Channel Assignment Dialog Box {#channel-properties}

The following properties are set from the **Settings** option in the **Channel Assignment** dialog box.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

### Select a Channel {#select-channel}

Selecting a channel lets you provide a reference to the desired channel, either by channel name or by channel path.

* **By path** &ndash; You provide an explicit reference using the absolute path of the channel.
* **By name** &ndash; You enter the name of the channel that resolves to an actual channel by context. This feature lets you create a local version of a channel so you can dynamically resolve location-specific content. For example, a channel with name *deals of the day*, where the actual content would be different in two cities, but you still have the sane channel role on all the displays.

### Channel Role {#role-channel}

Channel role defines the context of the display. The role is targeted by various actions and is independent of the actual channel that fulfills the role.

### Priority {#priority-channel}

Priority is used to order the assignments in case multiple ones match the playing criteria. The one with the highest value always takes precedence over lower values. For example, if there are two channels A and B. A has a priority of 1 and B has a priority of 2, then channel B is displayed, as it has a higher priority than A.

   >[!NOTE]
   >
   >The priority for a channel is set as a number (1 for minimum) in the **Channel Assignment** dialog box, as mentioned above. Also, the assigned channels are sorted based on descending priority.

### Supported Events {#supported-events-channel}

* **Initial Load** &ndash; Loads the channel when the player is started. It can be assigned to multiple channels with a schedule.
* **Idle Screen** &ndash; Loads when the screen is idle. It can be assigned to multiple channels with a schedule.
* **Timer** &ndash; Must be set when a schedule is provided.
* **User Interaction** &ndash; The player switches to the specified channel if there is a user interaction on the screen (touch) in an idle channel and loads when the screen is touched.

### Interruption Method {#interruption-method-channel}

>[!IMPORTANT]
> This option is only available with <!--AEM 6.4 Feature Pack 8 or-->AEM 6.5 Feature Pack 4.

As a content author, you can specify when a channel is interrupted. Doing so lets choose to cut off non-critical content. But it also gives you the option to let important content play back in full before cutting it short because of scheduling.

Select from one of following options that are available to set the interruption method from the **Channel Assignment** dialog box:

* **Immediately** &ndash; Whenever the schedule activates or an update is received, you can cut off the playback and immediately refresh or play the new content
* **End of the current item** &ndash; When a new schedule activates or an update is received, you can optionally wait for the current item in the sequence to finish playing. Then, only after that, you can refresh or play the new content.

   >[!NOTE]
   >This option is selected by default.

* **At the end of the sequence** &ndash; When a new schedule activates or an update is received, you can optionally wait for the whole sequence to reach its end. Then, just before the desired sequence, you can loop back to the first element, refresh, or play the new content.

   >[!NOTE]
   >Using the second or third option may result in the scheduling times defined on the assignment to be slightly deferred. The reason is because the player waits for the end of the item or sequence (after the specified time) before refreshing. The delay depends on the playback duration of the item.

The following properties are set from the **Schedule** option in the **Channel Assignment** dialog box.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp8.png)

### Activation Window {#activation-window}

The Activation Window lets you select a **Start date** and an **End date** to display your content.

### Recurrence Schedule {#recurrence-schedule}

The Recurrence Schedule lets you set a recurring schedule for your content. Select **+ Add Schedule** to add a recurrence schedule to your channel.

>[!NOTE]
>You can add multiple recurring schedules to your channel.
>Recurrence Schedules introduces *DayParting* that lets you set a global schedule with multiple channels running at specific times of the day, and reuse that set up for all your displays at once. 

You can set the following options:

* **Name** &ndash; Title of your recurrence schedule.
* **Repeat** &ndash; Choose whether the schedule runs **Daily**, **Weekly**, **Monthly**, or **Yearly**.
* **Start** &ndash; The start time for your schedule.
* **End** &ndash; The ending time for your schedule. You can set it by time or duration.
   * **Time** &ndash; The schedule ends at a specified time.
   * **Duration** &ndash; The schedule runs for a particular duration of time in hours or minutes.

### DayParting {#dayparting}

Day Parting refers to splitting up a day into time slots and specifying which content plays at the desired time. AEM Screens lets you schedule channels in terms of DayParting within a day, week, or month as per the requirement.

The following examples explain DayParting in channels in three different scenarios:

#### Playing content on a single day divided into multiple time slots {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

This example shows how a restaurant uses DayParting to showcase its breakfast, lunch, and dinner menu everyday.

Here, each day is divided into different time slots, so that channel content plays as per the specified time of the day. Set the following properties of the Recurrence Schedule for your channel to play the content as per this use case.

|**Name**|**Repeats**|**Start**|**End**|
|---|---|---|---|
|Breakfast|Daily|6:00 A.M.|11:00 A.M.|  
|Lunch|Daily|11:00 A.M.|3:00 P.M.|  
|Dinner|Daily|3:00 P.M.|8:00 P.M.|  

#### Playing content on a particular day of the week {#playing-content-on-a-particular-day-of-the-week}

This example shows the DayParting implemented in a casino where live event occurs every weekend from 8:00 P.M. until 10:00 P.M. and specials are available for dinner menu after 10:00 P.M. until 1:00 A.M.

|**Name**|**Repeats**|**Start**|**End**|
|---|---|---|---|
|Weekend|Weekly: Saturday and Sunday|8:00 P.M.|10:00 P.M.|  
|Specials|Daily: Monday through Friday|10:00 P.M.|1:00 A.M.| 

>[!NOTE]
>
>Also, you can define ***Priority*** for each of the channels. For example, if two channels are set for the same day and time or for the same month, then the channel with higher priority is played first. The minimum value for priority can be set as 0.
