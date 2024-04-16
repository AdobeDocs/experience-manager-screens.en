---
title: Emergency Channel
description: Learn about creating and managing an emergency channel that the content author can switch from a sequence channel if there is a precondition.
content-type: example
topic-tags: use-case-examples
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: d409ba46-b48a-44db-b305-27c392cd55de
---
# Emergency Channel {#emergency-channel}

## Use Case Description {#use-case-description}

This section describes a use case example that emphasizes on creating and managing an emergency channel that the content author can switch from a sequence channel if there is a precondition.

### Preconditions {#preconditions}

Before you start this use case, make sure you understand how to:

* **[Create and Manage Channels](managing-channels.md)**
* **[Create and Manage Locations](managing-locations.md)**
* **[Create and Manage Schedules](managing-schedules.md)**
* **[Device Registration](device-registration.md)**

### Primary Actors {#primary-actors}

Content Authors

## Basic Flow: Setting up the Project {#basic-flow-setting-up-the-project}

Follow the steps below to set up an emergency channel:

1. Create an AEM Screens Project named as **EmergencyChannel**, as shown below.

   >[!NOTE]
   >To learn more about creating and managing projects in AEM Screens, see Creating a Project.

   ![screen_shot_2019-02-21at35809pm](assets/screen_shot_2019-02-21at35809pm.png)

1. **Creating a Sequence Channel**

    1. Click the **Channels** folder and click **Create**.

    1. Click **Sequence Channel** from the wizard and create the channel titled as **MainAdChannel**.

   ![screen_shot_2019-02-21at35932pm](assets/screen_shot_2019-02-21at35932pm.png)

1. **Adding Content to Sequence Channel**

    1. Click the channel (**MainAdChannel**).
    1. Click **Edit** from the action bar.
    1. Drag-and-drop few assets to your channel.

   ![screen_shot_2019-02-21at40053pm](assets/screen_shot_2019-02-21at40053pm.png)

1. **Creating an Emergency Channel**

    1. Click the **Channels** folder.
    1. Click **Create**.
    1. Click **Sequence Channel** from the wizard and create the channel titled as **EmergencyChannel**.

   >[!NOTE]
   >
   >Normally, your emergency channel is added to your pre-existing production project.

   ![screen_shot_2019-02-21at40151pm](assets/screen_shot_2019-02-21at40151pm.png)

1. **Adding Content to Emergency Channel**

    1. Click the channel (**Emergency Channel)**.
    1. Click **Edit** from the action bar. 
    1. Drag-and-drop the asset that you want to run during an emergency to your channel.

   ![screen_shot_2019-02-21at40516pm](assets/screen_shot_2019-02-21at40516pm.png)

1. **Creating a Location**

    1. Navigate to **Locations** folder.
    1. Click **Create** from the action bar and create a location titled **Store** from the wizard.

   ![screen_shot_2019-02-22at121638pm](assets/screen_shot_2019-02-22at121638pm.png)

1. **Creating Displays in your Location**

   Navigate to your location (**Store**) and click **Create** from the action bar. Following the wizard, create two **Displays** titled as **StoreFront** and **StoreRear**.

   ![screen_shot_2019-02-22at122556pm](assets/screen_shot_2019-02-22at122556pm.png)

1. **Creating a Schedule**

    1. Navigate to your **Schedules** folder.
    1. Click **Create** from the action bar. 
    1. Following the wizard, create a schedule titled as **StoreSchedule**.

   ![screen_shot_2019-02-22at122845pm](assets/screen_shot_2019-02-22at122845pm.png)

1. Assign both the Displays to your Schedule and set Priorities

    1. Click the schedule **(StoreSchedule)** and click **Dashboard** from the action bar.

    1. Click **+ Assign Channel** from the **ASSIGNED CHANNELS** panel.

    1. From the **Channel Assignment** dialog box:

        1. Click the path to the **MainAdChannel**
        1. Set the **Priority** as 2
        1. Set the Supported Events as **Initial Load** and **Idle Screen**.
        1. Click **Save**

       Similarly, follow the same steps again to assign the **EmergencyChannel** and set its **Priority**.

   >[!NOTE]
   >
   >Priority is used to order the assignments in case multiple ones match the playing criteria. The one with the highest value always takes precedence over lower values.

   ![screen_shot_2019-03-04at104636am](assets/screen_shot_2019-03-04at104636am.png)

1. Click **+ Assign Channel** from the **ASSIGNED CHANNELS** panel.

1. From the **Channel Assignment** dialog box:

    1. Click the path to the **EmergencyChannel**
    1. Set the **Priority** as 1

    1. Set the Supported Events as **Initial Load**, **Idle Screen**, and **User Interaction**

    1. Click **Save**

   ![screen_shot_2019-03-04at104741am](assets/screen_shot_2019-03-04at104741am.png)

   You can view the assigned channels from the **StoreSchedule** dashboard.

   ![screen_shot_2019-02-25at93658pm](assets/screen_shot_2019-02-25at93658pm.png)

1. **Assigning Schedule to each Display**

    1. Navigate to each display, such as **EmergencyChannel** > **Locations** > **Store** >**StoreFront**.

    1. Click **Dashboard** from the action bar.
    1. Click **...** from the **ASSIGNED CHANNELS & SCHEDULES** panel and further click **+Assign Schedule**.

    1. Click the path to the Schedule (for example, here, **EmergencyChannel** > **Schedules** >**StoreSchedule**).

    1. Click **Save**.

   You can view the assigned schedule to the display from the **StoreSchedule** dashboard.
   ![screen_shot_2019-03-04at122003pm](assets/screen_shot_2019-03-04at122003pm.png)

1. **Device Registration**

   Complete the device registration process. When you have registered, you can view the following output on your AEM Screens player.

   ![new30](assets/new30.gif)

## Switching to Emergency Channel {#switching-to-emergency-channel}

If there is an emergency, perform the following steps:

1. Navigate to **EmergencyChannel** > **Schedules** > **StoreSchedule** and click **Dashboard** from the action bar.

   ![screen_shot_2019-02-25at101112pm](assets/screen_shot_2019-02-25at101112pm.png)

1. Click the **EmergencyChannel** from the **StoreSchedule** dashboard and click **Edit Assignment**.

   ![screen_shot_2019-02-25at101239pm](assets/screen_shot_2019-02-25at101239pm.png)

1. Update the **Priority** of the **EmergencyChannel** to **3** from the **Channel Assignment** dialog box and click **Save**.

   ![screen_shot_2019-02-25at101622pm](assets/screen_shot_2019-02-25at101622pm.png)

1. When the priority of the channel is updated, all the AEM Screens player displays the **EmergencyChannel** content.

   ![screen_shot_2019-02-25at101742pm](assets/screen_shot_2019-02-25at101742pm.png)

### Conclusion {#conclusion}

The **EmergencyChannel** continues to display its content until the content author resets the Priority Value to 1.

When the content author receives the instructions that the emergency has been cleared, they should update the priority of the **MainAdChannel** which causes normal playback to resume.
