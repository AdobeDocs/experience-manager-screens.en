---
title: Travel Center Temperature Activation
description: Using AEM Screens, learn how this use case demonstrates the usage of travel center local temperature activation based on the values populated in Google Sheets.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: use-case-examples
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 2ec2891f-0fbe-4812-b3c4-ff160ead36b8
---
# Travel Center Temperature Activation {#travel-center-temperature-activation}

The following use case demonstrates the usage of travel center local temperature activation based on the values populated in Google Sheets.

## Description {#description}

For this Use Case, if the value in Google Sheets is less than 50, then an image with hot drinks displays. If the value is greater than or equal to 50, then an image with cold drinks displays. If there is some other value or no value at all, the player displays a default image.

## Preconditions {#preconditions}

Before you start implementing the travel center local temperature activation, learn how to set up ***Data Store***, ***Audience Segmentation*** and ***Enable Targeting for Channels*** in an AEM Screens Project.

See [Configuring ContextHub in AEM Screens](configuring-context-hub.md) for detailed information.

## Basic Flow {#basic-flow}

Follow the steps below to implement the Travel Center Local Temperature Activation use case:

1. **Populating the Google Sheets**

    1. Navigate to the ContextHubDemo Google Sheet.
    1. Add a column with **`Heading1`** with corresponding value for temperature.

   ![screen_shot_2019-05-08at112911am](assets/screen_shot_2019-05-08at112911am.png)

1. **Configuring the segments in Audiences as per the requirements**

    1. Navigate to the segments in your audience (See ***Step 2: Setting up Audience Segmentation*** in **[Configuring ContextHub in AEM Screens](configuring-context-hub.md)** page for more details).

    1. Select the **Sheets A1 1** and select **Edit**.

    1. Select the comparison property and select the configuration icon.
    1. Select **googlesheets/value/1/0** from the drop-down in **Property name**

    1. Select the **Operator** as **greater-than-or-equal** from the drop-down menu

    1. Enter the **Value** as **50**

    1. Similarly, Select the **Sheets A1 2** and select **Edit**.

    1. Select the **Comparison Property - Value** and select the configuration icon.
    1. Select **googlesheets/value/1/0** from the drop-down in **Property name**

    1. Select the **Operator** as **less-than** from the drop-down menu

    1. Enter the **Value** as **50**

1. Navigate and select your channel () and select **Edit** from the action bar. In the following example, **DataDrivenWeather**, a sequential channel is used to showcase the functionality.

   >[!NOTE]
   >
   >Your channel should already have a default image and the Audiences should be pre-configured as described in [Configuring ContextHub in AEM Screens](configuring-context-hub.md).

   ![screen_shot_2019-05-08at113022am](assets/screen_shot_2019-05-08at113022am.png)

   >[!CAUTION]
   >
   >You should have set up your **ContextHub** **Configurations** using the channel **Properties** > **Personalization** tab.

   ![screen_shot_2019-05-08at114106am](assets/screen_shot_2019-05-08at114106am.png)

1. Select **Targeting** from the editor and select **Brand** and the **Activity** from the drop-down menu and select **Start Targeting**.

   ![new_activity3](assets/new_activity3.gif)

1. **Checking the Preview**

    1. Select **Preview.** Also, open your Google Sheet and update its value.
    1. Change the value to less than 50. You should be able to view an image of a cold drink. If the value in Google Sheets is 50 or greater, you should see an image of a hot drink.

    ![result3](assets/result3.gif)
