---
title: Content Update using Screens Launch
description: Learn how to create a future version of the channels, known as Launch, and setting a live date for the launch to make content live on devices or players.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
docset: aem65
feature: Authoring Screens, Launches
role: Admin, Developer
level: Intermediate
exl-id: b610e5dd-e0c6-45e6-bf9b-27be2054bc8f
---
# Content Update using Screens Launch {#launches}

Content authors can create a future version of the channels and further set the live date for this launch. This ability allows the content to be live in devices or players on the specified live date.

With the help of ***Screens Launch***, authors can preview each channel in the launch and should be able to initiate a request for review. Approvers group gets notification and can approve or reject the request. When the live date is reached, the content plays in the devices.

For example, if the author wants to create future versions of c1, c2 (channels), a launch is created and a live date is set (for instance, November 10 8:00 A.M.). Any more updates in the content are sent out for review. 

After approval and on the live date (November 10, 8:00 A.M.), this launch plays the content on the devices or players.

## Requirements {#requirements}

Before you start using *Screens Launch* in an AEM Screens project, make sure you understand the concept of grace period and its relevance.

Running an experience on the set live date on the player involves:

* Promotion of the launch (typically takes a few seconds).

* Publishing the resources to publish instances (typically takes a few minutes, depends on the size of the channels or assets that must be published).

* Time taken for the update offline content to complete (typically takes a few minutes).

* Time taken by the players to download the content from the publish instance (typically takes minutes depending on the bandwidth and size of the assets that must be downloaded).

* Anytime differences of the server and the player.

### Understanding Grace Period {#understanding-grace-period}

For the player to be able to start playing the content on the set live date, start the preceding activities before the live date. 

If the live date is *November 24, 9:00 A.M.* and *24 hours* is the grace period, then the above sequence of actions starts at (live date - grace period), that is, November 23, 9:00 A.M. server time. This setting gives 24 hours to complete all the above mentioned actions for the content to reach the players. Players understand that this period is a launch content. As such the content does not play immediately, but players can store this content as a future version and have it start playing exactly at the set live date on the player's time zone.

For example, the server is in PST and the devices are in EST. The maximum time difference is three hours. It assumes that promotion takes 1 minute and publishing from author to publish takes 10 minutes and the player can download the resources typically in 10-15 minutes. Then the grace period = time difference (three hours):

* Plus time to promote the launch (1 minute)
* Plus time to publish the launch (10 minutes)
* Plus time to download at player (10-15 minutes)
* Plus buffer (30 minutes)

Therefore, 3 hours 56 minutes (14160 seconds). 

So, whenever you schedule any launch live, the promotion starts early by taking into account this offset. In the above equation, most of the items do not take much time. You can use a decent guess for this offset when know the maximum time difference between the server and any player.

>[!NOTE]
>
>Out-of-the-box, the grace period for Screens Launch is set to 24 hours. This means that when you set a live date for any launch for the resources under */content/screens*, the promotion starts with this offset.

### Updating out-of-the-box grace period {#updating-out-of-the-box-grace-period}

This section explains how you can update an out-of-the-box grace period to 10 minutes.

