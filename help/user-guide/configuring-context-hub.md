---
title: Configuring ContextHub in AEM Screens
description: Learn about ContextHub in the targeting engine so you can define a data store for data trigger content change.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 04072107-d6be-4030-bb79-1f1a7609f37e
---
# Configuring ContextHub in AEM Screens {#configuring-contexthub-in-aem-screens}

This section emphasizes on creating and managing data-driven asset changes using a data store.

## Key Terms {#key-terms}

Before you get into the details of creating and managing inventory-driven channels in your AEM Screens project, learn some of the key terms to the different scenarios.

**Brand** &ndash; Your high-level project description.

**Area** &ndash; Your AEM Screens project name such as Digital Ad Signage

**Activity** &ndash; Defines the category rules such as Inventory-Driven, Weather-Driven, or Department Availability-Driven.

**Audience** &ndash; Defines the rule.

**Segment** &ndash; The version of an asset to play for the given rule. For example, if the temperature is below 50 degrees Fahrenheit, then the screen displays an image of a hot drink, otherwise a cold drink.

The following diagram provides a visual representation of how ContextHub configurations coincide with Activity, Audience, and Channels.

![screen_shot_2019-05-29at53729pm](assets/screen_shot_2019-05-29at53729pm.png)

## Preconditions {#preconditions}

Before you start configuring ContextHub configurations for an AEM Screens project, set up Google Sheets (for demonstration purposes).

