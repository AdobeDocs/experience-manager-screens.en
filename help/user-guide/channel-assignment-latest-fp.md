---
title: Channel Assignment - Latest FP
seo-title: Channel Assignment - Latest FP
description: Follow this page to learn about Channel Assignment and Day-parting.
---

# Channel Assignment {#channel-assignment}

>[!IMPORTANT]
>This section highlights the channel assignment and scheduling of channels for AEM 6.5.5 Screens Feature Pack and later.

Once you have set up a display, you must assign a channel to a display to view your content.

This page shows assigning a channel to your display.

>[!NOTE]
>You can assign multiple channels to a display.


## Assigning a Channel {#assign-a-channel-new-release}

Follow the sections below to create an AEM Screens project and assign a channel to a display.

### Creating an AEM Screens Project and Channels {#creating-project}

Follow the steps below to set up a project and a channel:

1. Create an AEM Screens Project titled as **DemoScreens**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp1.png)

   >[!NOTE]
   >Refer to [Creating and Managing Projects](creating-a-screens-project.md) to learn how to create an AEM Screens project.

1. Create a sequence channel titled as **Cafeteria** in the **Channels** folder.

1. Select the channel and click **Edit** from the action bar to add content to your channel.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp2.png)

   For example, the **Cafeteria** channel now displays the following images:

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp3.png)

1. Create a Location titled as **SanJose** and a display as **Lobby**.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp4.png)

### Assigning Channel to a Display {#assigning-channel-to-display}

Once you have the project set up complete, you must assign the channel to a display to view the content.

1. Navigate to the required display, for example, **DemoScreens** --&gt; **Locations** --&gt; **SanJose** --&gt; **Lobby**.

1. Tap/click **Assign Channel** from the action bar.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp5.png)

   Or,

   Tap/click **Dashboard** and click **+Assign Channel** from the **ASSIGNED CHANNELS & SCHEDULES** panel.
   
   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp6.png)
   
1. The **Channel Assignment** dialog box opens.

   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

