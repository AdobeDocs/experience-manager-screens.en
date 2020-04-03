---
title: Configuring ContextHub in AEM Screens
seo-title: Configuring ContextHub in AEM Screens
description: Follow this page to learn about ContextHub in the targeting engine to define data store for the purpose of data trigger content change.
seo-description: Follow this page to learn about ContextHub in the targeting engine to define data store for the purpose of data trigger content change.
uuid: be06bda8-7de9-40d6-a84b-5ed8d8b3d180
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
content-type: reference
discoiquuid: 9a26b5cd-b957-4df7-9b5b-f57e32b4196a
docset: aem65

---

# Configuring ContextHub in AEM Screens {#configuring-contexthub-in-aem-screens}

This section emphasizes on creating and managing data driven asset changes using a a data store.

## Key Terms {#key-terms}

Before we get into the details of creating and managing inventory driven channels in your AEM Screens project, you must learn few of the key terms that are important and relevant to the different scenarios.

**Brand** Refers to your high level project description.

**Area** Refers to your AEM Screens project name such as Digital Ad Signage

**Activity** Defines the rule category such as Inventory-Driven, Weather-Driven, Department Availability-Driven, and so on.

**Audience** Defines the rule.

**Segment** Refers to the version of the asset to play for the given rule such as if the temperature is below 50 degrees fahrenheit, then the screen displays an image of a hot coffee otherwise a cold drink.

The following diagram provides a visual representation of how ContextHub Configurations coincide with Activity, Audience, and Channels.

![screen_shot_2019-05-29at53729pm](assets/screen_shot_2019-05-29at53729pm.png)

## Preconditions {#preconditions}

Before you start configuring Context Hub Configurations for an AEM Screens project, you must set up Google Sheets (for demonstration purposes).