1. Navigate to CRXDE Lite and then to `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
1. Right-click and copy the file.
1. Navigate to `/apps/system/config` and right-click and paste.
1. Double-click `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` so you can open the file in the editor in CRXDE Lite. It must show the grace period for the path */content/screens/* as **86400**. Change that value to **600**.

 Now, the content in the text file should look similar to:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

You set the grace period to 10 minutes in the preceding example. Therefore, when you set a live date for any launch for the resources under */content/screens*, the promotion starts with this offset. 

For example, if the live date is set as November 24, 9:00 A.M. and the grace period is 600 seconds, the promotion job starts November 24 at 8:50 A.M.

## Using Screens Launch {#using-launches}

This section demonstrates how to implement Screens Launch in your AEM Screens project.

### Creating a Screens Launch {#creating-a-launch}

Follow the steps below to implement Screens Launch functionality to your AEM Screens project:

1. Create a sequence channel in your AEM Screens project, for example **LaunchesDemo** > **Channels** > **FutureLaunch**, as shown below.

   >[!CAUTION]
   >
   >Create a launch from a pre-existing channel in your AEM Screens project.

   ![Image](/help/user-guide/assets/launches-images/launches-11.png)

1. Click the channel **FutureLaunch** and click **Create Launch** from the action bar.

   ![Image](/help/user-guide/assets/launches-images/launches-12.png)

1. The **Create Launch** wizard opens. Either you can click the channel that is already visible in the wizard or click **+ Add Channels** to add the channel for which you want to create the launch.

1. Click **Next** from the **Create Launch** wizard. The **Include subpages** option is selected by default.

   ![image](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >You can use the **+ Add Channels** option to add another channel for which you want to create the launch.

   To use the **Add Channels** option, navigate to the channel for which you want to create the launch for and click **Select**. 
   
   The **Select** option is disabled if you try to click multiple channels or a folder for adding the launch.
   
   ![image](/help/user-guide/assets/launches-images/launches-14.png)

   After you click the channel/channels, click **Next**.


1. Enter the **Launch Title** as **SummerPromotions** and you do not need to set the **Launch Date**, as shown in the figure below. Click **Create**.

   >[!NOTE]
   >
   >*Enabling or checking* the option **Inherit source page live data** allows the channels to be created as live copies in the launch. If any changes are made in the original channel, those changes are automatically applied to launch channels.
   >
   >
   >*Disabling or unchecking* **Inherit source page live data** allows the channels to be copied without any live relationship in the launch. So, if any changes are made to the original channel, those changes are not applied to launch channels.

   ![Image](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >You can set the live launch date in this step or can set it up later while editing the properties of the launch once it has already been created.
   
   **Understanding Launch Promotion Scope**

   * **Promote full launch** &ndash; All the channels of the launch are promoted at the set live date.
   * **Promote modified pages** &ndash; Only modified launch resources are promoted. Use this option when the launch review is not required. 
   * **Promote approved pages** &ndash; This option requires the launch approval workflow to run on the launch channels. Only approved pages are promoted at the set live date.

      >[!CAUTION]
      >
      >Launch live date respects player/device's timezone rather than servers.

1. Notice that your launch is created. You can either click **Open** to view the pages in the editor or click **Done** to navigate back to your project.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Selecting **Done** let you navigate back to your **FutureLaunch** channel.

   ![Image](/help/user-guide/assets/launches-images/launches-16.png)


### Editing the Launch Properties to Set the Live Date and Scope {#editing-the-launch-properties-to-set-the-live-date-and-scope}

After the launch is created, you can update the properties such as live date, launch title, and promotion scope by using **Launch Properties**.

* **Launch Date** &ndash; The live date, that is, the date or time the content plays in the Screens player as per the player's timezone.
* **Production Ready** &ndash; After promotion, it allows the channels to be published, and out-of-the-box is enabled, so no need to change it.
* **Scope** &ndash; Decides which channels are promoted during the launch promotion.

Follow the steps below to edit the launch properties:

1. Navigate to the channel **FutureLaunch** *(the pending launch)*, and click the channel as shown in the figure below.

   ![image](/help/user-guide/assets/launches-images/launches-17.png)

1. Click **Dashboard** from the action bar and you see the **PENDING LAUNCHES** panel from the channel dashboard.

   ![image](/help/user-guide/assets/launches-images/launches-18.png)

1. Click the launch and click **Launch Properties** from the **PENDING LAUNCHES** panel.

   ![image](/help/user-guide/assets/launches-images/launches-19.png)

### Editing the Screens Launch to Add or Remove Channels {#editing-the-screens-launch-to-add-or-remove-channels}

After you have created the launch, you can add or remove channels to the existing launch using the **Edit Launch** option.

When you are done, click **Save** to navigate back to the **FutureLaunch** channel.

### Promoting the Screens Launch Manually{#promote-the-screens-launch-manually}

You can promote the launch manually using the **`Promote Launch`** option from the **PENDING LAUNCHES** panel.

You can choose the resources you want to promote as part of this manual promotion in the **Launch Promotion Wizard**.

![image](/help/user-guide/assets/launches-images/launches-e.png)

1. You can enable or disable the option to delete the launch after production.
1. You can set the **Scope** of the launch with the following options:
   * **Promote full launch** &ndash; All the channels of the launch are promoted at the set live date.
   * **Promote modified pages** &ndash; Only modified launch resources are promoted. Use this option when the launch review is not required. 
   * **Promote approved pages** &ndash; This option requires the launch approval workflow to run on the launch channels. Only approved pages are promoted at the set live date.
   * **Promote current page** &ndash; This option requires the launch approval workflow to run only for the current page.
1. Click **Next** in the **Promote Launch** wizard.
1. Click **Promote** to promote the launch.

### Deleting the Screens Launch

You can delete the launch using the **Delete Launch** option from the **PENDING LAUNCHES** panel.

>[!CAUTION]
>
>This action also deletes all the descendants (nested launches).
