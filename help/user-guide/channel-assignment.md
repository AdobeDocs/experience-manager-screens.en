---
title: Channel Assignment
seo-title: Channel Assignment
description: Follow this page to learn about Channel Assignment and Day-parting.
---

# Channel Assignment {#channel-assignment}

>[!IMPORTANT]
>This section highlights the Channel assignment and scheduling of channels for Feature packs older than AEM 6.5.5 Screens version.

Once you have set up a display, you must assign a channel to a display to view your content.

This page shows assigning a channel to your display.

>[!NOTE]
>You can assign multiple channels to a display.

## Assigning a Channel {#assign-a-channel}

Follow the steps below to assign a channel to a display:

1. Navigate to the required display, for example, **DemoProject** --&gt; **Locations** --&gt; **SanJose** --&gt; **StoreDisplay**.

   ![image](assets/screen_shot_2018-08-23at25359pm.png)

1. Tap/click **Assign Channel** in the action bar

   Or,

   Tap/click **Dashboard** and click **+Assign Channel** from the **ASSIGNED CHANNNELS** panel to open the **Channel Assignment** dialog box.

   ![image](/help/user-guide/assets/channel-assign1.png)

   You can configure the properties from the **Channel Assignment** dialog box from the section below. Refer to [Channel Properties](#channel-properties) section to learn more about channel properties.


## Understanding Channel Properties from Channel Assignment {#channel-properties}

### Reference Channel {#ref-channel}

Reference channel allows you to provide a reference to the desired channel, either by channel name or by channel path.

* **by path**: you provide an explicit reference using the absolute path of the channel.

* **by name**: You enter the name of the channel that will resolve to an actual channel by context. This feature allows you to create local version of a channel, in order to dynamically resolve location-specific content. For example, a channel with name *deals of the day*, where the actual content would be different in two cities, but you still have the sane channel role on all the displays.

### Channel Role {#role-channel}

Channel role defines the context of the display. The role is targeted by various actions and is independent of the actual channel that fulfils the role.

### Priority {#priority-channel}

Priority is used to order the assignments in case multiple ones match the playing criteria. The one with the highest value will always take precedence over lower values. For example, if there are two channels A and B. A has a priority of 1 and B has a priority of 2, then channel B is displayed, as it has a higher priority than A.

   >[!NOTE]
   >The priority for a channel is set as a number (1 for minimum) in the **Channel Assignment** dialog box, as mentioned above. Additionally, the assigned channels are sorted based on descending priority.

### Supported Events {#supported-events-channel}

* **Initial Load**: loads the channel when the player is started. It can be assigned to multiple channels in combination with schedule
* **Idle Screen**: loads when the screen is idle. It can be assigned to multiple channels in combination with schedule
* **Timer**: needs to be set when a schedule is provided
* **User Interaction**: the player will switch to the specified channel, if there is a user interaction on the screen (touch) in an idle channel and will load when the screen is touched

### Interruption Method {#interruption-method-channel}

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

### Schedule {#schedule-channel}

Schedule allows you to provide a description in text when the channel should appear. It also let's you define a start date (**active from**) and an end date (**active until**) for the channel to be shown. 

**Show Attraction Tooltip**:

   Show attraction tooltip defines if the attraction tooltip ("*Touch anywhere to begin*") must be shown or not while the channel is running.

### Day-parting {#dayparting}

Schedules when combined with **Day-parting**, allows you to set a global schedule with multiple channels running at specific times of the day, and re-use that setup for all your displays at once.

DayParting refers to as splitting up a day into time slots and specifying which content plays at the desired time. AEM Screens allows you to schedule channels in terms of day-parting within a day, week, or month as per the requirement.

The following examples explain day-parting in channels in three different scenarios:

#### Playing content on a single day divided into multiple time slots {#playing-content-on-a-single-day-divided-into-multiple-time-slots}

This example shows how a Restaurant uses day-parting to showcase its breakfast, lunch and dinner menu.

Here, we will divide each day into three different time slots, so that channel content plays as per the specified time of the day:

| **Channel** |**Role** |**Priority** |**Schedule** |
|---|---|---|---|
| Menu_A |Breakfast |  |after 6:00 and before 11:00 |
| Menu_B |Lunch |  |after 11:00 and before 15:00 |
| Menu_C |Dinner |  |after 15:00 and before 20:00 |

#### Playing content on a particular day of the week {#playing-content-on-a-particular-day-of-the-week}

This example shows the dayparting achieved in a casino where live event occurs every weekend from 8:00 pm until 10:00 pm and specials are available for dinner menu after 10:00 pm until 1:00 am.

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
   <td>Oct 21, 2017 - Oct 22, 2017 <br /> after 20:00 before 22:00</td>
  </tr>
  <tr>
   <td>SpecialsDinner</td>
   <td>Weekend</td>
   <td> </td>
   <td>Oct 21, 2017 - Oct 22, 2017 <br /> after 22:00 before 1:00</td>
  </tr>
 </tbody>
</table>

#### Playing content for a particular month/months {#playing-content-for-a-particular-month-months}

This example shows the day-parting for a store that displays their summer collection from the months of June until August and fall collection from September until the end of October.

Here, you will create day-parting as per months, so that channel content plays as per the specified months of the year.

| **Channel** |**Role** |**Priority** |**Schedule** |
|---|---|---|---|
| SummerCollection |Summer |  |June 01, 2017 - Aug 31, 2017 |
| FallCollection |Fall |  |Sep 01, 2017 - Oct 30, 2017 |

>[!NOTE]
>
>Additionally, you can define ***Priority*** for each of the channels. For example, if two channels are set for the same day and time or for the same month, then the channel with higher priority is played first. The minimum value for priority can be set as 0.

#### Playing content for channels with same priority {#playing-content-for-channels-with-same-priority}

This examples shows the day-parting for a store that displays their winter collection with the same schedule in the month of December. But since the Channel B has priority set as 2, during that week; channel B plays its content rather than Channel A.

| **Channel** |**Role** |**Priority** |**Schedule** |
|---|---|---|---|
| A |Winter |1 |Dec 01, 2017 - Dec 31, 2017 |
| B |Christmas |2 |Dec 24, 2017 - Dec 31, 2017 |


>[!NOTE]
>
> To learn more about day-parting, refer to the sections below:
>
>* [Handling Recurrence in Assets](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/product-features/asset-level-scheduling.html#handling-recurrence-in-assets)
>* [Handling Recurrence for Assets in a Channel](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/authoring/product-features/channel-level-activation.html#handling-recurrence-in-assets)

