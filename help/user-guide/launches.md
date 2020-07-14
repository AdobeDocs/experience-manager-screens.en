---
title: Content Update using Screens Launch
seo-title: Content Update using Screens Launch
description: Content authors can create future version of the channel(s), known as Launch and further setting live date for this launch allows content to be live in devices or players.
seo-description: Content authors can create future version of the channel(s), known as Launch and further setting live date for this launch allows content to be live in devices or players.
uuid: fb13117c-b99b-48bd-adb6-040dbd13af16
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: 9cd8892b-fe5d-4ad3-9b10-10ff068adba6
docset: aem65
---

# Content Update using Screens Launch {#launches}

Content authors can create future version of the channel(s), known as **Screens Launch** and further set the live date for this launch. This allows allows the content to be live in devices or players on the specified live date.

With the help of ***Screens Launch***, authors can preview each channel in the launch and should be able to initiate a request for review. Approvers group will get notification and can approve or reject the request. When the live date is reached, the content plays in the devices.

For example, if the author wants to create future versions of c1, c2 (channels), a launch is created and a live date is set (for instance, Nov 10th 8:00 AM). Any further updates in the content is sent out for review. 

Once approved and on live date (Nov 10th, 8:00 AM), this launch plays the content on the devices or players.

## Requirements {#requirements}

Before you start leveraging *Screens Launch* in an AEM Screens project, make sure you understand the concept of Grace Period and its relevance.

Running an experience on the set live date on the player involves:

* promotion of the launch (typically takes a few seconds)

* publishing the resources to publish instances (typically takes a few minutes, depends on the size of the channels or assets that needs to be published)

* time taken by the update offline content to complete (typically takes a few minutes)

* time taken by the players to download the content from the publish instance (typically takes minutes depending on the bandwidth and size of the assets that needs to be downloaded)

* any time differences of the server and the player

### Understanding Grace Period {#understanding-grace-period}

In order for the player to be able to start playing the content on the set live date, we need to start the preceding activities before the live date. 

If the live date is *Nov 24th, 9:00 AM* and grace period is *24 hours*, then the above sequence of actions will start at (live date - grace period), that is, Nov 23rd, 9:00 AM server time. This gives 24 hours time to complete all the above mentioned actions and the content will reach the players. Players will understand that this is a launch content, so the content will not play immediately, but players will store this content as a future version and will start playing exactly at the set live date on the player's time zone.

For example let's say, server is in PST and the devices are in EST, max time difference is 3 hours in this case and assume that promotion will take 1 min and publishing from author to publish takes 10 min and player can download the resources typically in 10-15 min. Then grace period = time difference (3 hours) + time to promote the launch (1 min) + time to publish the launch (10 min) + time to download at player (10-15 min) + buffer (to be safe, say 30 min) = 3 hours 56 min = 14160 seconds. 

So, whenever we schedule any launch live, the promotion will start early by this offset. In the above equation, most of the items does not take much time, we can use a decent guess for this offset once we know the maximum time difference between the server and any player.

>[!NOTE]
>
>Out-of-the-box, the grace period for Screens Launch is set to 24 hours which means that when we set live date for any launch for the resources under */content/screens*, the promotion will start with this offset.

### Updating out-of-the-box Grace Period {#updating-out-of-the-box-grace-period}

This section explains how you can update an out-of-the-box Grace Period to 10 minutes.

1.  Navigate to CRXDE Lite and then to `/libs/system/config.author/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config`.
 2. Right click and copy the file.
 3. Navigate to `/apps/system/config` and right-click and paste.
 4. Double click on `/apps/system/config/com.adobe.cq.wcm.launches.impl.LaunchesEventHandler.config` to open the file in the editor in CRXDE Lite. It must show the grace period for the path */content/screens/* as **86400**. Change that value to **600**.

 Now the content in the text file should look similar to:

```java
launches.eventhandler.launch.promotion.graceperiod=[ \
   "/content/screens(/.*):600", \
   ]
```

Since you have set the Grace Period to 10 minutes in the preceding example, when you set live date for any launch for the resources under */content/screens*, the promotion will start with this offset. 

For example, if the live date is set as Nov 24th, 9:00 AM and grace period is 600 seconds, the promotion job will start on Nov 24th at 8:50 AM.

## Using Screens Launch {#using-launches}

This section demonstrates how to implement Screens Launch in your AEM Screens project.

### Creating a Screens Launch {#creating-a-launch}

Follow the steps below to implement Screens Launch functionality to your AEM Screens project:

1. Create a sequence channel in your AEM Screens project, for example **LaunchesDemo** --&gt; **Channels** --&gt; **FutureLaunch**, as shown below.

   >[!CAUTION]
   >
   >You must create a launch from a pre-existing channel in your AEM Screens project.

   ![Image](/help/user-guide/assets/launches-images/launches-11.png)

1. Select the channel **FutureLaunch** and click **Create Launch** from the action bar.

   ![Image](/help/user-guide/assets/launches-images/launches-12.png)

