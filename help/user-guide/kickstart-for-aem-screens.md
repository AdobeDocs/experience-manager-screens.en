---
title: Kickstart Guide
description: Learn how to create a demo AEM Screens project. It helps you create a digital signage experience starting from installation and setting up a new project to viewing your content in AEM Screens Player.
feature: Overview, Digital Signage
role: User
level: Beginner
exl-id: 9b7c7f50-2846-4727-a0ec-0220b4cd52c4
---
# Kickstart Guide {#kickstart-guide}

The kickstart to AEM Screens demonstrates how to set up and run an AEM Screens project. It walks you through setting up a basic digital signage experience and adding content such as assets and/or videos to each channel and further publishing the content to an AEM Screens Player.

>[!NOTE]
>Before working on the project details, make sure you have installed the latest Feature Pack for AEM Screens. You can download the latest Feature Pack from the [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) using your Adobe ID.

## Prerequisites {#prerequisites}

Follow the steps below to create a sample project for AEM Screens and further publish content to the Screens player.

>[!NOTE]
>The following tutorial showcases playing the contents of your channel in a Chrome OS player.

>[!IMPORTANT]
>**OSGi Configuration Settings**
>You must enable the empty referrer to allow the device to post data to the server. For example, if the empty referrer property is disabled, the device cannot post a screenshot back. Currently some of these features are only available if the Apache Sling Referrer Filter Allow Empty is enabled in the OSGi Configuration. The dashboard may display a warning that security settings may prevent some of these features from working.
>Follow the steps below to enable the ***Apache Sling Referrer Filter Allow Empty***:


## Allow Empty Referrer Requests {#allow-empty-referrer-requests}

1. Navigate to **Adobe Experience Manager Web Console Configuration** by way of AEM instance > hammer icon > **Operations** > **Web Console**.

   ![image](assets/config/empty-ref1.png)

1. **Adobe Experience Manager Web Console Configuration** opens. Search for sling referrer.

   For searching the sling referrer property, press **Command+F** for **Mac** and **Control+F** for **Windows**.

1. Check the **Allow Empty** option, as shown in the figure below.

    ![image](assets/config/empty-ref2.png)
    
1. Click **Save** to enable the Apache Sling Referrer Filter Allow Empty.

## Creating a Digital Signage Experience in 5 minutes {#creating-a-digital-signage-experience-in-minutes}

### Creating an AEM Screens Project {#creating-project}

The first step is to create an AEM Screens project.

1. Navigate to your Adobe Experience Manager (AEM) instance and click **Screens**. Alternatively, you can navigate directly from `https://localhost:4502/screens.html/content/screens](https://localhost:4502/screens.html/content/screens`.

1. Click **Create Screens Project** so you can create a Screens project.
1. Enter the title as **DemoScreens**, then click **Save**.

   ![image](assets/kickstart/demo-1.png)

   >[!NOTE]
   >After you create the project, it brings you back to the AEM Screens Project home page. You can now click your project. In a project, there are five different folders titled **Applications**, **Channels**, **Devices**, **Locations**, and **Schedules**.

### Creating a Channel {#creating-channel}

After you have created your AEM Screens project, create a channel where you manage the content.

Follow the steps below to create a channel for your project:

1. After you create a project, click the **DemoScreens** project and click the **Channels** folder, as shown in the figure below. Click **+ Create** from the action bar.

   ![image](assets/kickstart/demo-2.png)

1. Choose the **Sequence Channel** from the wizard and click **Next**.
   ![image](assets/kickstart/demo-3.png)

1. Enter the **Title** as **TestChannel** and click **Create**.

   ![image](assets/kickstart/demo-4.png)

   The **TestChannel** is now added to your channels folder, as shown in the figure below.

   ![image](assets/kickstart/demo-5.png)

### Adding Content to a Channel {#adding-content}

When you have your channel in place, add content to your channel that AEM Screens Player can display.

Follow the steps below to add content to the channel (**TestChannel**) in your project:

1. Navigate to the **DemoProject** you created and click the **TestChannel** from the **Channels** folder.

1. Click **Edit** from the action bar (see the figure below). The editor for the **TestChannel** opens.

   ![image](assets/kickstart/demo-6.png)

1. Click the icon that toggles the side panel on the left-hand side of the action bar to open the assets and components.  

1. Drag and drop the components you want to add to your channel.

   ![image](assets/kickstart/demo-7.png)

### Creating a Location {#creating-location}

When you have your channel in place, create a location.

>[!NOTE]
>***Locations*** compartmentalize your various digital signage experiences and contains the configurations of the displays according to where the various screens are.

Follow the steps below to create a location for your project:

1. Navigate to the **DemoProject** you created and click the **Locations** folder.
1. Click **+ Create** from the action bar. 
1. Click **Location** from the wizard and click **Next**.
1. Enter the **Name** for your location (enter the title as **TestLocation**) and click **Create**. 