>[!IMPORTANT]
>
>Google Sheets is used in the following example as a sample database system from where the values are fetched and is solely for educational purposes. Adobe does not endorse using Google Sheets for production environments.
>
>For more information, see [Get API Key](https://developers.google.com/maps/documentation/javascript/get-api-key) in Google documentation.

## Step 1: Setting up a Data Store {#step-setting-up-a-data-store}

You can set up the data store as a Local I/O event or as a local database event. 

The following asset level data triggers example showcases a local database event. The event sets up a data store such as an Excel sheet that lets you use ContextHub configurations and segments path to the AEM Screens channel.

After you have set up the `google` sheet correctly, as shown in the example below: 

![image](/help/user-guide/assets/context-hub/context-hub1.png)

The following validation is what you view when you check your connection by entering the two values, `*google sheet ID*` and `*API key*` in the format below:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![image](/help/user-guide/assets/context-hub/context-hub2.png)

>[!NOTE]
>
>The specific example below showcases the Google Sheets as a data store that triggers an asset change if the value is higher than 100 or less than 50.

## Step 2: Setting up Store Configurations {#step-setting-store-configurations}

1. **Navigating to ContextHub**

   Navigate to your AEM instance and click the tools icon from the left sidebar. Click **Sites** > **ContextHub**, as shown in the figure below.

   ![image](/help/user-guide/assets/context-hub/context-hub3.png)

1. **Creating a ContextHub Store Configuration**

    1. Navigate to the configuration container titled as **screens**.

    1. Click **Create** > **Create Configuration Container** and enter the title as **ContextHubDemo**.

       ![image](/help/user-guide/assets/context-hub/context-hub4.png)

    1. **Navigate** to **ContextHubDemo** > **Create** **ContentHub Configuration** and click **Save**.

        >[!NOTE]
        > After you click **Save**, you are in the **ContextHub Configuration** screen.

    1. From the **ContextHub Configuration** screen, click **Create** > **ContentHub Store Configuration**

      ![image](/help/user-guide/assets/context-hub/context-hub5.png)

      >[!CAUTION]
      >
      >As part of AEM 6.5 Feature Pack 4 or AEM 6.4 Feature Pack 8, customers should update `/conf/screens/settings/cloudsettings` to `sling:Folder`.
      >
      >Follow the steps below:
      >
      >1. Navigate to CRXDE Lite and then to `/conf/screens/settings/cloudsettings`. 
      >1. Check if `cloudsettings jcr:primaryType` is in `sling:Folder`. If the `jcr:primaryType` is not in `sling:folder`, proceed to the next steps.
      >1. Right-click `/conf/screens/settings` and create a node with *name* as **`cloudsettings1`** and *Type* as **`sling:Folder`** and save the changes.
      >1. Move all the nodes under `/conf/screens/settings/cloudsettings` to `cloudsettings1`.
      >1. Delete `cloudsettings` and save.
      >1. Rename `cloudsettings1` to `cloudsettings` and save.
      >1. Observe that `/conf/screens/settings/cloudsettings` has `jcr:primaryType` as `sling:Folder`.
      >
      >Follow these steps in Author and Publish before or after the upgrade.

   1. Enter the **Title** as **Google Sheets**, **Store Name** as **`googlesheets`**, and **Store Type** as **c`ontexthub.generic-jsonp`** and click **Next**.

      >[!CAUTION]
      >If you are using Adobe Experience Manager (AEM) 6.4, enter the **Configuration Title** as **`googlesheets`** and the **Store Type** as **c`ontexthub.generic-jsonp`**.

      ![image](/help/user-guide/assets/context-hub/context-hub6.png)

   1. Enter your specific json configuration. For example, you can use the following json for demo purposes and click **Save**. You see the store configuration titled as **Google Sheets** in ContextHub configuration.

      >[!IMPORTANT]
      >Make sure to replace the code with your `*<Sheet ID>*` and `*<API Key>*`, that you fetched while setting up the Google Sheets.

      ```
       {
        "service": {
        "host": "sheets.googleapis.com",
        "port": 80,
        "path": "/v4/spreadsheets/<your google sheets id>/values/Sheet1",
        "jsonp": false,
        "secure": true,
        "params": {
        "key": "<your Google API key>"
       }
      },
      "pollInterval": 10000
      }
      ```

      >[!NOTE]
      >
      >In the above sample code, **pollInterval** defines the frequency at which the values are refreshed (in milliseconds).
      >
      >Replace the code with your `*<Sheet ID>*` and `*<API Key>*`, that you fetched while setting up the Google Sheets.

      >[!CAUTION]
      >
      >If you create your Google Sheets to store configurations outside of the global folder (for example, in your own project folder), then targeting does not work out-of-the-box.

1. **Setting up Store Segmentation**

   1. Navigate to **ContentHub Store Configuration** and create another store configuration in the AEM Screens configuration container and set the **Title** as **segmentation-contexthub**, **Store Name** as **segmentation** and **Store Type** as **aem.segmentation**. 

      ![image](/help/user-guide/assets/context-hub/context-hub7.png)

   1. Click **Next** and then **Save**.

      >[!NOTE]
      >Skip the process of defining the json and leave it as blank.


## Step 3: Setting Up Segments in Audience {#setting-up-audience}

1. **Creating Segments in Audiences**

    1. Navigate from your AEM instance to **Personalization** > **Audiences** > **screens**.

    1. Click **Create** > **Create ContextHub Segment.** The **New ContextHub Segment** dialog box opens.

    1. Enter the **Title** as `**Higherthan50**` and click **Create**. Similarly, create another segment titled as `**Lowerthan50**`.

       ![image](/help/user-guide/assets/context-hub/context-hub11.png)

    1. Click the segment `**Higherthan50**` and click **Properties** from the action bar.
       ![image](/help/user-guide/assets/context-hub/context-hub12.png)

    1. Click the **Personalization** tab from the **Segment Properties**. Set the **ContextHub Path** to `/conf/screens/settings/cloudsettings/ContextHubDemo/contexthub configurations` and **Segments Path** to `/conf/screens/settings/wcm/segments` and click **Save**, as shown in the figure below.

      ![image](/help/user-guide/assets/context-hub/context-hub13.png)

    1. Similarly, set the **ContextHub Path** and **Segments Path** for `**Lowerthan50**` segment too.

## Step 4: Setting Up Brand and Area {#setting-brand-area}

Follow the steps below to create a brand in your activities and areas under the brand:

1. **Creating a Brand in Activities**

    1. Navigate from your AEM instance to **Personalization** > **Activities**.

    1. Click **Create** > **Create Brand**.

    1. Click **Brand** from the **Create Page** wizard and click **Next**.

    1. Enter the **Title** as **ScreensBrand** and click **Create**. Your brand is now created as shown below.

       ![image](/help/user-guide/assets/context-hub/context-hub8.png)


       >[!CAUTION]
       >
       >Known Issue:
       >To add an area, remove the primary from the URL, such as
       >`http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/screensbrand/master`.

1. **Creating an Area in your Brand**

    Follow the steps below to create an area in the brand:

      1. Click **Create** and then **Create Area**.

         ![image](/help/user-guide/assets/context-hub/context-hub9.png)

      1. Click **Area** from the **Create Page** wizard and click **Next**.

      1. Enter the **Title** as **ScreensValue** and click **Create**. 
       An area is created in your brand.

## Step 5: Creating the Segments in an Activity {#step-setting-up-audience-segmentation}

After you have set up a data store and defined your activity (brand and area), follow the steps below to create segments in your activity.

1. **Creating Segments in Activities**

    1. Navigate from your AEM instance to **Personalization** > **Activities** > **ScreensBrand** >**ScreensValue**.

    1. Click **Create** > **Create Activity.** The **Configure Activity Wizard** opens.

    1. Enter the **Title** as **ValueCheck50** and **Name** as **valuecheck50**. Click the **Targeting engine** as **ContextHub (AEM)** from the drop-down and click **Next**.

       ![image](/help/user-guide/assets/context-hub/context-hub14.png)

    1. Click **Add Experience** from the `**Configure Activity**` wizard.

    1. From the **Audiences**, click the `**Higherthan50**` and click **Add Experience** and enter the **Title** as `**higherthan50**` **Name** as `**higherthan50**`. Click **Ok**.

    1. From the **Audiences**, click the `**Lowerthan50**` and click **Add Experience** and enter the **Title** as `**lowerthan50**` **Name** as `**lowerthan50**`. Click **Ok**.

      ![image](/help/user-guide/assets/context-hub/context-hub15.png)

   1. Click **Next** and then **Save**. `**ValueCheck50**` activity is now created and configured.

      ![image](/help/user-guide/assets/context-hub/context-hub16.png)

## Step 5: Editing the Segments in Audiences{#editing-audience-segmentation}

1. **Editing the Segments**

    1. Navigate from your AEM instance to **Personalization** > **Audiences** > **screens**.

    1. Click the segment `**Higherthan50**`, and click **Edit** from the action bar.

    1. Drag and drop the **Comparison: Property - Value** component to the editor.

    1. Click the wrench icon so you can open the **Comparing a property with value** dialog box.

    1. Click **googlesheets/value/1/0** from the drop-down in **Property name**.

       >[!NOTE]
       > The **googlesheets/value/1/0** refers to row 2 and column as populated in `google` sheets in the figure below:

       ![image](/help/user-guide/assets/context-hub/context-hub17.png)

    1. Click the **Operator** as **greater-than** from the drop-down menu.

    1. Enter the **Value** as **70**.

       >[!NOTE]
       >
       >The AEM validates your data from the Google Sheet by showing your segment as green.

       ![image](/help/user-guide/assets/context-hub/context-hub18.png)

   Similarly, edit the property values to `**Lowerthan50**`.

    1. Drag and drop the **Comparison: Property - Value** component to the editor.

    1. Click the wrench icon.

    1. In the **Comparing a property with value** dialog box, click **googlesheets/value/1/0** from the drop-down in **Property name**.

    1. Click the **Operator** as **less-than** from the drop-down menu.

    1. Enter the **Value** as **50**.


## Enabling Targeting in Channels {#step-enabling-targeting-in-channels}

Follow the steps below to enable targeting in your channels.

1. Navigate to one of the AEM Screens channels. The following steps demonstrate how to enable targeting by using **DataDrivenChannel** created in an AEM Screens channel.

1. Click the channel **TargetChannel** and click **Properties** from the action bar.

   ![image](/help/user-guide/assets/context-hub/context-hub19.png)

1. Click the **Personalization** tab so you can set up the ContextHub configurations.

    1. Set the **ContextHub Path** to `/conf/screens/settings/wcm/segments` and **Segments Path** to `/conf/screens/settings/wcm/segments`.
    1. Set brand to **ScreensBrand** from the dropdown and **Set Area Reference** to **ScreensValue**.

    1. Click **Save & Close**.

       >[!NOTE]
       >
       >Use the ContextHub and the Segments path, where you initially saved your ContextHub configurations and segments.

       ![image](/help/user-guide/assets/context-hub/context-hub20New.png)

   1. Navigate and click the **TargetChannel** channel and click **Edit** from the action bar.

      >[!NOTE]
      >
      >If you have set up everything correctly, you see the **Targeting** option in the drop-down from the editor, as shown in the figure below.

      ![image](/help/user-guide/assets/context-hub/context-hub21.png)

## Learn More: Example Use Cases {#learn-more-example-use-cases}

After you have configured ContextHub for your AEM Screens project, you can follow the different Use Cases to understand how data triggered assets plays a vital role in different industries:

1. **[Retail Inventory Targeted Activation](retail-inventory-activation.md)**
1. **[Travel Center Temperature Activation](local-temperature-activation.md)**
1. **[Hospitality Reservation Activation](hospitality-reservation-activation.md)**
