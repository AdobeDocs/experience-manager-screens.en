---
title: Voice Recognition in AEM Screens
description: The page describes voice recognition feature in AEM Screens.
---

# Voice Recognition in AEM Screens {#voice-recognition}

>[!IMPORTANT]
>
>**Important Privacy Information**
>
>When using the voice recognition feature follow all applicable legal and ethical guidelines for your region (including but not limited to providing a visible notice to end users that the player is using Voice Recognition). Adobe Inc., does not receive, store or process any of the voice related information. The AEM Screens players use the standard web speech API built into the browsing engine. Behind the scenes this API sends a wave form of your speech to Google's servers for conversion from speech to text and this text is matched by the player against configured keywords. 
>
>Refer to [Google Privacy White-paper on web speech API](https://www.google.com/chrome/privacy/whitepaper.html#speech) for more details.


The voice recognition feature allows content change in an AEM Screens channel driven by voice interaction.

A content author can configure a display to be voice enabled. The purpose of this feature is to allow customers to utilize speech as a method of interacting with their displays. Some similar use cases include finding product recommendations in stores, ordering menu items at diners and restaurants. This feature increases accessibility for users and can greatly enhance customer experience. 

>[!NOTE]
>The player hardware must support voice input, such as a microphone.

## Implementing Voice Recognition {#implementing}

>[!IMPORTANT]
> The voice recognition feature is available only on Chrome OS and Windows players.

To implement voice recognition in your AEM Screens project, you must enable the voice recognition for the Display and associate each channel with a unique tag to trigger a channel transition.

The following section describes how you can enable and use the voice recognition feature in an AEM Screens project.

## Viewing Content in Full Screen or Split Screen Channel Switch {#sequence-channel}

Before you use voice recognition feature, make sure you have a project and a channel with content set up for your project.

1. The following example showcases a demo project named **VoiceDemo** and three sequence channels **Main**, **ColdDrinks**, and **HotDrinks**, as shown in the figure below.

   ![image](assets/voice-recognition/vr-1.png)

   >[!NOTE]
   >
   >To learn how to create a channel or add content to a channel, refer to [Creating and Managing Channels](/help/user-guide/managing-channels.md)

   Or,

   You can create three sequence channels **Main**, **ColdDrinks**, and **HotDrinks**, and one additional 1x2 Split Screens channel **SplitScreen** as shown in the figure below.

   ![image](assets/voice-recognition/vr-emb-1.png)

1. Navigate to each of the channel and add content. For example, navigate to **VoiceDemo** --> **Channels** --> **Main** and select the channel. Click **Edit** from the action bar to open the editor and add content (images/videos) as per your requirement. Similarly, add content to both **ColdDrinks** and  the **HotDrinks** channel.

   The channels now contain assets (images), as shown in the figures below.

   **Main**:

   ![image](assets/voice-recognition/vr-4.png)

   **ColdDrinks**:

   ![image](assets/voice-recognition/vr-3.png)
   
   **HotDrinks**:

   ![image](assets/voice-recognition/vr-2.png)

   If you have added Split Screens channel to your project, navigate to **SplitScreen** and drag and drop two embedded sequences and add paths to both the **ColdDrinks** and **HotDrinks** channel as shown in the figure below.
   ![image](assets/voice-recognition/vr-emb-6.png)


### Setting up Tags for Channels {#setting-tags}

Once you have added content to your channels, you need to navigate to each of the channels and add appropriate tags that would trigger the voice recognition.

Follow the steps below to add tags to your channel:

1. Navigate to each of the channel and add content. For example, navigate to **VoiceDemo** --> **Channels** --> **Main** and select the channel.

1. Click **Properties** from the action bar.

   ![image](assets/voice-recognition/vr-5.png)
   
1. Navigate to **Basics** tab and select an already existing tag from the **Tags** field or create a new one.

   You can either create a new tag by typing in a new name for you tag and hit `return` key, as shown in the figure below:

   ![image](assets/voice-recognition/vr-6.png)

   Or,

   You can also create tags from your AEM instance beforehand for your project and select those. Once you follow the steps explained in [Creating Tags](#creating-tags), you can select the tag from the location and add it to your channel, as shown in the figure below:

   ![image](assets/voice-recognition/vr-tag1.png)

1. Similarly, add tag titled as **hot** to the **HotDrinks** channel.

1. If you are using a Split Screens channel, add both the tags (**hot** and **cold**) to the **SplitScreen** channel properties, as shown in the figure below.

   ![image](assets/voice-recognition/vr-emb-7.png)

1. Click **Save & Close** once you are done.


### Creating Tags {#creating-tags}
   
Follow the steps below to create tags:

   1. Navigate to your AEM instance.

   1. Click on tools icon --> **Tagging**.
       ![image](assets/voice-recognition/vr-7.png)

   1. Click **Create** --> **Create Namespace**.
       ![image](assets/voice-recognition/vr-tag3.png)

   1. Enter the name of your project, for example, **VoiceDemo** and click **Create**.

   1. Select the **VoiceDemo** project and click **Create Tag** from the action bar.
       ![image](assets/voice-recognition/vr-tag4.png)

   1. Enter the name of your tag and click **Submit**.
       ![image](assets/voice-recognition/vr-tag5.png)

Now, you can use these tags in your AEM Screens project.

### Assigning Channel to a Display and Enabling Voice Recognition {#channel-assignment}

1. Create a display in the **Locations** folder, as shown in the figure below.

   ![image](assets/voice-recognition/vr-loc.png)

   >[!NOTE]
   >To learn how to assign a channel to a display, refer to [Creating and Managing Displays](/help/user-guide/managing-displays.md).
   
1. Assign the channels **Main**, **ColdDrinks**, and **HotDrinks** to your **LobbyDisplay**. Additionally, if you are using the **SplitScreen** channel for your project, make sure you assign that too to the display.

   >[!NOTE]
   >If you have created a split screen channel, assign the **SplitScreen** channel too to your display.
  
1. Set the following properties to each of the channel, while assigning the channel.

   |**Channel Name**|**Priority**|**Supported Events**|
   |---|---|---|
   |Main|2|Initial Load, Idle Screen, Timer|
   |HotDrinks|1|User Interaction|
   |ColdDrinks|1|User Interaction|
   |SplitScreen|1|User Interaction|

   >[!NOTE]
   >
   >To learn how to assign a channel to a display, refer to [Creating and Managing Displays](/help/user-guide/managing-displays.md).

1. Once you have assigned channels to a display, navigate to the **LobbyDisplay** and select the display. Select **Properties** from the action bar.

1. Navigate to the **Display** tab and enable **Voice enabled** option under **Content**.

   ![image](assets/voice-recognition/vr-disp.png)

   >[!IMPORTANT]
   >It is mandatory to enable the voice recognition feature from the display.

### Viewing the Content in the Chrome Player {#viewing-content}

Once the preceding steps are complete,  you can register your chrome device to view the output.

>[!NOTE]
>Refer to [Device Registration](device-registration.md) to learn how to register a device on an AEM Screens player.

**Desired Output for Sequence Channel**

The **Main** channel is playing its content, but when you use words with keyword **hot** such as *I would like to have a hot drink*, the channel starts playing the contents of the **HotDrinks** channel.

Similarly, if you use word with a keyword **cold** such as *I would like to haves something cold*, the channel starts playing the contents of the **ColdDrinks** channel.

**Desired Output for Split Screens Channel**

The **Main** channel is playing its content, but when you use words with keyword **hot** and **cold** together such as *I would like to see the menu for hot and cold beverages*, the channel starts playing the contents of the **SplitScreen** channel. If you say *back to main menu*, it switches back to the main channel.