The **TestLocation** is created and added to your **Locations** folder.


### Creating a Display for Location {#creating-display}

When you have created a location, create a display for your location.

>[!NOTE]
>***Display*** represents the digital experience that run on one or multiple screens.

1. Navigate to the **TestLocation** and click it. 
1. Click **Create** from the action bar.

   ![image](assets/kickstart/demo-disp1.png)

1. Click **Display** from the **Create** wizard and click **Next**.

   ![image](assets/kickstart/demo-disp2.png)

1. Enter the **Title** as **LobbyDisplay** and click **Create**.

   ![image](assets/kickstart/demo-disp3.png)

   A new display titled as **TestDisplay** is now added to your location **TestLocation**, as shown in the figure below.

   ![image](assets/kickstart/demo-disp4.png)

### Assigning a Channel {#assigning-channel}

When the project setup is complete, assign the channel to a display to view the content.

1. Navigate to the required display from **DemoScreens** > **Locations** > **TestLocation** > **LobbyDisplay**.

1. Click **Assign Channel** from the action bar.

   ![image](assets/kickstart/demo-assign1.png)

   Or,

   Click **Dashboard** from the action bar and click **+Assign Channel** from the **ASSIGNED CHANNELS & SCHEDULES** panel.
  
     ![image](assets/kickstart/demo-assign2.png)
      
1. The **Channel Assignment** dialog box opens.

1. From the **Settings** option, choose the channel **by path** and **Supported Events** such as **Initial Load** and **Idle Screen**.

   >[!NOTE]
   >
   >The **Channel Role**, **Priority**, and **Interruption Methods** are all populated by default. See the [Channel Properties](/help/user-guide/channel-assignment-latest-fp.md#channel-properties) section for more information about channel assignment properties.

   ![image](assets/kickstart/demo-assign3.png)

   Also, you can click the **Activation Window** and **Recurrence Schedule**.

   >[!NOTE]
   >The *Recurrence Schedule* lets you set a recurring schedule for your channel. You can set up multiple recurrence schedules for a channel.
   >See [Recurrence Schedule](/help/user-guide/channel-assignment-latest-fp.md#recurrence-schedule) for more details.

1. Click **Save** once you have configured your preferences.

### Registering a Device and Assigning Device to a Display {#registering-device}

Register your device using the AEM dashboard. 

>[!IMPORTANT]
>Chrome OS player can be installed as a Chrome browser plugin in developer mode without requiring an actual Chrome Player device. For installation, follow the steps below:
>
>1. Click [here](https://download.macromedia.com/screens/) to download the latest Chrome Player.
>1. Unzip and save it on disk.
>1. Open the Chrome browser and click **Extensions** from the menu or directly navigate to ***chrome://extensions***.
>1. Switch on the **Developer mode** from the top-right corner.
>1. Click **Load Unpacked** from the top-left corner and load unzipped Chrome Player.
>1. Check **AEM Screens Chrome Player** plugin if it is available in the list of extensions.
>1. Open a new tab and click the **Apps** icon from the top-left corner, or directly navigate to ***chrome://apps***.
>1. Click **AEM Screens** Plugin so you can launch Chrome Player. By default, the player is launched in full screen mode. Press **Esc** to exit full screen mode.

After your Chrome OS player is on, follow the steps below to register a Chrome device.

1. Navigate to the **Devices** folder of your project from your AEM instance.

1. Click the **Device Manager** from the action bar.

   ![image](assets/kickstart/demo-register1.png)   

1. Click the **Device Registration** from the top right.

1. Click the required device and click **Register Device**.

   ![image](assets/kickstart/demo-register2.png)   

1. Wait for the device to send its registration code and simultaneously check the **Registration Code** from your Chrome device.
   ![image](assets/kickstart/demo-register3.png)

1. If the **Registration Code** is the same on both machines, click **Validate** in AEM.

1. Set the desired name as **ChromeDeviceforDemo** for the device, and click **Register**.

   ![image](assets/kickstart/demo-register4.png)

1. Click **Assign Display** from the **Device Registration Successful** dialog box.

   ![image](assets/kickstart/demo-register5.png)

1. Click the path to your display as **DemoScreens** > **Locations** > **TestLocation** > **LobbyDisplay** and click **Assign**.
 
   ![image](assets/kickstart/demo-device6.png)

1. When the device is successfully assigned, you see the following confirmation.

   ![image](assets/kickstart/demo-register8.png)

1. Click **Finish** to complete the registration process. You can now view your registered device from the display dashboard.

   ![image](assets/kickstart/demo-register9.png)

### Viewing the Content in Chrome Player {#viewing-content-output}

All the assets in your channel are now playing on your Chrome OS player.

Congratulations you are now playing content in an AEM Screens channel!

![image](assets/kickstart/demo-video-screens.gif)
