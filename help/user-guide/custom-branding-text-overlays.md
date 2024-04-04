---
title: Applying Custom Branding and Styling for Text Overlays
seo-title: Applying Custom Branding and Styling for Text Overlays
description: Follow this page to learn how to apply custom branding and styling for Text Overlays.
seo-description: Follow this page to learn how to apply custom branding and styling for Text Overlays.
contentOwner: Jyotika Syal
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 059e1b19-e9b5-48f0-8f2f-141f0c2f7842
---
# Custom Branding and Styling for Text Overlays {#creating-custom-branding-styling}

Follow this page to learn how to apply custom branding and styling for Text Overlays applied to your assets in an AEM Screens channel.

## Creating Custom Branding and Styling for Text Overlays {#steps-custom-branding}

Follow the steps below to create custom branding and styling for text overlays:

1. Create an AEM Screens project. This example showcases the functionality by creating a project named **customstyle** and a channel titled **DemoBrand** , as shown in the figure below.

    ![image](/help/user-guide/assets/custom-brand/custom-brand1.png)

1. From the editor drag and drop an image and add text overlay to the asset.

   ![image](/help/user-guide/assets/custom-brand/custom-brand2.png)  

   >[!NOTE]
   >To learn how to add a text overlay to your asset in a channel editor, refer to [Text Overlay](/help/user-guide/text-overlay.md).
   
1. Navigate to CRXDE Lite from your AEM instance > tools > **CRXDE Lite**.

1. You have to create a custom design in `/apps/settings/wcm/designs/<your-project>/`, for example, in this case, navigate to `/apps/settings/wcm/designs/customstyle/`

   ![image](/help/user-guide/assets/custom-brand/custom-brand3.png)

1. Create *static.css* file and set the following css rules. Also shown as an example in the figure below the css rules.

    ```shell
     //global styles
     cq-Screens-textOverlay {
     padding: 1em;
     font-size: 3rem;
     line-height: 1em;
      }
     //authoring overrides
    .aem-AuthorLayer-Edit .cq-Screens-textOverlay {
     display: none;
     padding: 0;
     font-size: 1rem;
     }
      // light text variant
     .cq-Screens-textOverlay-color--light {
      background-color: rgba(0, 0, 0, .6);
      }
      // dark text variant
      .cq-Screens-textOverlay-color--dark {
       background-color: rgba(255, 255, 255, .6);
     }
    ```

   ![image](/help/user-guide/assets/custom-brand/custom-brand4.png)

1. Copy the path to your project, in this case, the path will be `/apps/settings/wcm/designs/customstyle`.

1. Navigate to the channel titled as **DemoBrand** (created in step(1)) and click **Properties** from the action bar after selecting the channel.

1. Navigate to the **Advanced** tab and check the **Design** field.
   ![image](/help/user-guide/assets/custom-brand/custom-brand5.png)

   >[!NOTE]
   >Be default, the **Design** field shows the path pointing to designs  in libs folder.

1. Update the **Design** field with the path to your project folder. In this case, it will be, `/apps/settings/wcm/designs/customstyle`.

   ![image](/help/user-guide/assets/custom-brand/custom-brand6.png)

1. Click **Save & Close** to update the design path.

   >[!IMPORTANT]
   >You have the option to overlay the existing Screens templates to inject your own designs by default or create your own template altogether. Refer to the steps below for more details.

1. To overlay the existing Screens templates to inject your own designs by default: 

    1. Overlay `/libs/screens/core/templates/sequencechannel` in `/apps/screens/core/templates/sequencechannel`.
    1. Modify the *cq:designPath* property in `/apps/screens/core/templates/sequencechannel/jcr:content` to point to the new design.

1. To create your own template altogether:
     1. Copy `/libs/screens/core/templates/sequencechannel` to `/apps/customstyle/templates/styled-sequencechannel`.
     1. Modify the *cq:designPath* property in `/apps/customstyle/templates/styled-sequencechannel/jcr:content` to point to the new design.
 

### Updating ACLs {#updating-acls}

You must update the ACLs for these designs so that they can be downloaded by the player.

1. Navigate to user admin and choose the `screens-<project>-devices group` and give it read permission to the custom design path.

1. Provide `screens-<project>-administrators` group read and modify permissions to this path.

## Viewing the Result {#viewing-the-result}

Once you have completed the preceding steps, you can update your *statis.css* file from **CRXDE Lite** and consequently view the update to your text overlay that is already added to the asset.

Follow the steps below to view the updated design to text overlay:

1. Navigate to your AEM Screens project titled as **customstyle** > **Channels** > **DemoBrand**. Select the channel and click **Edit** from the action bar to open the editor.

1. Since you have now added the design to your **Designs** field, as mentioned above, click **Preview** to view the current styling on the image with text overlay.

   ![image](/help/user-guide/assets/custom-brand/custom-brand7.png)

1. Navigate to your *static.css* file in CRXDE Lite, and add the font such as, `font-family: "Lucida Console", Courier, monospace;` to this file, as shown below.
   ![image](/help/user-guide/assets/custom-brand/custom-brand8.png)

1. Once you save the changes and reload the preview you will see an update to the text overlay font, as shown in the figure below.

   ![image](/help/user-guide/assets/custom-brand/custom-brand9.png)

1. Additionally, you can remove the last two blocks of code from *static.css* file to remove the the boxed styling around the text overlay.
  ![image](/help/user-guide/assets/custom-brand/custom-brand10.png)

1. You will view the updated change in your preview where the text overlay is added to the image.

   ![image](/help/user-guide/assets/custom-brand/custom-brand11.png)

   Now you are ready to update your brand and custom styling for text overlays added to your assets.
