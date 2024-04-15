---
title: Embedding a REACT application using the AEM SPA Editor and Integrating with AEM Screens Analytics
description: Learn how to embed an interactive single page application using REACT (or Angular) using the AEM SPA editor.
content-type: reference
topic-tags: developing
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
discoiquuid: e4ecc179-e421-4687-854c-14d31bed031d
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 7dc7d07e-cd94-4ce1-a106-98669be62046
---
# Embedding a REACT application using the AEM SPA Editor and Integrating with AEM Screens Analytics {#embedding-a-react-application-using-the-aem-spa-editor-and-integrating-with-aem-screens-analytics}

You can embed an interactive single page application using REACT (or Angular). You do so by using the AEM SPA editor that is configured by business professionals in AEM. You can also learn how to integrate your interactive application with offline Adobe Analytics.

## Using the AEM SPA Editor {#using-the-aem-spa-editor}

Follow the steps below to use the AEM SPA Editor:

1. Clone the AEM SPA Editor repo at [https://github.com/adobe/aem-spa-project-archetype.](https://github.com/adobe/aem-spa-project-archetype)

   >[!NOTE]
   >
   >This archetype creates a minimal Adobe Experience Manager project as a starting point for your own SPA projects. The properties that must be provided when using this archetype let you name as desired all parts of this project.

1. To create an AEM SPA editor archetype project, follow the readme instructions:

   ```
   mvn clean install archetype:update-local-catalog
   mvn archetype:crawl

   mvn archetype:generate \
   -DarchetypeCatalog=internal \
   -DarchetypeGroupId=com.adobe.cq.spa.archetypes \
   -DarchetypeArtifactId=aem-spa-project-archetype \
   -DarchetypeVersion=1.0.3-SNAPSHOT \
   ```

   >[!NOTE]
   >
   >This documentation uses the **GroupId** as ***com.adobe.aem.screens*** and the **ArtifactId** as ***My Sample SPA*** (which are the defaults). You can choose your own as needed.

1. After the project is created, either use an IDE or editor of your choice and import the generated Maven project.
1. Deploy to your local AEM instance using the command ***mvn clean install -PautoInstallPackage***.

### Editing content in the REACT app {#editing-content-in-the-react-app}

To edit the contents in the REACT app:

1. Navigate to `https://localhost:4502/editor.html/content/mysamplespa/en/home.html` (replace the hostname, port, and project name as applicable).
1. You should be able to edit the text being displayed in the Hello world application.

### Adding the interactive REACT app to AEM Screens {#adding-the-interactive-react-app-to-aem-screens}

Follow the steps below to add the interactive REACT app to AEM Screens:

1. Create an AEM Screens project. See [Creating and Managing Projects](creating-a-screens-project.md) for more details.
1. Create an **Application Channel** (preferably) (or 1x1 template, or multi-zone channel) in the **Channels** folder of your AEM Screens project.

    >[!NOTE]
    >**Sequence Channels** are discouraged for this use case because they inherently come with a slideshow logic that conflicts with the interactive nature of the experience.
    >See [Creating and Managing Channels](managing-channels.md) for more details.

1. Edit any sequence channel and drag and drop an embedded page component.

   See [Adding Components to a Channel](adding-components-to-a-channel.md) for more details.

   >[!NOTE]
   >
   >Make sure you add the user interaction event when assigning the channel to the display.

1. Select **Edit** from the action bar so you can edit the properties of the channel.

   ![screen_shot_2019-02-15at100555am](assets/screen_shot_2019-02-15at100555am.png)

1. Drag and drop the **Embedded Page** component , or reuse the existing component in an application channel, and select the home page under the mysamplespa application, for example, ***/content/mysamplespa/en/home***.

   ![screen_shot_2019-02-15at101104am](assets/screen_shot_2019-02-15at101104am.png)

1. Assign the channel to a display.

    >[!NOTE]
    >Make sure you add the user interaction event when assigning the channel to the display.

1. Register a player against this project and assign it to the display. You should now be able to see your interactive application running on AEM Screens.

   See [Device Registration](device-registration.md) for more information about registering a device.

## Integrating the SPA with Adobe Analytics with Offline Capability through AEM Screens {#integrating-the-spa-with-adobe-analytics-with-offline-capability-through-aem-screens}

Follow the steps below to integrate the SPA with Adobe Analytics with offline capability through AEM Screens:

1. Configure Adobe Analytics in AEM Screens.

   See [Configuring Adobe Analytics with AEM Screens](configuring-adobe-analytics-aem-screens.md) for more information about how to perform sequencing in Adobe Analytics with AEM Screens and send custom events using offline Adobe Analytics.

1. Edit your react app in the IDE/editor of your choice (especially the text component or other component which you wish to start emitting events).
1. On the select event or other event that you wish to capture for your component, add the analytics information using the standard data model.

   See [Configuring Adobe Analytics with AEM Screens](configuring-adobe-analytics-aem-screens.md) for more details.

1. Call the AEM Screens Analytics API so you can save the event offline and send it in bursts to Adobe Analytics.

   For example,

   ```
   handleClick() {
       if ((window.parent) && (window.parent.CQ) && (window.parent.CQ.screens) && (window.parent.CQ.screens.analytics))
       {
           var analyticsEvent = {};
           analyticsEvent['event.type'] = 'play'; // Type of event
    analyticsEvent['event.coll_dts'] = new Date().toISOString(); // Start of collecting the event
    analyticsEvent['event.dts_start'] = new Date().toISOString(); // Event start
    analyticsEvent['content.type'] = 'Washing machine'; // Mime Type or product category
    analyticsEvent['content.action'] = 'Path to the washing machine asset in AEM'; // Path in AEM to relevant asset
    analyticsEvent['trn.product'] = 'Washing machine Model number'; // Product being explored
    analyticsEvent['trn.amount'] = 1000; // Product pricing or other numeric value or weight
    analyticsEvent['event.dts_end'] = new Date().toISOString(); // Event end
    analyticsEvent['event.count'] = 100; // Numeric value that may count a number of clicks or keystrokes or wait time in seconds for example
    analyticsEvent['event.value'] = 'My favorite analytics event';
           analyticsEvent['trn.quantity'] = 10; // Quantity of product selection
    analyticsEvent['event.subtype'] = 'end'; // Event subtype if applicable
    window.parent.CQ.screens.analytics.sendTrackingEvent(analyticsEvent);
       }
   }
   ```

   >[!NOTE]
   >
   >The player firmware automatically adds more details about the player and its runtime environment to the custom analytics data that you send. Hence, you may have to capture low-level OS/device details unless necessary. Focus on the business analytics data.
