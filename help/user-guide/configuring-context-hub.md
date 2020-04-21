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

>[!CAUTION]
>
>Google Sheets is used in the following example as a sample database system from where the values are fetched and is solely for educational purposes. Adobe does not endorse using Google Sheets for production environments.
>
>For more information, refer to [Get API Key](https://developers.google.com/maps/documentation/javascript/get-api-key) in Google documentation.


## Step 1: Setting up a Data Store {#step-setting-up-a-data-store}

You can set up the data store as a Local I/O event or as a local database event. 

The following asset level data triggers example showcases a local database event that sets up a data store such as an excel sheet that allows you to use ContextHub configurations and segments path to AEM Screens channel.

Once you have set up the google sheet correctly for example as shown below: 

![image](/help/user-guide/assets/context-hub/context-hub1.png)

The following validation is what you will view when you check your connection by entering the google sheet ID and API key in the format below:

`https://sheets.googleapis.com/v4/spreadsheets/<your sheet id>/values/Sheet1?key=<your API key>`

![image](/help/user-guide/assets/context-hub/context-hub2.png)


>[!NOTE]
>**Using the Google Sheet values in AEM**
>The Google Sheets will expose its values in the ContextHub Store, and will be available under `<store-name>/values/<i>/<j>`, where `<i>` and `<j>` are the row and column indexes in the spreadsheet (starting from 0).
>
> * /values/0/0 points to A1
> * /values/5/0 points to A5
> * /values/0/5 points to E1

The specific example below shows the the excel sheet as a data store that will trigger asset change if the value is higher than 100 or less than 50.


1. **Navigating to ContextHub**

   Navigate to your AEM instance and click the tools icon from left sidebar. Click **Sites** --&gt; **ContextHub**, as shown in the figure below.

   ![screen_shot_2019-04-22at53222pm](assets/screen_shot_2019-04-22at53222pm.png)

1. **Creating a new ContextHub Store Configuration**

    1. Navigate to **global** &gt; **default** &gt; **ContextHub Configuration**.

    1. Click **Create** &gt; **Configuration Container** and enter the title as **ContextHubDemo**.

    1. **Navigate** to **ContextHubDemo** &gt; **ContentHub Store Configuration...** to open the **Configure wizard**.

    1. Enter the **Title** as **Google Sheets**, **Store Name** as **googlesheets**, and **Store Type** as **contexthub.generic-jsonp**

   >[!CAUTION]
   >
   >In AEM 6.4, please use the **Configuration Title** as **googlesheets** and and **Store Type** as **contexthub.generic-jsonp**
   
    1. Click **Next**
    1. Enter your specific json configuration. For example, you can use the following json for demo purposes.
    1. Click **Save**.

   ```
   {
     "service": {
       "host": "sheets.googleapis.com",
       "port": 80,
       "path": "/v4/spreadsheets/<your google sheet id>/values/Sheet1",
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
   >
   >
   >Replace the code with your *&lt;Sheet ID&gt;* and *&lt;API Key&gt;*, that you fetched while setting up the Google Sheets.

   >[!CAUTION]
   >
   >If you create your Google Sheets store configurations outside of the global folder (for instance in your own project folder), then targeting will not work out of the box.
   >
   >
   >In case, you want to configure the Google Sheets store configurations outside the global folder, then you should must set the **Store Name** as **segmentation** and **Store Type** as **aem.segmentation**. Additionally, you have to skip the process of defining the json as defined above.

1. **Creating a Brand in Activities**

    1. Navigate from your AEM instance to **Personalization** &gt; **Activities**

    1. Click **Create** &gt; **Create Brand**

    1. Select **Brand** from the **Create Page** wizard and click **Next**

    1. Enter the **Title** as **ContextHubDemo** and click **Create**. Your brand is now created as shown below.

   ![screen_shot_2019-05-05at44305pm](assets/screen_shot_2019-05-05at44305pm.png)


   >[!CAUTION]
   >
   >Known Issue:
   >
   >
   >To add an area, remove the master from the URL, such as
   >
   >
   >`https://localhost:4502/libs/cq/personalization/touch-ui/content/v2/activities.html/content/campaigns/contexthubdemo/master`

1. **Creating an Area in your Brand**

    Follow the steps below to create an area in the brand:

      1. Click **Create** and then **Create Area**

      1. Select **Area** from the **Create Page** wizard and click Next

      1. Enter the **Title** as **GoogleSheets** and click **Create**. 
       Your area will be created in your activity.

## Step 2: Setting Up Audience Segmentation {#step-setting-up-audience-segmentation}

Once you have set up a data store and defined your brand, follow the steps below to set up audience segments.

1. **Creating Segments in Audiences**

    1. Navigate from your AEM instance to **Personalization** &gt; **Audiences** &gt; **screens**.

    1. Click **Create** &gt; **Create Context Hub Segment.** The **New ContextHub Segment** dialog box opens.

    1. Enter the **Title** as **SheetA1 1** and click **Create**. Similarly, create another segment titled as **SheetA2 2**.

1. **Editing the Segments**

    1. Select the segment **Sheets A1 1**, and click **Edit** from the action bar.

    1. Drag and drop the **Comparison: Property - Value** component to the editor.
    1. Click the wrench icon to open the **Comparing a property with value** dialog box.
    1. Select **googlesheets/value/1/0** from the drop-down in **Property name**.

    1. Select the **Operator** as **Equal** from the drop-down menu.

    1. Enter the **Value** as **1**.

   >[!NOTE]
   >
   >The AEM validates your data from the Google Sheet by showing your segment as green.

   ![screen_shot_2019-04-23at20142pm](assets/screen_shot_2019-04-23at20142pm.png)

   Similarly, edit the property values to **Sheets A1 2**.

    1. Drag and drop the **Comparison: Property - Value** component to the editor.
    1. Click the wrench icon to open the **Comparing a property with value** dialog box.
    1. Select **googlesheets/value/1/0** from the drop-down in **Property name**.

    1. Select the **Operator** as **Equal** from the drop-down menu.

    1. Enter the **Value** as **2**.


## Step 3: Enabling Targeting in Channels {#step-enabling-targeting-in-channels}

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