1. From the **Settings** option, you can choose the channel by path or by name, enter the **Channel Role**, **Priority**, **Supported Events**, and **Interruption Methods**. Additionally, you can enable the **Attraction tooltip** from this dialog box.

    ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

   >[!NOTE]
   >Refer to [Channel Properties](#channel-properties) section to learn more about channel assignment properties.

1. From the **Schedules** option select the **Reference Timezone**, **Activation Window** and **Recurrence Schedule**.
   ![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

    >[!NOTE]
   >Refer to [Channel Properties](#channel-properties) section to learn more about channel assignment properties.

1. Click **Save** once you have configured your preferences.

### Viewing the Content in Chrome Player {#viewing-content-output}

This example showcases the output on a Chrome Player. Once you have assigned the channel to your display, you must register the device to a player.

Refer to [Device Registration](device-registration.md) to learn how to register a device on an AEM Screens player.

You will view the following output on your choice of player:

 ![new1](assets/channel-assignment/channel-assign-output.gif)

### Understanding Channel Properties from Channel Assignment Dialog Box {#channel-properties}

The following properties are set from the **Settings** option in the **Channel Assignment** dialog box.

![image](/help/user-guide/assets/channel-assignment/channel-assign-fp7.png)

#### Select a Channel {#select-channel}

Selecting a channel allows you to provide a reference to the desired channel, either by channel name or by channel path.

* **by path**: you provide an explicit reference using the absolute path of the channel.

* **by name**: You enter the name of the channel that will resolve to an actual channel by context. This feature allows you to create local version of a channel, in order to dynamically resolve location-specific content. For example, a channel with name *deals of the day*, where the actual content would be different in two cities, but you still have the sane channel role on all the displays.

#### Channel Role {#role-channel}

Channel role defines the context of the display. The role is targeted by various actions and is independent of the actual channel that fulfils the role.

#### Priority {#priority-channel}

Priority is used to order the assignments in case multiple ones match the playing criteria. The one with the highest value will always take precedence over lower values. For example, if there are two channels A and B. A has a priority of 1 and B has a priority of 2, then channel B is displayed, as it has a higher priority than A.

   >[!NOTE]
   >The priority for a channel is set as a number (1 for minimum) in the **Channel Assignment** dialog box, as mentioned above. Additionally, the assigned channels are sorted based on descending priority.

#### Supported Events {#supported-events-channel}

* **Initial Load**: loads the channel when the player is started. It can be assigned to multiple channels in combination with schedule
* **Idle Screen**: loads when the screen is idle. It can be assigned to multiple channels in combination with schedule
* **Timer**: needs to be set when a schedule is provided
* **User Interaction**: the player will switch to the specified channel, if there is a user interaction on the screen (touch) in an idle channel and will load when the screen is touched

#### Interruption Method {#interruption-method-channel}

>[!IMPORTANT]
>
> This option is only available with AEM 6.4 Feature Pack 8 or AEM 6.5 Feature Pack 4.

As a content author, you should be able to specify when a channel is interrupted so you can choose to cut off non-critical content, but have the option to let important content fully play before cutting off playback because of scheduling.

Select from one of following options that are available to set the interruption method from the **Channel Assignment** dialog box:

* **Immediately**: whenever the schedule activates or an update is received, you can cut off the playback and immediately refresh or play the new content
* **At the end of the current item**: when a new schedule activates or an update is received, you have the option to wait for the current item in the sequence to finish playing, and only after that you refresh or play the new content
   >[!NOTE]
   >This option is selected by default.
* **At the end of the sequence**: when a new schedule activates or an update is received, you have the option to wait for the whole sequence to reach its end, and just before the desired sequence, you loop back to the 1st element, you refresh or play the new content

   >[!NOTE]
   >Using the second or third option may result in the scheduling times defined on the assignment to be slightly deferred as the player will wait for the end of the item or sequence (after the specified time) before refreshing. The delay will depend on the playback duration of the item.


The following properties are set from the **Schedule** option in the **Channel Assignment** dialog box.

#### Reference Timezone {#reference-timezone}

The Reference Timezone allows you to select the timezone for your content display.

#### Activation Window {#activation-window}

The Activation Window allows you to select a **Start date** and an **End date** to display your content.

#### Recurrence Schedule {#recurrence-schedule}

The Recurrence Schedule allows you to set a recurring schedule for your content. Click on **+ Add Schedule** to add a recurrence schedule to your channel.

>[!NOTE]
>You can add multiple recurring schedules to your channel.
>Recurrence Schedules introduces *DayParting*, that allows you to set a global schedule with multiple channels running at specific times of the day, and re-use that setup for all your displays at once. 

You can set the following options:

* **Name**: Title of your recurrence schedule.
* **Repeat**: Choose whether the schedule runs **Daily**, **Weekly**, **Monthly**, or **Yearly**.
* **Start**: The start time for your schedule.
* **End**: The ending time for your schedule. You can set the it by:
* **Time**: The schedule will end at a specified time.
* **Duration**: The schedule runs for a particular duration of time in hours or minutes.

### DayParting {#dayparting}

DayParting refers to as splitting up a day into time slots and specifying which content plays at the desired time. AEM Screens allows you to schedule channels in terms of DayParting within a day, week, or month as per the requirement.

The following examples explain DayParting in channels in three different scenarios:

#### Playing content on a single day divided into multiple time slots {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

This example shows how a Restaurant uses DayParting to showcase its breakfast, lunch and dinner menu everyday.

Here, we will divide each day into different time slots, so that channel content plays as per the specified time of the day. Set the following properties of the Recurrence Schedule to play the content as per this use case.

|**Name**|**Repeat**|**Start**|**End**|
|---|---|---|---|
|Breakfast|Daily|6:00 AM|11:00 AM|  
|Lunch|Daily|11:02 AM|3:00 PM|  
|Dinner|Daily|3:01 PM|8:00 PM|  

#### Playing content on a particular day of the week {#playing-content-on-a-particular-day-of-the-week}

This example shows the DayParting implemented in a casino where live event occurs every weekend from 8:00 pm until 10:00 pm and specials are available for dinner menu after 10:00 pm until 1:00 am.

|**Name**|**Repeat**|**Start**|**End**|
|---|---|---|---|
|Weekend|Weekly|8:00 PM|10:00 PM|  
|Special|Daily|10:00 PM|1:00 AM| 

**Weekend**


**Special**

#### Playing content for a particular month/months {#playing-content-for-a-particular-month-months}

This example shows the DayParting for a store that displays their summer collection from the months of June until August and fall collection from September until the end of October.

Here, you will create DayParting as per months, so that channel content plays as per the specified months of the year.


>[!NOTE]
>
>Additionally, you can define ***Priority*** for each of the channels. For example, if two channels are set for the same day and time or for the same month, then the channel with higher priority is played first. The minimum value for priority can be set as 0.

#### Playing content for channels with same priority {#playing-content-for-channels-with-same-priority}

This examples shows the DayParting for a store that displays their winter collection with the same schedule in the month of December. But since the Channel B has priority set as 2, during that week; channel B plays its content rather than Channel A.

## Timeline View {#timeline-view}

Once you have assigned a channel to a display and set up a recurrence schedule, you can view the timeline from the **ASSIGNED CHANNELS & SCHEDULES** panel.

Follow the steps below to navigate to the timeline view:



