---
title: Using Experience Fragments
seo-title: Using Experience Fragments
description: Follow this page to learn about using Experience Fragments in AEM Screens. 
seo-description: Follow this page to learn about using Experience Fragments in AEM Screens. 
uuid: 6ee16a94-3c53-43e0-99d5-c35cb9e01120
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
discoiquuid: 0e88e9e0-a95b-4acd-98ea-499d4d4e3c99
docset: aem65

---

# Using Experience Fragments {#using-experience-fragments}

This page covers the following topics:

* **Overview**
* **Using Experience Fragments in AEM Screens**
* **Propagating Changes to the Page**

## Overview {#overview}

An ***Experience Fragment*** is a group of one or more components including content and layout that can be referenced within pages. Experience fragments can contain any component, such as, one or multiple components that can contain anything within a paragraph system, that will be referenced into the complete experience or requested by a third endpoint.


## Using Experience Fragments in AEM Screens {#using-experience-fragments-in-aem-screens}

>[!NOTE]
>The following example uses **We.Retail** as a demo project from where the Experience Fragment is leveraged from a **Sites** page to an AEM Screens project.

As an example, the following workflow demonstrates the use of experience fragments from We.Retail in Sites. You can choose a web page and leverage that content in your AEM Screens channel in one of your projects.

### Pre-requisites {#pre-requisites}

**Creating a Demo Project with a Channel**

***Creating a Project***

1. Click **Create Screens Project** to create a new project. 
1. Enter the Title as **DemoProject**.
1. Click **Save**.

A **DemoProject** will be added to your AEM Screens.

***Creating a Channel***

1. Navigate to the **DemoProject** you created and select the **Channels** folder.

1. Click **Create** from the action bar to open the wizard.
1. Choose the **Sequence Channel** template from the wizard and click **Next**.

1. Enter the **Title** as **TestChannel** and click **Create**.

A **TestChannel** will be added to your **DemoProject**.   
![screen_shot_2019-07-29at105101am](assets/screen_shot_2019-07-29at105101am.png)


### Creating an Experience Fragment {#creating-an-experience-fragment}

Follow the steps below to leverage the content from **We.Retail** to your **TestChannel** in **DemoProject**.

1. **Navigate to a Sites page in We.Retail**

    1. Navigate to Sites and select **We.Retail** -&gt; **United States** -&gt; **English** -&gt; **Equipment** and select this page to use this as an experience fragment for your Screens channel. 
    
    1. Click **Edit** from the action bar to open the page you want to use as an experience fragment for your Screens channel.

1. **Re-using the Content**

    1. Select the fragment you want to include in your channel.
    1. Click the last icon from the right to open the **Convert to experience fragment** dialog box.

   ![screen_shot_2019-07-29at105314am](assets/screen_shot_2019-07-29at105314am.png)

1. **Creating Experience fragment**

    1. Choose the **Action** as **Create a new Experience Fragment**.
    
    1. Select the **Parent path**.
    1. Select the **Template**. Choose the **Experience Fragment - Screens Variation** template here (value in the field `/libs/settings/screens/experience-fragments/templates/experience-fragment-template-screens`).  
    
    1. Enter the **Fragment Title** as **ScreensFragment**.
    
    1. Click the check mark to complete the creation of a new experience fragment.
   
   ![screen_shot_2019-07-29at105918am](assets/screen_shot_2019-07-29at105918am.png)

   Note: In order to select easier an option, click on the check mark on the right of the fields to open the selection dialog.

1. **Creating Live Copy of Experience Fragment**

    1. Navigate to the AEM home page.
    1. Select **Experience Fragments** and highlight the **ScreensFragment** and click **Variation as live-copy**, as shown in the figure below:

   ![screen_shot_2019-07-29at110443am](assets/screen_shot_2019-07-29at110443am.png)

   c. Select the **ScreensFragment** from **Create Live Copy** wizard and click **Next**.

   d. Enter the **Title** and **Name** as **Screens**.

   e. Click **Create** to create the Live Copy.

   f. Click **Done** to move back to **ScreensFragment** page.

   ![screen_shot_2019-07-29at110616am](assets/screen_shot_2019-07-29at110616am.png)

   >[!NOTE]
   >
   >Once you have created Screens fragment, you can edit the properties of your fragment. Select the fragment and click **Properties** from the action bar.

   **Editing Properties of a Screens Fragment**

    1. Navigate to the **ScreensFragment** (you created in the preceding steps) and click **Properties** from the action bar.
    
    1. Select the **Offline Config** tab, as shown in the figure below.

   You can add the **Client-side Libraries** (java and css) and **Static Files** to your experience fragment.  

   The following example shows the addition of client-side libraries and the fonts as a part of static files to your experience fragment.  ![fragment](assets/fragment.gif)

