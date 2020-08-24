---
title: Channel Assignment - Latest FP
seo-title: Channel Assignment - Latest FP
description: Follow this page to learn about Channel Assignment and Day-parting.
---

# Channel Assignment {#channel-assignment}

>[!IMPORTANT]
>This section highlights the Channel assignment and scheduling of channels for AEM 6.5.5 Screens Feature Pack and later.

Once you have set up a display, you must assign a channel to a display to view your content.

This page shows assigning a channel to your display.

>[!NOTE]
>You can assign multiple channels to a display.

## Assigning a Channel {#assign-a-channel-new-release}

Follow the steps below to assign a channel to a display:

1. Navigate to the required display, for example, **DemoProject** --&gt; **Locations** --&gt; **SanJose** --&gt; **StoreDisplay**.


1. Tap/click **Assign Channel** from the action bar

   Or,

   Tap/click **Dashboard** and click **+Assign Channel** from the **ASSIGNED CHANNNELS & SCHEDULES** panel to open the **Channel Assignment** dialog box.

1. From the Setting option, you can choose the channel by path or by name, enter the channel role, priority, Supported Events.

   >[!NOTE]
   >Refer to [Channel Properties](#channel-properties) section to learn more about channel properties.

1. From the **Schedules** option select the **Reference Timezone**, **Activation Window** and **Recurrence Schedule**.

1. Click **Save** once you have configured your preferences.

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