---
title: Asset Level Activation
description: Learn how to activate a specific asset in a channel for a scheduled time frame in the player's local timezone.
feature: Authoring Screens, Asset Level Activation
role: Admin, Developer
level: Intermediate
exl-id: a2f5b2cc-6797-4397-b49c-72175a2d2ef7
---
# Asset Level Activation {#asset-level-scheduling}

This page describes asset level activation for the assets used in Channels.

The following topics are covered in this section:

* Overview
* Activation Window
* Single Event Playback
* Handling Recurrence in Assets
   * DayParting
   * WeekParting
   * MonthParting
   * Combination of Partings
* Multi-asset Activation
* Global Override For Universal Start Time

<!-- REFERS TO ARCHIVED VERSIONS THAT ADOBE NO LONGER SUPPORTS>
>[!CAUTION]
>
>This AEM Screens functionality is only available if you have installed AEM 6.3 Feature Pack 3 or AEM 6.4 Screens Feature Pack 1.
>
>To get access to this Feature Pack, you must contact Adobe Support and request access. When you have permission, you can download it from Package Share. -->

## Overview {#overview}

***Asset Level Activation*** lets you activate a specific asset in a channel for a scheduled time frame in the player's local timezone. This is available for images, videos, transitions, pages, and embedded channels (dynamic or static).

*For example*, you want a special promotion to be displayed only during happy hour (2PM to 5PM) on Mondays and Wednesdays.

With this feature, not only can you specify start and end date and time but also a recurrence pattern.

## Activation Window {#single-event-playback}

Asset Level Activation is done by configuring the **Activation** tab while accessing properties of an asset.

Follow the steps below to perform asset level scheduling:

1. Select any channel, then select **Edit** from the action bar.

   ![screen_shot_2018-04-23at111422am](/help/user-guide/assets/asset-activation/asset-level1.png)

   >[!NOTE]
   >
   >To learn in detail on how to
   >
   >* Create a project, see [Creating a new Project](creating-a-screens-project.md).
   >* Create and add content to a channel, see [Managing Channels](managing-channels.md).

1. Select **Edit** so you can open the channel editor and select an asset you want to apply the scheduling to.

    ![image](/help/user-guide/assets/asset-activation/asset-level2.png)

1. Select the asset, then select top left **Configure** (wrench icon).

   Select the **Activation** tab.

   ![image](/help/user-guide/assets/asset-activation/asset-level3.png)

1. You can specify the date from the date picker using **Active from** and **Active until** fields.

   If you select the **Active from** and **Active until** date and time, the asset displays and loops only between that start date/time and end date/time, respectively.

   ![image](/help/user-guide/assets/asset-activation/asset-level3.png)

## Handling Recurrence in Assets {#handling-recurrence-in-assets}

You can schedule assets to recur at certain intervals on daily, weekly, or monthly basis too as per your requirement.

Suppose you want to display an image only on Fridays from 1:00 P.M. until 10:00 P.M.. You can use the **Activation** tab to set the desired recurring interval for your asset.

### Day Parting {#day-parting}

1. Select the asset and select on **Configure** (wrench icon) to open the properties dialog box.

1. After entering the start date/time and end/date time, you can use an expression or a natural text version to specify your recurrence schedule.
   
   >[!NOTE]
   >You can skip or include the **Active from** and **Active Until** fields and add the expression to the Schedules field, as per your requirement.

1. Enter the expression into the **Schedule** and your asset is displayed for the particular interval of day and time.

#### Example Expressions for Day Parting {#example-one}

The following table summarizes few example expressions that you can add to the schedule while assigning channel to a display.

| **Expression** | **Interpretation** |
|---|---|
| before 8:00 A.M. | the asset in the channel plays before 8:00 A.M. everyday |
| after 2:00 P.M. | the asset in the channel plays after 2:00 P.M. everyday |
| after 12:15 and before 12:45 | the asset in the channel plays after 12:15 P.M. everyday for 30 minutes |
| before 12:15 also after 12:45 | the asset in the channel plays before 12:15 P.M. everyday and then also after 12:45 P.M. |

>[!NOTE]
>
>You can also use _military time_ notation (14:00) instead of *A.M./P.M.* (2:00 P.M.).

### WeekParting {#week-parting}

1. Select the asset, then select **Configure** (wrench icon).

1. After entering the start date/time and end/date time, you can use an expression or a natural text version to specify your recurrence schedule.
   
   >[!NOTE]
   >You can skip or include the **Active from** and **Active Until** fields and add the expression to the Schedules field, as per your requirement.

1. Enter the expression into the **Schedule** and your asset displays for the particular interval of day and time.

#### Example Expressions for WeekParting {#example-two}

The following table summarizes few example expressions that you can add to the schedule while assigning channel to a display.

| **Expression** | **Interpretation** |
|---|---|
| `Mon,Wed,Fri` | the asset plays in the channel from on Mondays, Wednesdays, and Fridays |
| `Mon-Thu` | the asset plays in the channel from on Mondays to Thursdays |

>[!NOTE]
>
>You can also use _full_ notation (`Monday,Wednesday,Friday`) instead of _short-hand_ (`Mon,Wed,Fri`).


### MonthParting {#month-parting}

1. Select the asset, then select **Configure** (wrench icon).