1. The **Create Launch** wizard opens. Either you can select the channel that is already visible in the wizard or click **+ Add Channels** to add the channel for which you want to create the launch.

1. Click **Next** from the **Create Launch** wizard. The **Include subpages** option is selected by default.

   ![image](/help/user-guide/assets/launches-images/launches-d.png)

   >[!NOTE]
   >You can use **+ Add Channels** option to add another channel for which you want to create the launch for.

   To use **Add Channels** option, navigate to the channel for which you want to create the launch for and click **Select**. 
   
   The **Select** option will be disabled if you try to select multiple channels or a folder for adding the launch.
   
   ![image](/help/user-guide/assets/launches-images/launches-14.png)

   Once you have selected the channel/channels, click **Next**.


1. Enter the **Launch Title** as **SummerPromotions** and you do not need to set the **Launch Date**, as shown in the figure below. Click **Create**.

   >[!NOTE]
   >
   >*Enabling or checking* the option **Inherit source page live data** allows the channels to be created as live copies in the launch. If any changes are made in the original channel, those changes are automatically applied to launch channels.
   >
   >
   >*Disabling or unchecking* **Inherit source page live data** allows the channels to be be copied without any live relationship in the launch. So, if any changes are made to the original channel, those changes are not applied to launch channels.

   ![Image](/help/user-guide/assets/launches-images/launches-c.png)

   >[!NOTE]
   >
   >You can set the live launch date in this step or can set it up later while editing the properties of the launch once it has already been created.
   
   **Understanding Launch Promotion Scope**

   * **Promote full launch**: All the channels of the launch are promoted at the set live date.
   * **Promote modified pages**: Only modified launch resources will be promoted. It is recommended to use this option when the launch review is not required. 
   * **Promote approved pages**: This option requires the launch approval workflow to run on the launch channels. Only approved pages will be promoted at the set live date.

      >[!CAUTION]
      >
      >Launch live date respects player/device's timezone rather than server's.

1. You will see that your launch is created. You can either click **Open** to view the pages in the editor or click **Done** to navigate back to your project.

   ![screen_shot_2019-06-25at20355pm](assets/screen_shot_2019-06-25at20355pm.png)

   Clicking **Done** allows you to navigate back to your **FutureLaunch** channel.

   ![Image](/help/user-guide/assets/launches-images/launches-16.png)


### Editing the Launch Properties to Set the Live Date and Scope {#editing-the-launch-properties-to-set-the-live-date-and-scope}

After the launch is created, you can update the properties such as live date, launch title and promotion scope by using **Launch Properties**.

* **Launch Date**, refers to the live date, that is, the date or time the content will play in the Screens player as per the player's timezone.
* **Production Ready**, allows the channels to be published after promoting these, out-of-the-box this is enabled, so no need to change this.
* **Scope**, decides which channels will be promoted during the launch promotion.


Follow the steps below to edit the launch properties:

1. Navigate to the channel **FutureLaunch**, *(that is the pending launch)* and select the channel, as shown in the figure below.

   ![image](/help/user-guide/assets/launches-images/launches-17.png)

1. Click on **Dashboard** from the action bar and you see the **PENDING LAUNCHES** panel from the channel dashboard.

   ![image](/help/user-guide/assets/launches-images/launches-18.png)

1. Select the launch and click **Launch Properties** from the **PENDING LAUNCHES** panel.

   ![image](/help/user-guide/assets/launches-images/launches-19.png)

### Editing the Screens Launch to Add or Remove Channels  {#editing-the-screens-launch-to-add-or-remove-channels}

After you have created the launch, you can add or remove channels to the existing launch using **Edit Launch** option.

Once you are done, click **Save** to navigate back to **FutureLaunch** channel.

### Promoting the Screens Launch Manually{#promote-the-screens-launch-manually}

You can promote the launch manually using the **Promote Launch** option from the **PENDING LAUNCHES** panel.

You can choose the resources you want to promote as part of this manual promotion in the **Launch Promotion Wizard**.

![image](/help/user-guide/assets/launches-images/launches-e.png)

1. You can enable or disable the option to delete the launch after production.
1. You can set the **Scope** of the launch, with the following options:
   1. **Promote full launch**: All the channels of the launch are promoted at the set live date.
   1. **Promote modified pages**: Only modified launch resources will be promoted. It is recommended to use this option when the launch review is not required. 
   1. **Promote approved pages**: This option requires the launch approval workflow to run on the launch channels. Only approved pages will be promoted at the set live date.
   1. **Promote current page**: This option requires the launch approval workflow to run only for the the current page.
1. Click **Next** in the **Promote Launch** wizard.
1. Click **Promote** to promote the launch.

### Deleting the Screens Launch {#deleting-the-screens-launch}

You can delete the launch using **Delete Launch** option from the **PENDING LAUNCHES** panel.

>[CAUTION]
>This action will delete all the descendants (nested launches) also.