>[!IMPORTANT]
>
>Google Sheets is used in the following example as a sample database system from where the values are fetched and is solely for educational purposes. Adobe does not endorse using Google Sheets for production environments.
>
>For more information, refer to [Get API Key](https://developers.google.com/maps/documentation/javascript/get-api-key) in Google documentation.

## Step 1: Setting up a Data Store {#step-setting-up-a-data-store}

You can set up the data store as a Local I/O event or as a local database event. 

The following asset level data triggers example showcases a local database event that sets up a data store such as an excel sheet that allows you to use ContextHub configurations and segments path to AEM Screens channel.

Once you have set up the google sheet correctly for example as shown below: 

![image](/help/user-guide/assets/context-hub/context-hub1.png)

The following validation is what you will view when you check your connection by entering the two values, *google sheet ID* and *API key* in the format below:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![image](/help/user-guide/assets/context-hub/context-hub2.png)

>[!NOTE]
> The specific example below showcases the the google sheets as a data store that will trigger asset change if the value is higher than 100 or less than 50.

## Step 2: Setting up Store Configurations {#step-setting-store-configurations}

1. **Navigating to ContextHub**

   Navigate to your AEM instance and click the tools icon from left sidebar. Click **Sites** --&gt; **ContextHub**, as shown in the figure below.

   ![image](/help/user-guide/assets/context-hub/context-hub3.png)

1. **Creating a new ContextHub Store Configuration**

    1. Navigate to the configuration container titled as **screens**.

    1. Click **Create** &gt; **Create Configuration Container** and enter the title as **ContextHubDemo**.

       ![image](/help/user-guide/assets/context-hub/context-hub4.png)

    1. **Navigate** to **ContextHubDemo** &gt; **Create** **ContentHub Configuration** and click **Save**.

        >[!NOTE]
        > After you click **Save** you will be in the **ContextHub Configuration** screen.

   1. From the **ContextHub Configuration** screen, click **Create** &gt; **ContentHub Store Configuration..**

      ![image](/help/user-guide/assets/context-hub/context-hub5.png)
   
   1. Enter the **Title** as **Google Sheets**, **Store Name** as **googlesheets**, and **Store Type** as **contexthub.generic-jsonp** and click **Next**.
      ![image](/help/user-guide/assets/context-hub/context-hub6.png)

   1. Enter your specific json configuration. For example, you can use the following json for demo purposes and click **Save** and you will see the store configuration titled as **Google Sheets** in ContextHub configuration.

      >[!IMPORTANT]
      >Make sure to replace the code with your *&lt;Sheet ID&gt;* and *&lt;API Key&gt;*, that you fetched while setting up the Google Sheets.

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
      >In the above sample code, **pollInterval** defines the frequency at which the values are refreshed (in ms).
      >Replace the code with your *&lt;Sheet ID&gt;* and *&lt;API Key&gt;*, that you fetched while setting up the Google Sheets.

      >[!CAUTION]
      >
      >If you create your Google Sheets store configurations outside of the global folder (for instance in your own project folder), then targeting will not work out of the box.

1. **Setting up Store Segmentation**

   1. Navigate to **ContentHub Store Configuration..** and create another store configuration in the screens configuration container and set the **Title** as **segmentation-contexthub**, **Store Name** as **segmentation** and **Store Type** as **aem.segmentation**. 

      ![image](/help/user-guide/assets/context-hub/context-hub7.png)

   1. Click **Next** and then **Save**.

      >[!NOTE]
      >You have to skip the process of defining the json and leave it as blank.


## Step 3: Setting Up Audience {#setting-up-audience}

Pending: to add properties

1. **Creating Segments in Audiences**

    1. Navigate from your AEM instance to **Personalization** &gt; **Audiences** &gt; **screens**.

    1. Click **Create** &gt; **Create Context Hub Segment.** The **New ContextHub Segment** dialog box opens.

    1. Enter the **Title** as **TargetValue1** and click **Create**. Similarly, create another segment titled as **TargetValue2**.

       ![image](/help/user-guide/assets/context-hub/context-hub10.png)



## Step 4: Setting Up Audience Segmentation {#step-setting-up-audience-segmentation}

Pending to add editing

Once you have set up a data store and defined your activity (brand and area), follow the steps below to set up audience segments:

1. **Creating Segments in Audiences**

    1. Navigate from your AEM instance to **Personalization** &gt; **Audiences** &gt; **screens**.

    1. Click **Create** &gt; **Create Context Hub Segment.** The **New ContextHub Segment** dialog box opens.

    1. Enter the **Title** as **TargetValue1** and click **Create**. Similarly, create another segment titled as **TargetValue2**.

       ![image](/help/user-guide/assets/context-hub/context-hub10.png)


1. **Editing the Segments**

    1. Select the segment **TargetValue1**, and click **Edit** from the action bar.

    1. Drag and drop the **Comparison: Property - Value** component to the editor.
    1. Click the wrench icon to open the **Comparing a property with value** dialog box.
    1. Select **googlesheets/value/1/0** from the drop-down in **Property name**.

    1. Select the **Operator** as **equal** from the drop-down menu.

    1. Enter the **Value** as **1**.

   >[!NOTE]
   >
   >The AEM validates your data from the Google Sheet by showing your segment as green.

   ![screen_shot_2019-04-23at20142pm](assets/screen_shot_2019-04-23at20142pm.png)

   Similarly, edit the property values to **TargetValue2**.

    1. Drag and drop the **Comparison: Property - Value** component to the editor.
    1. Click the wrench icon to open the **Comparing a property with value** dialog box.
    1. Select **googlesheets/value/1/0** from the drop-down in **Property name**.

    1. Select the **Operator** as **Equal** from the drop-down menu.

    1. Enter the **Value** as **2**.

## Step 5: Setting Up Brand and Area {#setting-brand-area}

Follow the steps below to create a brand in your activities and area under the brand:

1. **Creating a Brand in Activities**

    1. Navigate from your AEM instance to **Personalization** &gt; **Activities**.

    1. Click **Create** &gt; **Create Brand**.

    1. Select **Brand** from the **Create Page** wizard and click **Next**.

    1. Enter the **Title** as **ScreensBrand** and click **Create**. Your brand is now created as shown below.

       ![image](/help/user-guide/assets/context-hub/context-hub8.png)


       >[!CAUTION]
       >
       >Known Issue:
       >To add an area, remove the master from the URL, such as
       >`http://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/screensbrand/master`.

1. **Creating an Area in your Brand**

    Follow the steps below to create an area in the brand:

      1. Click **Create** and then **Create Area**.

         ![image](/help/user-guide/assets/context-hub/context-hub9.png)

      1. Select **Area** from the **Create Page** wizard and click **Next**.

      1. Enter the **Title** as **ScreensValue** and click **Create**. 
       An area will be created in your brand.

## Step 6: Setting up the Activity {#step-setting-up-activity}

Follow the steps below to create an area in the brand:

   1. Navigate to **ScreensValue** (created in the preceding step) and click **Create** &gt; **Create Activity**.

   1. The **Configure Activity Wizard** opens. Enter the **Title** as **targetvaluecheck** and **Name** as **targetvaluecheck**. Select the **Targeting engine** as **ContextHub (AEM)** from the drop-down and click **Next**.

   1. Click **Add Experience** from the **Configure Activity Wizard**.

   1. From the **Audiences**, select the **TargetValue1** and click **Add Experience** and enter the **Title** as **valuecheck** **Name** as **valuecheck**.

   1. Similarly, From the **Audiences**, select the **TargetValue2** and click **Add Experience** and enter the **Title** as **valuecheck** **Name** as **valuecheck2**.

   1. Click **Next** and then **Save**.

## Enabling Targeting in Channels {#step-enabling-targeting-in-channels}

Follow the steps below to enable targeting in your channels.

1. Navigate to one of the AEM Screens channel. The following steps demonstrate how to enable targeting by using **DataDrivenRetail** created in an AEM Screens Channel.

1. Select the channel **DataDrivenRetail** and click **Properties** from the action bar.

   ![screen_shot_2019-05-01at43332pm](assets/screen_shot_2019-05-01at43332pm.png)

1. Select the **Personalization** tab to setup the ContextHub configurations.

    1. Select the **ContextHub Path** as **libs** &gt; **settings** &gt; **cloudsettings** &gt; **default** &gt; **ContextHub Configurations** and click **Select**.

    1. Select the **Segments Path** as **conf** &gt; **We.Retail** &gt; **settings** &gt; **wcm** &gt; **segments** and click **Select**.

    1. Click **Save & Close**.

   >[!NOTE]
   >
   >Use the ContextHub and the Segments path, where you initially saved your context hub configurations and segments.

   ![screen_shot_2019-05-01at44030pm](assets/screen_shot_2019-05-01at44030pm.png)

1. Navigate and select the **DataDrivenRetail** from **DataDrivenAssets** &gt; **Channels** and click **Edit** from the action bar.

   >[!NOTE]
   >
   >If you have set up everything correctly, you will see **Targeting** option in the drop-down from the editor, as shown in the figure below.

   ![screen_shot_2019-05-01at44231pm](assets/screen_shot_2019-05-01at44231pm.png)

   >[!NOTE]
   >
   >Once you have configured the ContextHub configurations for your channel, make sure you follow preceding steps from 1 through 4, for the other three sequence channels too if you want to follow all the use cases below.

## Learn More: Example Use Cases {#learn-more-example-use-cases}

After you have configured ContextHub for your AEM Screens project, you can follow the different Use Cases to understand how data triggered assets plays a vital role in different industries:

1. **[Retail Inventory Targeted Activation](retail-inventory-activation.md)**
1. **[Travel Center Temperature Activation](local-temperature-activation.md)**
1. **[Hospitality Reservation Activation](hospitality-reservation-activation.md)**
