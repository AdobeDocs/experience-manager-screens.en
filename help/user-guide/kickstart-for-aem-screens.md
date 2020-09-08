---
title: Kickstart Guide
seo-title: Kickstart Guide
description: Follow this page to create a demo AEM Screens project. It helps you create a digital signage experience starting from installation and setting up a new project to viewing your content in AEM Screens player.
---

# Kickstart Guide {#kickstart-guide}

This section is a kickstart to AEM Screens and demonstrates how to set up and run an AEM Screens project. It walks you through setting up a basic digital signage experience and adding content such as assets and/or videos to each channel and further publishing the content to an AEM Screens player.

>[!NOTE]
>Before you start working on the project details, make sure you have installed the latest Feature Pack. You can download the latest feature pack for AEM Screens 6.5.5 Release from the [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) using your Adobe ID.

## Creating a Digital Signage Experience in 5 minutes {#creating-a-digital-signage-experience-in-minutes}

Follow the steps below to create a sample project for AEM Screens and further publish content to Screens player.

>[!NOTE]
>The following tutorial showcases playing the contents of your channel in Chrome OS player.

>[!IMPORTANT]
>**OSGi Configuration Settings**
>You need to enable the empty referrer to allow the device to post data to the server. For example, if the empty referrer property is disabled, the device cannot post a screenshot back. Currently some of these features are only available if the Apache Sling Referrer Filter Allow Empty is enabled in the OSGi Configuration. The dashboard may display a warning that security settings may prevent some of these features from working.
>Follow the steps below to enable the ***Apache Sling Referrer Filter Allow Empty***:


## Allow Empty Referrer Requests {#allow-empty-referrer-requests}

1. Navigate to **Adobe Experience Manager Web Console Configuration** via AEM instance --&gt; hammer icon --&gt; **Operations** --&gt; **Web Console**.

   ![image](assets/config/empty-ref1.png)

1. **Adobe Experience Manager Web Console Configuration** opens. Search for sling referrer.

   For searching the sling referrer property, press **Command+F** for **Mac** and **Control+F** for **Windows**.

1. Check the **Allow Empty** option, as shown in the figure below.

    ![image](assets/config/empty-ref2.png)
    
1. Click **Save** to enable the Apache Sling Referrer Filter Allow Empty.


## Tutorial {#tutorial}

### Creating a new AEM Screens Project {#creating-project}

The first step is creating a new AEM Screens project.

1. Navigate to your Adobe Experience Manager (AEM) instance and click **Screens**. Alternatively, you can navigate directly from `https://localhost:4502/screens.html/content/screens](https://localhost:4502/screens.html/content/screens`.

1. Click **Create Screens Project** to create a new Screens project. Enter the title as **DemoScreens** and click **Save**.

   ![image](assets/kickstart/demo-1.png)

   >[!NOTE]
   >Once you create the project, it brings you back to the Screens Project home page. You can now select your project. In a project, there are five different folders titled **Applications**, **Channels**, **Devices**, **Locations**, and **Schedules**.


### Creating a new Channel {#creating-channel}

Once you have your project in place, you need to create a new channel where you manage the content.

Follow the steps below to create a new channel for your project:

1. Once you create a project, select the **DemoScreens** project and select the **Channels folder**, as shown in the figure below. Click **+ Create** from the action bar.

   ![image](assets/kickstart/demo-2.png)

1. Choose the **Sequence Channel** from the wizard and click **Next**.
   ![image](assets/kickstart/demo-3.png)

1. Enter the **Title** as *TestChannel* and click **Create**.

   ![image](assets/kickstart/demo-4.png)

The *TestChannel* is created and added to your channels folder, as shown in the figure below.

   ![image](assets/kickstart/demo-5.png)

### Adding Content to a Channel {#adding-content}

Once you have your channel in place, you need to add content to your channel that the Screens player will display.

Follow the steps below to add content to the channel (*TestChannel*) in your project:

1. Navigate to the *Test_Project* you created and select the **Channels** folder.

1. Click **Edit** from the action bar (see the figure below). The editor for the *TestChannel* opens.

1. Click the icon that toggles side panel on left hand side of the action bar to open the assets and components.

1. Drag and drop the components you want to add to your channel.

   ![chlimage_1-8](assets/chlimage_1-8.png)

In this example, the editor shows an image added to the channel.

   ![chlimage_1-9](assets/chlimage_1-9.png)

### Creating a new location {#creating-location}

Once you have your channel in place, you need to create your location.

***Locations*** compartmentalize your various digital signage experiences and contains the configurations of the displays according to where the various screens are.

Follow the steps below to create a new location for your project:

1. Navigate to the *Test_Project* you created and select the **Locations** folder.

1. Click **Create** next to the plus icon in the action bar (see the figure below). A wizard will open.
1. Select **Location** from the wizard and click **Next**.

1. Enter the **Name** and **Title** for your location (enter the title as *TestLocation*) and click **Create**.

   ![chlimage_1-10](assets/chlimage_1-10.png)

The *TestLocation* is created and added to your **Locations** folder.

   ![chlimage_1-11](assets/chlimage_1-11.png)

### Creating a new display for TestLocation {#creating-display}

Once you have created a location, you need to create a new display for your location.

***Displays*** represent the digital experience that run on one or multiple screens.

1. Navigate to the location where you want to create your display (*Test_Projec*t --&gt; **Locations** --&gt; *TestLocation)* as shown in the figure above and selct *TestLocation*.

1. Click **Create** from the action bar.
1. Select **Display** from the **Create** wizard and click **Next**.

1. Enter **Name** and **Title** for your display location (enter the title as *TestDisplay*).

1. Under the **Display** tab, choose the details of the Layout.

   1. Choose the **Resolution** as **Full HD**.

   1. Choose the **Number of Devices Horizontally** as 1.

   1. Choose the **Number of Devices Vertically** as 1.

   1. Click **Create**.

A new display (*TestDisplay*) is added to your location *TestLocation)*, as shown in the figure below.

   ![chlimage_1-12](assets/chlimage_1-12.png)

### Assigning a channel {#assigning-channel}

1. Navigate to the display from *Test_Project* --&gt; **Locations** --&gt; *TestLocation* --&gt; *TestDisplay*.

1. Select *TestDisplay* and tap/click **Assign Channel **from the action bar, *Or*,

1. Click **Dashboard** and select **+Assign Channel** at the top right from **ASSIGNED CHANNELS & SCHEDULES** panel, as shown in the figure below. **Channel Assignment** dialog box opens.

1. Select **Reference Channel** by **path**

1. Enter the **Channel Role** as *LiveStream*.

1. Select the **Channel Path** (*Test_Project* --&gt; *Channels* --&gt; *TestChannel* ) in the **Channel**.

1. Select the **Priority** for this channel as *1*.

1. Choose the **Supported Events** as **Initial Load** and **Idle Screen**.

1. Enter **Schedule** and select the dates in **active from** and **active until**.

1. Click **Save**.

The channel is created and added to the panel.

   ![chlimage_1-15](assets/chlimage_1-15.png)

### Registering a device {#registering-device}

You need to register your device using the AEM dashboard.

>[!NOTE]
>You can open the Screens player using the AEM Screens app you downloaded or using the web browser.

   

### Viewing the content in AEM Screens Player {#viewing-the-content-in-screens-player}

Once you have added the above configurations, the player should automatically show the default channel for the display on your device.

![chlimage_1-23](assets/chlimage_1-23.png)

See [AEM Screens Player](working-with-screens-player.md) to get more detailed information on AEM Screens player.
