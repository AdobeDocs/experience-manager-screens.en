---
title: Asset Level Activation
seo-title: Asset Level Activation
description: Follow this page to learn how to activate a specific asset in a channel for a scheduled time frame in the player's local timezone.
seo-description: Follow this page to learn how to activate a specific asset in a channel for a scheduled time frame in the player's local timezone.
---

# Asset Level Activation {#asset-level-scheduling}

This section describes asset level activation for the assets used in Channels.

The following topics are covered in this section:

* Overview
* Activation Window
* Single Event Playback
* Handling Recurrence in Assets
   * Day Parting
   * Week Parting
   * Month Parting
* Multi-asset Activation

>[!CAUTION]
>
>This AEM Screens functionality is only available, if you have installed AEM 6.3 Feature Pack 3 or AEM 6.4 Screens Feature Pack 1.
>
>To get access to this Feature Pack, you must contact Adobe Support and request access. Once you have permissions you can download it from Package Share.

## Overview {#overview}

***Asset Level Activation***, allows you to activate a specific asset in a channel for a scheduled time frame in the player's local timezone. This is available for images, videos, transitions, pages, and embedded channels (dynamic or static).

*For example*, you want a special promotion to be displayed only during happy hour (2PM to 5PM) on Mondays and Wednesdays.

With this feature, not only can you specify start and end date and time but also a recurrence pattern.

## Single Event Playback {#single-event-playback}

Asset Level Activation is done by configuring the **Activation** tab while accessing properties of an asset.

Follow the steps below to perform asset level scheduling:

1. Select any channel and click **Edit** from the action bar to add or edit content in your channel.

   ![screen_shot_2018-04-23at111422am](assets/screen_shot_2018-04-23at111422am.png)

   >[!NOTE]
   >
   >To learn in detail on how to
   >
   >* Create a project, see [Creating a new Project](creating-a-screens-project.md).
   >* Create and add content to a channel, see [Managing Channels](managing-channels.md).

1. Click **Edit** to open the channel editor and select an asset you want to apply the scheduling to.

   ![screen_shot_2018-04-24at90434pm](/help/user-guide/assets/asset-activation/asset-level1.png)

1. Select the asset and click on top left **Configure** icon to open the properties of the image.

   Click the **Activation** tab.

   ![image](/help/user-guide/assets/asset-activation/asset-level2.png)

1. You can specify the date from the date picker using **Active from** and **Active until** fields.

   If you select the **Active from** and **Active until** date and time, the asset will display and loop only between that start date/time and end date/time respectively.

   ![image](/help/user-guide/assets/asset-activation/asset-level3.png)

## Handling Recurrence in Assets {#handling-recurrence-in-assets}

You can schedule assets to recur at certain intervals on daily, weekly, or monthly basis too as per your requirement.

Suppose you want to display an image only on Fridays from 1:00 pm until 10:00 pm. You can use the Activation tab to set the desired recurring interval for your asset.

### Day Parting {#day-parting}

1. Select the asset and click on **Configure** icon to open the properties dialog box.
1. After entering the start date/time and end/date time, you can use an expression or a natural text version to specify your recurrence schedule.

   Enter the expression into the **Schedule** and your asset will display for the particular interval of day and time.
   *For example:*
   Enter the expression **before 8:00 am** in the **Schedules** field and the channel plays before 8:00 am everyday.

### Week Parting {#week-parting}

1. Select the asset and click on **Configure** icon to open the properties dialog box.
1. After entering the start date/time and end/date time, you can use a natural text version to specify your recurrence schedule.

   Enter the expression into the **Schedule** and your asset will display for the particular interval of day and time every week.
   *For example:*
   Enter the expression **On Monday,Wednesday,Friday** in the **Schedules** field and the channel plays every Monday, Wednesday, Friday.

### Month Parting {#month-parting}

1. Select the asset and click on **Configure** icon to open the properties dialog box.
1. After entering the start date/time and end/date time, you can use an expression or a natural text version to specify your recurrence schedule.

   Enter the expression into the **Schedule** and your asset will display for the particular interval of day and time every month.
   *For example:*
   Enter the expression **On Monday,Wednesday,Friday** in the **Schedules** field and the channel plays every Monday, Wednesday, Friday for two months.

   
## Multi-asset Activation {#multi-asset-scheduling}

>[!CAUTION]
>
>The **Multi-asset Activation** feature is only available, if you have installed AEM 6.3 Feature Pack 5 or AEM 6.4 Feature Pack 3.

***Multi-asset Activation*** allows the user to select multiple assets and apply a playback schedule to all selected assets.

### Prerequisites {#prerequisites}

To use multi-asset level activation for your assets, create an AEM Screens project with a sequence channel. For example, the following use case showcases the implementation of the feature:

* Create an AEM Screens project titled as **MultiAssetDemo**
* Create a channel titled as **MultiAssetChannel** and add content to the channel, as shown in the figure below

![screen_shot_2018-12-21at70128am](assets/screen_shot_2018-12-21at70128am.png)

Follow the steps below to select multiple assets and schedule their display in an AEM Screens project:

1. Select **MultiAssetChannel** and click **Edit** from the action bar to open the editor.

   ![screen_shot_2018-12-21at70313am](assets/screen_shot_2018-12-21at70313am.png)

1. Select multiple assets from the editor and click **Edit Activation** (top left icon).

   ![screen_shot_2018-12-21at70550am](assets/screen_shot_2018-12-21at70550am.png)

1. Select the date and time in **Active from** and **Active until** from the **Component Activation** dialog box. Click the check mark icon when you are done selecting the schedules.

   ![screen_shot_2018-12-17at20337pm](assets/screen_shot_2018-12-17at20337pm.png)

1. Click refresh to check the assets to which multi-asset schedule is applied.

   >[!NOTE]
   >
   >The schedule icon is visible on the top right corner to those assets that have muti-asset activation.

   ![screen_shot_2018-12-21at70722am](assets/screen_shot_2018-12-21at70722am.png)

## Example Expressions {#example-expressions}

The following table summarizes few example expressions that you can add to the schedule while assigning channel to a display.

| **Expression** | **Interpretation** |
|---|---|
| before 8:00 am | the channel plays before 8:00 am everyday |
| after 2:00 pm | the channel plays after 2:00 pm everyday |
| after 12:15 and before 12:45 | the channel plays after 12:15 pm everyday for 30 minutes |
| before 12:15 also after 12:45 | the channel plays before 12:15 pm everyday and then also after 12:45 pm |
| on the 1st day of January after 2:00 pm also on the 2nd day of January also on the 3rd day of January before 3:00 am | the channel starts playing after 2:00 pm on January 1st, continues playing for the whole day on January 2nd all the way until 3:00 am on January 3rd |
| on the 1-2 day of January after 2:00 pm also on the 2-3 day of January before 3:00 am | the channel starts player after 2:00 pm on January 1st, continues playing until 3:00 am on January 2nd, then it starts again on January 2nd at 2:00 pm and continues playing until 3:00 am on January 3rd |

>[!NOTE]
>You can also use _military time_ notation (that is, 14:00) instead of *am/pm* notation (that is, 2:00 pm).