1. **Using Experience Fragment as a Component in Screens Channel**

    1. Navigate to the Screens channel where you want to use the **Screens** fragment.
    1. Select the **TestChannel** and click **Edit** from the action bar.
    
    1. Click the components icon from the side tab.  
    1. Drag and drop the **Experience Fragment** to your channel.

   ![screen_shot_2019-07-29at123115pm](assets/screen_shot_2019-07-29at123115pm.png)

   e. Select the **Experience Fragment** component and select the top left (wrench) icon to open the **Experience Fragment** dialog box.

   f. Select the **Screens** live copy of the fragment you created in *Step 3* in **Path**.

   ![screen_shot_2019-07-26at82650pm](assets/screen_shot_2019-07-26at82650pm.png)

   f. Select the **Screens** live copy of the fragment you created in *Step 3* in the **Experience Fragment**.

   ![screen_shot_2019-07-26at82509pm](assets/screen_shot_2019-07-26at82509pm.png)

   h. Enter the milliseconds in **Duration**.

   i. Select the **Offline Config** from the **Experience Fragments** dialog box to define the client-side libraries and the static files.

   >[!NOTE]
   >
   >If you want to add client-side libraries or the static files in addition to what you configured in step (4), you can add from the **Offline Config** tab in the **Experience Fragment** dialog box.

   ![screen_shot_2019-07-26at82844pm](assets/screen_shot_2019-07-26at82844pm.png)

   j. Click the check mark to complete the process.

### Validating the Result {#validating-the-result}

After completion of preceding steps, you can validate your experience fragment in **ChannelOne** by:

1. Navigating to the **TestChannel**.
1. Selecting the **Preview** from the action bar.

You will view the content from the **Sites** page (live-copy of the experience fragment) in your channel, as shown in the figure below:   
![screen_shot_2018-06-08at120739pm](assets/screen_shot_2018-06-08at120739pm.png) 

## Propagating Changes to the Page {#propagating-changes-from-the-master-page}

***Live Copy*** refers to the copy (of the source), maintained by synchronization actions as defined by the rollout configurations.

Since the Experience Fragment, we created is a live copy from the **Sites** pages, so if you make changes to that particular fragment from the master page, you will view the changes in your channel or the destination where you have used the Experience Fragment.

>[!NOTE]
>
>For more information on Live Copy, see Reusing Content: Multi Site Manager and Live Copy.

Follow the steps below to propagate changes from the master channel to your destination channel:

1. Select the Experience Fragment from the **Sites** (master) page and click the pencil icon to edit the items in the Experience Fragment.

   ![screen_shot_2018-06-08at122655pm](assets/screen_shot_2018-06-08at122655pm.png)

1. Select the Experience Fragment and click the wrench icon to open the dialog box to edit the images.

   ![screen_shot_2018-06-08at25031pm](assets/screen_shot_2018-06-08at25031pm.png)

1. The **Product Grid** dialog box opens.

   ![screen_shot_2018-06-08at25306pm](assets/screen_shot_2018-06-08at25306pm.png)

1. You can edit any of the images. For example, here the first image is replaced in this fragment.

   ![screen_shot_2018-06-08at25608pm](assets/screen_shot_2018-06-08at25608pm.png)

1. Select the Experience Fragment and click the Rollout icon to propagate changes to the fragment that is used in your channel.

   ![screen_shot_2018-06-08at31352pm](assets/screen_shot_2018-06-08at31352pm.png)

1. Click Rollout to confirm the changes.

   You will see that the changes are rolled out.

   ![screen_shot_2018-06-08at32148pm](assets/screen_shot_2018-06-08at32148pm.png)

### Validating the Changes {#validating-the-changes}

Follow the steps below to confirm the changes in your channel:

1. Navigate to the **Screens** -&gt; **Channels** -&gt; **TestChannel**.

1. Click **Preview** from the action bar to confirm the changes.

The following image illustrates the changes in your **TestChannel**:   
![screen_shot_2018-06-08at33351pm](assets/screen_shot_2018-06-08at33351pm.png)

