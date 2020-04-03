---
title: Applying Custom Branding and Styling for Text Overlays
seo-title: Applying Custom Branding and Styling for Text Overlays
description: Follow this page to learn how to apply custom branding and styling for Text Overlays.
seo-description: Follow this page to learn how to apply custom branding and styling for Text Overlays.
contentOwner: Jyotika Syal
---

# Custom Branding and Styling for Text Overlays {#creating-custom-branding-styling}

Follow this page to learn how to apply custom branding and styling for Text Overlays.

## Creating Custom Branding and Styling for Text Overlays {#steps-custom-branding}

Follow the steps below to create custom branding and styling for text overlays:

1. Create an AEM Screens project titled as **customstyle** and a channel titled as **DemoBrand**, as shown in the figure below.

    ![image](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. From the editor drag and drop an image and add text overlay to the asset.

   ![image](/help/user-guide/assets/custom-brand/custom-brand2.png)  

   >[!NOTE]
   >To learn how to add a text overlay to your asset in a a channel editor, refer to [Text Overlay](/help/user-guide/text-overlay.md).
   
1. Navigate to CRXDE Lite from your AEM instance --> Tools --> **CRXDE Lite**.

1. You have to create a custom design in `/apps/settings/wcm/designs/<your-project>/`, for example, in this case

   ![image](/help/user-guide/assets/custom-brand/custom-brand3.png)

1. Navigate to static.css file and set the following css rules. Also shown in the figure below.
   ```
    //global styles
    .cq-Screens-textOverlay
    { … }
    //authoring overrides
    .aem-AuthorLayer-Edit .cq-Screens-textOverlay { … }
    // light text variant
    .cq-Screens-textOverlay-color--light
    { … }
     // dark text variant
    .cq-Screens-textOverlay-color--dark { … }
    ```
   ![image](/help/user-guide/assets/custom-brand/custom-brand4.png)

1. Copy the path to your project, in this case, the path will be ``

1. Navigate to the channel titled as titled as **DemoBrand** (created in step(1)) and click **Properties** from the action bar after selecting the channel.

1. Navigate to the **Advanced** tab and check the **Design** field.
   ![image](/help/user-guide/assets/custom-brand/custom-brand5.png)

   >[!NOTE]
   >Be default, the **Design** field shows the path pointing to designs  in libs folder.

1. Update the **Design** field with the path to your project folder. In this case, it will be, `/apps/settings/wcm/designs/customstyle`.

   ![image](/help/user-guide/assets/custom-brand/custom-brand6.png)

1. Click **Save & Close** to update the design path.


## Viewing the Result {#viewing-the-result}

Once you have completed the preceding steps, you can update your *statis.css* file from **CRXDE Lite** and consequently view the update to your text layout added to the asset.

Follow the steps below to view the updated design to text layout:

1. Navigate to your AEM Screens project titled as **customstyle** and a channel titled as **DemoBrand** and click **Edit** from the action bar to open the editor.

1. Since you have now added the design to your **Designs** field, as mentioned above, click **Preview** to view the current styling on the image with text overlay.

   ![image](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Navigate to your static.css file in CRXDE Lite, 
example, add the font. 
   ![image](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Once you save the changes and reload the preview you will see an update the text overlay font, as shown in the figure below.

   ![image](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Additionally, you can remove the last two block of code from static.css file to remove the the boxed styling around the text overlay.
  ![image](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. You will view the updated change in your preview where the text overlay is added to the image, as shown below.

   ![image](/help/user-guide/assets/custom-brand/custom-brand11.png)

So, following the steps in the preceding sections, you can update your brand and custom styling for text overlays added to your assets.









