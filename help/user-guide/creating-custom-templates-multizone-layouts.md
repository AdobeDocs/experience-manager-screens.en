---
title: Creating Custom Templates in MultiZone Layouts
seo-title: Creating Custom Templates in MultiZone Layouts
description: Follow this page to learn about creating custom templates in MultiZone layouts.
seo-description: Follow this page to learn about creating custom templates in MultiZone layouts.
contentOwner: Jyotika Syal
---

# Creating Custom Templates in MultiZone Layouts {#creating-custom-templates-multizone}

This page showcases how you can create a custom template in a multi-zone layout.

## Naming Convention {#name-terms}

Before you understand how to create custom multi-zone templates to use in an AEM Screens project, it is recommended to understand the verbiage of the templates you would want to create.

| **Layout Name** | **Description** |
|---|---|
| Left20-LandscapeHD3Zone | Refers to a 3-zone landscape layout that allows you to create 3 zones with zone 1 as 20% of the horizontal and vertical screen from the left, zone 2 as 80 % of the horizontal screen and 20 % of vertical screen right justified, zone 3 as 100 % of horizontal and 80 % of the vertical screen with aspect ratio of 16:9 |
| Upper20-PortraitHD2Zone | Refers to a 2-zone portrait template that covers 20% of the screen from the top, with aspect ratio of 16:9 | 
| Right20-LandscapeSD3Zone | Refers to a 3-zone template that covers 20% of the screen from the right, with aspect ratio of 4:3 | 

## Example Use Cases {#example-use-cases}

## Left20-LandscapeHD3Zone Layout {#custom-template-one}

Follow the section below to create a custom template *Left20-LandscapeHD3Zone* with the following configuration:

*  **Left20** refers to the to the top zone on the left covering 20% of horizontal and vertical screen size.
* **Landscape** refers to the screen orientation
* **HD** refers to the aspect ratio as 16:9
* **3Zone** refers to three zones of the display

## Visual Representation of MultiZone Layout {#multi-layout-visual-one}

The Left20-LandscapeHD3Zone Layout allows you to create the following multi-zone layout in your project:

![image](/help/user-guide/assets/custom-multizone/custom-multizone1.png)

## Creating a Left20-LandscapeHD3Zone Layout {#landscape-layout-one}

Follow the steps below to create a Left20-LandscapeHD3Zone Layout for an AEM Screens project:

1. Create an AEM Screens project titled as **customtemplate**.

   ![image](/help/user-guide/assets/custom-multizone/custom-template2.png)
   
1. Navigate to **CRXDE Lite** from your AEM instance --> Tools --> **CRXDE Lite**.

1. Create a folder under **apps** titled as **customtemplate**. Similarly, create another folder titled as **template** under **customtemplate**, as shown in the figure below.

   ![image](/help/user-guide/assets/custom-multizone/custom-template1.png)

   > [!NOTE]
   > It is recommended that you click on **Save all** from the action bar in CRXDE Lite each time you create, edit, or copy content to any of the nodes, otherwise you will not be able to commit the updates.

1. Copy the lbar-left template from `/libs/screens/core/templates/splitscreenchannel/lbar-left` to `/apps/customtemplate/template`. 

1. Rename the copied **lbar-left** (`/apps/customtemplate/template`) to **my-custom-layout**.
   ![image](/help/user-guide/assets/custom-multizone/custom-template3.png)

1. Navigate to `/apps/customtemplate/template/my-custom-layout` and update the properties **jcr:description** to *Template for Left20-LandscapeHD3Zone* and **jcr:title** to *Left20-LandscapeHD3Zone*.

   ![image](/help/user-guide/assets/custom-multizone/custom-template4.png)

1. Navigate to the **offline-config** node from `/apps/customtemplate/template/my-custom-layout/jcr:content/offline-config` and update the **jcr:title** to *Left20-LandscapeHD3Zone*.

   ![image](/help/user-guide/assets/custom-multizone/custom-template5.png)

1. Navigate to the *jcr:content* property of **my-custom-template** from `/apps/customtemplate/template/my-custom-layout/jcr:content` and update the **cq:cssClass** property to **aem-Layout my-custom-layout**.

   ![image](/help/user-guide/assets/custom-multizone/custom-template6.png)

1. Referring to step (4), in which, you copied the lbar-left template, you will view 3 responsive grids under `my-custom-layout/jcr:content`. Add custom css class to each of the responsive grid in the *cq:cssClass* property, for example, *my-custom-layout--top-left* for *r1c1* node.

   ![image](/help/user-guide/assets/custom-multizone/custom-template7.png)

   Similarly, add *my-custom-layout--top-right* for *r1c2*  and, *my-custom-layout--bottom* for *r2c1* node.

   >[!NOTE]
   >These custom classes will be used in the css to set the width/height for these responsive grids.

   >[!NOTE]
   > You can add or remove the responsive grids based on the number of total grids you want. In this example, we showcase 2 grids in the first row and 1 grid in the second row, so there are a total of 3 responsive grids (r1c1, r1c2, r2c1).

1. Copy `/libs/settings/wcm/designs/screens` to `/apps/settings/wcm/designs/` and rename the copied design as **custom-template-designs**.

1. Navigate to `/apps/settings/wcm/designs/custom-template-designs` and update the property *jcr:title* of **custom-template-designs** to **customtemplate-design**.

1. Navigate to `/apps/settings/wcm/designs/custom-template-designs` and create a file static.css.

1. Copy the content to static.css file:

   ```shell
       /*my-custom-layout styles*/
      .cq-Screens-channel--multizone.my-custom-layout .my-custom-layout--top-left {
       width:20%;
        height: 36%;
       float: left !important;
      }
      .cq-Screens-channel--multizone.my-custom-layout .my-custom-layout--top-right {
      width:80%;
      height: 36%;
      float: left !important;
      }
      .cq-Screens-channel--multizone.my-custom-layout .my-custom-layout--bottom {
      width:100%;
      height: 64%;
      }
   ```
   
   >[!NOTE]
   > You can update the percentages to match requirements for your custom template.

1. Navigate to `/apps/<project>/templates/my-custom-layout/jcr:content` and update the property *cq:designPath* to `/apps/settings/wcm/designs/customtemplate-designs` to load the styles configured in static.css

   >[!NOTE]
   > It is recommended that you type all the styles rather than copy or pasting, that can cause white spaces resulting in css styling issues.

## Viewing the Result {#viewing-result}

Follow the steps below to use the above customized template in your AEM Screens project:

1. Navigate to your Screens project that you created in step (1) and select the **Channels** folder.

   ![image](/help/user-guide/assets/custom-multizone/custom-template8.png)

1. Click **Create** from the action bar and select the template **Left20-LandscapeHD3Zone** from the **Create** wizard.

1. Once you have created a channel with the customized template, you can add assets to your channel from the editor.

## Inserting an image as the Background Layer  {#inserting-image}

You can insert an image as a background layer to the layout:

You can adjust the CSS rule to use what is called “data-uri” and directly inline the image (Base64 encoded) in the CSS file. 

This is done as follows:
`.cq-Screens-channel--multizone.my-CustomLayout { background: url('data:image/…;base64,…') no-repeat center center; }`
 
Or, you can follow the steps below:

1. Make sure the image is somehow included in the offline config for the channel
1. Use a direct link to the image in the CSS above, instead of the “data-uri” variant


## Updating Background Color {#updating-color}

To change the background color, add the following code to the xml file:

`.cq-Screens-channel--multizone.my-CustomLayout { background-color: …; }`