1. After entering the start date/time and end/date time, you can use an expression or a natural text version to specify your recurrence schedule.
   
   >[!NOTE]
   >You can skip or include the **Active from** and **Active Until** fields and add the expression to the Schedules field, as per your requirement.

1. Enter the expression into the **Schedule** and your asset displays for the particular interval of day and time.

#### Example Expressions for MonthParting {#example-three}

The following table summarizes few example expressions that you can add to the schedule while assigning channel to a display.

| **Expression** | **Interpretation** |
|---|---|
| `on February,May,August,November` | the asset plays in the channel in February, May, August, and November |
| `on February-July` | the asset plays in the channel from February to the end of July |

   >[!NOTE]
   >When defining days of the week and months, you can both use the short-hand and full-name notations, such as, Mon/Monday and Jan/January.

### Combination of Partings {#combined-parting}

1. Select the asset, then select **Configure** (wrench icon).

1. After entering the start date/time and end/date time, you can use an expression or a natural text version to specify your recurrence schedule.
   
   >[!NOTE]
   >You can skip or include the **Active from** and **Active Until** fields and add the expression to the Schedules field, as per your requirement.

1. Enter the expression into the **Schedule** and your asset displays for the particular interval of day and time.

#### Example Expressions for Combination of Partings {#example-four}

The following table summarizes few example expressions that you can add to the schedule while assigning channel to a display.

| **Expression** | **Interpretation** |
|---|---|
| `after 6:00 and before 18:00 on Mon,Wed of Jan-Mar` | the asset plays in the channel between 6am and 6pm on Mondays and Wednesdays from January to end of March |
| `on the 1st day of January after 2:00 P.M. also on the 2nd day of January also on the 3rd day of January before 3:00 A.M.` | the asset in the channel starts playing after 2:00 P.M. on January 1, continues playing for the whole day on January 2 all the way until 3:00 A.M. on January 3 |
| `on the 1-2 days of January after 2:00 P.M. also on the 2-3 days of January before 3:00 A.M.` | the asset in the channel starts player after 2:00 P.M. on January 1, continues playing until 3:00 A.M. on January 2, then it starts again on January 2 at 2:00 P.M. and continues playing until 3:00 A.M. on January 3 |

   >[!NOTE]
   >When defining days of the week and months, you can both use the short-hand and full-name notations, such as, Mon/Monday and Jan/January. Also, you can also use _military time_ notation (14:00) instead of *A.M./P.M.*(2:00 P.M.).


## Multi-asset Activation {#multi-asset-scheduling}

<!--
>[!CAUTION]
>
>The **Multi-asset Activation** feature is only available if you have installed AEM 6.3 Feature Pack 5 or AEM 6.4 Feature Pack 3. -->

***Multi-asset Activation*** lets the user select multiple assets and apply a playback schedule to all selected assets.

### Prerequisites {#prerequisites}

To use multi-asset level activation for your assets, create an AEM Screens project with a sequence channel. For example, the following use case showcases the implementation of the feature:

* Create an AEM Screens project titled as **MultiAssetDemo**.
* Create a channel titled as **MultiAssetChannel** and add content to the channel, as shown in the figure below.

![screen_shot_2018-12-21at70128am](assets/screen_shot_2018-12-21at70128am.png)

Follow the steps below to select multiple assets and schedule their display in an AEM Screens project:

1. Select **MultiAssetChannel**, then select **Edit** from the action bar.

   ![screen_shot_2018-12-21at70313am](assets/screen_shot_2018-12-21at70313am.png)

1. Select multiple assets from the editor, then select **Edit Activation** (top-left icon).

   ![screen_shot_2018-12-21at70550am](assets/screen_shot_2018-12-21at70550am.png)

1. Select the date and time in **Active from** and **Active until** from the **Component Activation** dialog box. Select the check mark icon when you are done selecting the schedules.

   ![screen_shot_2018-12-17at20337pm](assets/screen_shot_2018-12-17at20337pm.png)

1. Select refresh to check the assets to which multi-asset schedule is applied.

   >[!NOTE]
   >
   >The schedule icon is visible on the top-right corner to those assets that have muti-asset activation.

   ![screen_shot_2018-12-21at70722am](assets/screen_shot_2018-12-21at70722am.png)

## Global Override For Universal Start Time {#global-override-scheduling}   

***Global Override for Universal Start Time***, is a setting that allows the content author to define the playback of an image or video asset based on a specific time. The time/timezone setting of any individual player is not used.

Normally, playback is determined by the local time of any given player but with the global override, a specific, universal start time can be used to initiate the playback of the asset.

This allows the content author to designate playback of a specific asset as occurring at a specific date/time regardless of the local clock on any players which have the assigned content.

Global Override for Universal Start Time is done by configuring the **Activation** tab while accessing properties of an asset. Follow the steps below to perform a Global Override for asset scheduling:

1. Select any channel, then select **Edit** from the action bar so you can add or edit content in your channel.

   ![screen_shot_2018-04-23at111422am](/help/user-guide/assets/asset-activation/asset-level1.png)

1. Select **Edit**.
1. In the channel editor, select an asset whose schedule you want to apply to it.

   ![screen_shot_2018-12-21at70550am](/help/user-guide/assets/asset-activation/Asset-level4.png)
 
1. For a Global Override, enter activation time in the **Timezone override** section for the asset. If you do not enter anything in this area, the timezone applied is the player's timezone.


