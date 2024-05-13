---
title: Channel Assignment
description: Learn about Channel Assignment and Day-parting.
feature: Authoring Screens, Channel Assignment
role: Admin, Developer
level: Intermediate
exl-id: 6ed86bfc-38c7-4ced-b472-db2a362585c5
---
# Channel Assignment {#channel-assignment}

>[!IMPORTANT]
>This section highlights the Channel Assignment and scheduling of channels for Feature packs older than AEM 6.5.5 Screens version.

When you have set up a display, assign a channel to a display to view your content.

This page shows assigning a channel to your display.

>[!NOTE]
>You can assign multiple channels to a display.

## Assigning a Channel {#assign-a-channel}

Follow the steps below to assign a channel to a display:

1. Navigate to the required display, for example, **DemoProject** > **Locations** > **SanJose** > **StoreDisplay**.

   ![image](assets/screen_shot_2018-08-23at25359pm.png)

1. Click **Assign Channel** in the action bar.

   or,

   Click **Dashboard** and click **+Assign Channel** from the **ASSIGNED CHANNELS** panel so you can open the **Channel Assignment** dialog box.

   ![image](/help/user-guide/assets/channel-assign1.png)

   You can configure the properties from the **Channel Assignment** dialog box from the section below. See the [Channel Properties](#channel-properties) section for more information about channel properties.

## Understanding Channel Properties from Channel Assignment {#channel-properties}

### Reference Channel {#ref-channel}

A Reference channel lets you provide a reference to the desired channel, either by channel name or by channel path.

* **by path** &ndash; You provide an explicit reference using the absolute path of the channel.

* **by name** &ndash; You enter the name of the channel that resolves to an actual channel by context. This feature lets you create a local version of a channel so you can dynamically resolve location-specific content. For example, a channel with name *deals of the day*, where the actual content would be different in two cities, but you still have the sane channel role on all the displays.

### Channel Role {#role-channel}

Channel role defines the context of the display. The role targets various actions and is independent of the actual channel that fulfills the role.

### Priority {#priority-channel}

Priority is used to order the assignments in case multiple ones match the playing criteria. The one with the highest value always takes precedence over lower values. For example, if there are two channels A and B. A has a priority of 1 and B has a priority of 2, then channel B is displayed, as it has a higher priority than A.

   >[!NOTE]
   >The priority for a channel is set as a number (1 for minimum) in the **Channel Assignment** dialog box, as mentioned above. Also, the assigned channels are sorted based on descending priority.

### Supported Events {#supported-events-channel}

* **Initial Load** &ndash; Loads the channel when the player is started. It can be assigned to multiple channels with a schedule.
* **Idle Screen** &ndash; Loads when the screen is idle. It can be assigned to multiple channels with a schedule.
* **Timer** &ndash; Must be set when a schedule is provided.
* **User Interaction** &ndash; The player switches to the specified channel if there is a user interaction on the screen (touch) in an idle channel and loads when the screen is touched.

### Interruption Method {#interruption-method-channel}

>[!IMPORTANT]
>
> This option is only available with <!--AEM 6.4 Feature Pack 8 or -->AEM 6.5 Feature Pack 4.

As a Content Author, specify when a channel is interrupted. Doing so lets you cut off non-critical content if desired, but optionally let important content play before cutting off its playback because of scheduling.

Click from one of the following options that are available to set the interruption method from the **Channel Assignment** dialog box:

* **Immediately** &ndash; Whenever the schedule activates or an update is received, you can cut off the playback and immediately refresh or play the new content.
* **At end of current item** &ndash; When a new schedule activates or an update is received, you can optionally wait for the current item in the sequence to finish playing. Only after that can you refresh or play the new content.

   >[!NOTE]
   >This option is selected by default.
* **At the end of the sequence** &ndash; When a new schedule activates or an update is received, you can optionally wait for the whole sequence to reach its end. Then, just before the desired sequence, you can loop back to the first element, refresh, or play the new content.

   >[!NOTE]
   >Using the second or third option may result in the scheduling times defined on the assignment to be slightly deferred. The reason is because the player waits for the end of the item or sequence (after the specified time) before refreshing. The delay depends on the playback duration of the item.

### Schedule {#schedule-channel}

Schedule lets you provide a description in text when the channel should appear. It also lets you define a start date (**active from**) and an end date (**active until**) for the channel to be shown. 

**Show Attraction Tooltip**

   Show attraction tooltip defines if the attraction tooltip ("*Touch anywhere to begin*") must be shown or not while the channel is running.

### DayParting {#dayparting}

Schedules, when combined with **DayParting**, lets you set a global schedule with multiple channels running at specific times of the day, and reuse that set up for all your displays at once.

DayParting refers to as splitting up a day into time slots and specifying which content plays at the desired time. AEM Screens lets you schedule channels in terms of DayPparting within a day, week, or month as per the requirement.

The following examples explain Day-parting in channels in three different scenarios:

#### Playing content on a single day divided into multiple time slots {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

This example shows how a Restaurant uses DayParting to showcase its breakfast, lunch, and dinner menu.

Here, you divide each day into three different time slots so that channel content plays as per the specified time of the day:

| **Channel** |**Role** |**Priority** |**Schedule** |
|---|---|---|---|
| Menu_A |Breakfast |  |After 6:00 and before 11:00 |
| Menu_B |Lunch |  |After 11:00 and before 15:00 |
| Menu_C |Dinner |  |After 15:00 and before 20:00 |

#### Playing content on a particular day of the week {#playing-content-on-a-particular-day-of-the-week}

This example shows the dayParting achieved in a casino where live event occurs every weekend from 8:00 P.M. until 10:00 P.M. and specials are available for dinner menu after 10:00 P.M. until 1:00 A.M.

<table>
 <tbody>
  <tr>
   <td><strong>Channel</strong></td>
   <td><strong>Role</strong></td>
   <td><strong>Priority</strong></td>
   <td><strong>Schedule</strong></td>
  </tr>
  <tr>
   <td>LiveConcert</td>
   <td>Weekend</td>
   <td> </td>
   <td>October 21, 2017 - October 22, 2017 <br /> after 20:00 before 22:00</td>
  </tr>
  <tr>
   <td>SpecialsDinner</td>
   <td>Weekend</td>
   <td> </td>
   <td>October 21, 2017 - October 22, 2017 <br /> after 22:00 before 1:00</td>
  </tr>
 </tbody>
</table>

#### Playing content for a particular month/months {#playing-content-for-a-particular-month-months}

This example shows the DayParting for a store that displays their summer collection from the months of June until August and fall collection from September until the end of October.

Here, you create DayParting as per month, so that channel content plays as per the specified months of the year.

| **Channel** |**Role** |**Priority** |**Schedule** |
|---|---|---|---|
| SummerCollection |Summer |  |June 01, 2017 - August 31, 2017 |
| FallCollection |Fall |  |September 01, 2017 - October 30, 2017 |

>[!NOTE]
>
>Also, you can define ***Priority*** for each of the channels. For example, if two channels are set for the same day and time or for the same month, then the channel with higher priority is played first. The minimum value for priority can be set as 0.

#### Playing content for channels with same priority {#playing-content-for-channels-with-same-priority}

This example shows the DayParting for a store that displays their winter collection with the same schedule in the month of December. But since the channel B has the priority set as 2, during that week; channel B plays its content rather than channel A.

| **Channel** |**Role** |**Priority** |**Schedule** |
|---|---|---|---|
| A |Winter |1 |December 01, 2017 - December 31, 2017 |
| B |Christmas |2 |December 24, 2017 - December 31, 2017 |


>[!NOTE]
>
> To learn more about DayParting, see the sections below:
>
>* [Handling Recurrence in Assets](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/asset-level-scheduling)
>* [Handling Recurrence for Assets in a Channel](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/authoring/product-features/channel-level-activation)
