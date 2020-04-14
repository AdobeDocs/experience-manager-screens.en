---
title: Text Overlay
seo-title: Text Overlay
description: Text Overlay is a feature available in AEM Screens that allows you to create a compelling experience in a Sequence Channel by providing a title or a description overlaid on top of an image. Follow this page to learn more.
seo-description: Text Overlay is a feature available in AEM Screens that allows you to create a compelling experience in a Sequence Channel by providing a title or a description overlaid on top of an image. Follow this page to learn more.
uuid: 944477e8-0025-4cc7-aa61-6b72f4a245fd
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
discoiquuid: b6fdb5a0-5601-4443-a3f4-85cc90c49914
noindex: true
---

# Text Overlay {#text-overlay}

This section covers the following topics:

* **Overview**
* **Using Text Overlay**
* **Prerequisites**
* **Understanding Text Overlay Properties**

>[!CAUTION]
>
>The **Text Overlay** feature is only available, if you have installed AEM 6.3 Feature Pack 5 or AEM 6.4 Feature Pack 3.

## Overview {#overview}

Text Overlay is a feature available in AEM Screens that allows you to create a compelling experience in a Sequence Channel by providing a title or a description overlaid on top of an image.

To learn how to create your own custom component, please refer to **Extending an AEM Screens Component**.

This section only showcases how to use and leverage the poster component in an AEM Screens project and use it as text overlay in one of your sequence channels.

## Using Text Overlay {#using-text-overlay}

The following section describes the use of text overlay in an AEM Screens project.

### Prerequisites {#prerequisites}

Before you start implementing this functionality, please make sure you have set up a project as a prerequisite to start implementing text overlay. For example,

* Create an AEM Screens project (in this example, **TextOverlayDemo**)

* Create a sequence channel titled as **TextSample** under **Channels** folder

* Add content to your **TextSample** Channel

The following image shows the **TextOverlayDemo** project with **TextSample** channel in **Channels** folder.

![screen_shot_2018-12-16at75908pm](assets/screen_shot_2018-12-16at75908pm.png)

### Using Text Overlay {#using-text-overlay}

Follow the steps below to use text overlay in an AEM Screens channel:

1. Navigate to **TextOverlayDemo** --&gt; **Channels** --&gt; **TextSample** and click **Edit** from the action bar to open the editor.

   ![screen_shot_2018-12-16at80017pm](assets/screen_shot_2018-12-16at80017pm.png)

1. Select the image and click **Configure** (wrench icon) to open the properties dialog box.

   ![screen_shot_2018-12-16at80221pm](assets/screen_shot_2018-12-16at80221pm.png)

1. Select the **Text Overlay** option from the navigation bar of the dialog box, as shown in the figure below.

   ![screen_shot_2018-12-16at80424pm](assets/screen_shot_2018-12-16at80424pm.png)

### Understanding Text Overlay Properties {#understanding-text-overlay-properties}

Using the Text Overlay properties, you can add text to any of the component in your Screens project. The following section provides an overview of the properties that are available in Text Overlay:

![text](assets/text.gif)

You can add a text to the text box and add typographical emphasis such as bold, italics, underline, and so on.

**Color Variant** This option allows the text to be either Dark (text in black color) or Light (text in white color).

**Sizing & positioning** This option allows the user to align the text horizontally or vertically or additionally use fine-grained tools for text alignment.

>[!NOTE]
>
>To properly use fine-grained tools, be sure to identify the correct position in pixels using (px) as a suffix, for example 200px. The result of this expression will be 200 pixels from start point.

## Using ContextHub Values in Text Overlay {#using-text-overlay-context-hub}

The following section describes the usage of values from a data store, for example, google sheets in text overlay component. 

**Prerequisites**

You must set up ContextHub configurations for your AEM Screens project. 

To learn how to setup and manage data driven asset changes using a a data store, refer to [Configuring ContextHub in AEM Screens](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/developing/configuring-context-hub.html).

Once you have set up the required configurations for your project, follow the steps below to use values from the google sheets: 

1. Navigate to **TextOverlayDemo** --&gt; **Channels** --&gt; **TextSample** and click **Properties** from the action bar.

1. Select the **Personalization** tab to setup the ContextHub configurations.

    1. Select the **ContextHub Path** as **libs** &gt; **settings** &gt; **cloudsettings** &gt; **default** &gt; **ContextHub Configurations** and click **Select**.

    1. Select the **Segments Path** as **conf** &gt; **screens** &gt; **settings** &gt; **wcm** &gt; **segments** and click **Select**.

    1. Click **Save & Close**.

       >[!NOTE]
       >
       >Use the ContextHub and the Segments path, where you initially saved your context hub configurations and segments.

       ![image1](/help/user-guide/assets/text-overlay/text-overlay8.png)

1. Navigate to **TextOverlayDemo** --&gt; **Channels** --&gt; **TextSample** and click **Edit** from the action bar to open the editor.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay1.png)

1. Add an image and text overlay component to your image as described in [Using Text Overlay](#using-text-overlay) section of this page.

1. Click on **Configure** (wrench icon) to open the **Image** dialog box.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay4.png)

1. Navigate to the **ContextHub** tab from the **Image** dialog box. Click **Add**.

   >[!NOTE]
   >If you have not setup your ContextHub configurations, this option will be disabled for your project.

1. Enter **Value** in the **Placeholder** field, select the row that you want to get the value from your google sheet in **ContextHub Variable** (in this case, the value is retrieved from row 2 and column 1 from the google sheets), and enter the **Default Value** as **20**, a shown in the figure below. Once you are done click on the check-mark.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay5.png)

   >[!NOTE]
   >For your reference, the following image showcases the value that is retrieved from the google sheets:

   ![image1](/help/user-guide/assets/text-overlay/text-overlay6.png)

1. Navigate back to the **Text Overlay** tab from the Image dialog box and add the text *Current Temperature {Value}*, as shown in the figure below.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay7.png)

1. Click on **Preview** to view the desired output.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay10.png)
   














