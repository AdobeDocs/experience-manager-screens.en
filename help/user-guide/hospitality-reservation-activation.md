---
title: Hospitality Reservation Activation
description: Learn how this use case demonstrates the use of hospitality reservation activation based on the values populated in Google Sheets.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: ae032042-fa2b-49cd-91fe-ce50f3ce9867
---
# Hospitality Reservation Activation {#hospitality-reservation-activation}

The following use case demonstrates the usage of hospital reservation activation based on the values populated in Google Sheets.

## Description {#description}

For this use case, the Google Sheet is populated with percentage of reservations on two restaurants **`Restaurant1`** and **`Restaurant2`**. A formula is applied based on values of `Restaurant1` and `Restaurant2` and, based on the formula, value 1 or 2 is assigned to the **AdTarget** Column.

If the value of **`Restaurant1`** > **`Restaurant2`**, then **AdTaget** is assigned value **1** otherwise **AdTarget** is assigned value **2**. Value 1 generates a *Steak food* option and Value two results in a display of *Thai food* option on your display screen.

## Preconditions {#preconditions}

Before you start implementing the reservation activation, learn how to set up ***Data Store***, ***Audience Segmentation*** and ***Enable Targeting for Channels*** in an AEM Screens Project.

See [Configuring ContextHub in AEM Screens](configuring-context-hub.md) for detailed information.

## Basic Flow {#basic-flow}

Follow the use case steps below to implement the hospitality reservation activation for your AEM Screens project:

1. **Populating the Google Sheets and adding the formula**.

   For example, apply the formula to the third column **AdTarget**, as shown in the figure below.

   ![screen_shot_2019-04-29at94132am](assets/screen_shot_2019-04-29at94132am.png)

1. **Configuring the segments in Audiences as per the requirements**

    1. Navigate to the segments in your audience (See ***Step 2: Setting up Audience Segmentation*** in **[Configuring ContextHub in AEM Screens](configuring-context-hub.md)** page for more details).
    1. Click the **Sheets A1 1** and click **Edit**.
    1. Click the comparison property and click the **Configuration** icon.
    1. Click **googlesheets/value/1/2** from the drop-down in **Property name**.
    1. Click the **Operator** as **equal** from the drop-down menu.
    1. Enter the **Value** as **1**.
    1. Similarly, click the **Sheets A1 2** and click **Edit**.
    1. Click the comparison property and click the **Configuration** icon.
    1. Click **googlesheets/value/1/2** from the drop-down in **Property name**.
    1. Click the **Operator** as **2**.

1. Navigate and click your channel () and click **Edit** from the action bar. In the following example, **DataDrivenRestaurant**, a sequential channel is used to showcase the functionality.

   >[!NOTE]
   >
   >Your channel should already have a default image and the Audiences should be pre-configured as described in [Configuring ContextHub in AEM Screens](configuring-context-hub.md).

   ![screen_shot_2019-05-08at14652pm](assets/screen_shot_2019-05-08at14652pm.png)

   >[!CAUTION]
   >
   >Your **ContextHub** **Configurations** using the channel **Properties** > **Personalization** tab should have already been set up at this point.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Click **Targeting** from the editor and click **Brand** and the **Activity** from the drop-down menu and click **Start Targeting**.
1. **Checking the Preview**

    1. Click **Preview.** Also, open your Google Sheets and update its value.
    1. Update the value in **`Restaurant1`** and **`Restaurant2`** columns. If **`Restaurant1`** > **`Restaurant2`,** you should be able to view an image of *Steak* food otherwise, *Thai* food image displays on your screen.

   ![result5](assets/result5.gif)
