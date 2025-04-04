---
title: Text Overlay
description: Learn about text Overlay in AEM Screens that lets you create a compelling experience in a Sequence Channel by providing a title or a description overlaid on top of an image.
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
content-type: reference
topic-tags: authoring
noindex: true
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: bbc719df-24a7-4cfb-9786-1c3496f9f082
---
# Text Overlay {#text-overlay}

This section covers the following topics:

* **Overview**
* **Using Text Overlay**
* **Understanding Text Overlay Properties**
* **Using ContextHub Values in Text Overlay**

>[!CAUTION]
>
>The **Text Overlay** feature is only available if you have installed AEM 6.3 Feature Pack 5 or AEM 6.4 Feature Pack 3.

## Overview {#overview}

Text Overlay is a feature available in AEM Screens. It lets you create a compelling experience in a Sequence Channel by providing a title or a description overlaid on top of an image.

To learn how to create your own custom component, see **Extending an AEM Screens Component**.

This section only showcases how to use and apply the poster component in an AEM Screens project. It also showcases using it as a text overlay in one of your sequence channels.

## Using Text Overlay {#using-text-overlay}

The following section describes the use of text overlay in an AEM Screens project.

**Prerequisites**

Before implementing this functionality, make sure you have set up a project as a prerequisite to start implementing text overlay. For example,

* Create an AEM Screens project (in this example, **TextOverlayDemo**)

* Create a sequence channel titled as **TextSample** under the **Channels** folder

* Add content to your **TextSample** Channel

The following image shows the **TextOverlayDemo** project with the **TextSample** channel in the **Channels** folder.

![screen_shot_2018-12-16at75908pm](assets/screen_shot_2018-12-16at75908pm.png)

Follow the steps below to use text overlay in an AEM Screens channel:

1. Navigate to **TextOverlayDemo** > **Channels** > **TextSample** and click **Edit** from the action bar.

   ![screen_shot_2018-12-16at80017pm](assets/screen_shot_2018-12-16at80017pm.png)

1. Click the image and click **Configure** (wrench icon) to open the properties dialog box.

   ![screen_shot_2018-12-16at80221pm](assets/screen_shot_2018-12-16at80221pm.png)

1. Click the **Text Overlay** option from the navigation bar of the dialog box, as shown in the figure below.

   ![screen_shot_2018-12-16at80424pm](assets/screen_shot_2018-12-16at80424pm.png)

### Understanding Text Overlay Properties {#understanding-text-overlay-properties}

Using the Text Overlay properties, you can add text to any of the components in your Screens project. The following section provides an overview of the properties that are available in Text Overlay:

![text](assets/text.gif)

You can add a text to the text box and add typographical emphasis such as bold, italics, and underline.

**Color Variant** This option allows the text to be either Dark (text in black color) or Light (text in white color).

**Sizing & positioning** This option lets the user align the text horizontally or vertically or also use fine-grained tools for text alignment.

>[!NOTE]
>
>When using fine-grained tools, be sure to identify the correct position in pixels using (px) as a suffix, for example 200 px. The result of this expression is 200 pixels from the start point.

## Using ContextHub Values in Text Overlay {#using-text-overlay-context-hub}

The following section describes the usage of values from a data store, for example, google sheets in the text overlay component. 

**Prerequisites**

Set up ContextHub configurations for your AEM Screens project. 

To learn how to setup and manage data driven asset changes using a data store, see [Configuring ContextHub in AEM Screens](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/developing/configuring-context-hub).

After you set up the required configurations for your project, follow the steps below to use values from the Google Sheets: 

1. Navigate to **TextOverlayDemo** > **Channels** > **TextSample** and click **Properties** from the action bar.

1. Click the **Personalization** tab so you can set up the ContextHub configurations.

    1. Click the **ContextHub Path** as **libs** > **settings** > **cloudsettings** > **default** > **ContextHub Configurations** and click **Select**.

    1. Click the **Segments Path** as **conf** > **screens** > **settings** > **wcm** > **segments** and click **Select**.

    1. Click **Save & Close**.

       >[!NOTE]
       >
       >Use the ContextHub and the Segments path, where you initially saved your context hub configurations and segments.

       ![image1](/help/user-guide/assets/text-overlay/text-overlay8.png)

1. Navigate to **TextOverlayDemo** > **Channels** > **TextSample** and click **Edit** from the action bar.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay1.png)

1. Add an image and text overlay component to your image as described in the [Using Text Overlay](/help/user-guide/text-overlay.md#using-text-overlay) section of this page.

1. Click on **Configure** (wrench icon) to open the **Image** dialog box.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay4.png)

1. Navigate to the **ContextHub** tab from the **Image** dialog box. Click **Add**.

   >[!NOTE]
   >If you have not set up your ContextHub configuration, this option is disabled for your project.

1. Enter **Value** in the **Placeholder** field. Click the row that you want to get the value from your Google sheet in **ContextHub Variable**. In this case, the value is retrieved from row 2 and column 1 from the Google sheets. Now, enter the **Default Value** as **20**, a shown in the figure below. When you are done, click the checkmark.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay5.png)

   >[!NOTE]
   >For your reference, the following image showcases the value that is retrieved from the Google Sheets:

   ![image1](/help/user-guide/assets/text-overlay/text-overlay6.png)

1. Navigate back to the **Text Overlay** tab from the Image dialog box and add the text *Current Temperature {Value}*, as shown in the figure below.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay7.png)

1. Click **Preview**.

   ![image1](/help/user-guide/assets/text-overlay/text-overlay10.png)
