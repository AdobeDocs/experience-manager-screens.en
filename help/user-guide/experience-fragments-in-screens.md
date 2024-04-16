---
title: Using Experience Fragments
description: Learn about using Experience Fragments in AEM Screens.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens, Experience Fragments
role: Admin, Developer
level: Intermediate
exl-id: 13c0d75e-435f-433e-8886-f451df863517
---
# Using Experience Fragments {#using-experience-fragments}

This page covers the following topics:

* **Overview**
* **Using Experience Fragments in AEM Screens**
* **Propagating Changes to the Page**

## Overview {#overview}

An ***Experience Fragment*** is a group of one or more components including content and layout that can be referenced within pages. Experience fragments can contain any component, such as one or multiple components that can contain anything within a paragraph system that is referenced into the complete experience or requested by a third endpoint.


## Using Experience Fragments in AEM Screens {#using-experience-fragments-in-aem-screens}

>[!NOTE]
>The following example uses **`We.Retail`** as a demo project from where the Experience Fragment is applied from a **Sites** page to an AEM Screens project.

As an example, the following workflow demonstrates the use of experience fragments from `We.Retail` in Sites. You can choose a web page and use that content in your AEM Screens channel in one of your projects.

### Pre-requisites {#pre-requisites}

**Creating a Demo Project with a Channel**

***Creating a Project***

1. To create a project, click **Create Screens Project**. 
1. Enter the Title as **DemoProject**.
1. Click **Save**.

A **DemoProject** is added to your AEM Screens.

***Creating a Channel***

1. Navigate to the **DemoProject** you created and click the **Channels** folder.

1. Click **Create** from the action bar so you can open the wizard.
1. Choose the **Sequence Channel** template from the wizard and click **Next**.

1. Enter the **Title** as **TestChannel** and click **Create**.

A **TestChannel** is added to your **DemoProject**.   
![screen_shot_2019-07-29at105101am](assets/screen_shot_2019-07-29at105101am.png)


### Creating an Experience Fragment {#creating-an-experience-fragment}

Follow the steps below to apply the content from **`We.Retail`** to your **TestChannel** in **DemoProject**.

1. **Navigate to a Sites page in We.Retail**

    1. Navigate to Sites and click **`We.Retail`** > **United States** > **English** > **Equipment** and click this page so you can use this as an Experience Fragment for your Screens channel. 
    
    1. Click **Edit** from the action bar so you can open the page you want to use as an Experience Fragment for your Screens channel.

1. **Reusing the Content**

    1. Click the fragment that you want to include in your channel.
    1. Click the last icon from the right so you can open the **Convert to Experience Fragment** dialog box.

   ![screen_shot_2019-07-29at105314am](assets/screen_shot_2019-07-29at105314am.png)

1. **Creating an Experience Fragment**

    1. Choose the **Action** as **Create a new Experience Fragment**.
    
    1. Click the **Parent path**.
    1. Click the **Template**. Choose the **Experience Fragment - Screens Variation** template here (value in the field `/libs/settings/screens/experience-fragments/templates/experience-fragment-template-screens`).  
    
    1. Enter the **Fragment Title** as **ScreensFragment**.
    
    1. To complete the creation of a new Experience Fragment, click the check mark.
   
   ![screen_shot_2019-07-29at105918am](assets/screen_shot_2019-07-29at105918am.png)

   Note: To click an easier option, click the check mark to the right of the field so you can open the selection dialog box.

1. **Creating Live Copy of Experience Fragment**

    1. Navigate to the AEM home page.
    1. Click **Experience Fragments** and highlight the **ScreensFragment** and click **Variation as live-copy**, as shown in the figure below:

   ![screen_shot_2019-07-29at110443am](assets/screen_shot_2019-07-29at110443am.png)

   c. Click the **ScreensFragment** from **Create Live Copy** wizard and click **Next**.

   d. Enter the **Title** and **Name** as **Screens**.

   e. Click **Create** so you can create the Live Copy.

   f. Click **Done** so you can  move back to **ScreensFragment** page.

   ![screen_shot_2019-07-29at110616am](assets/screen_shot_2019-07-29at110616am.png)

   >[!NOTE]
   >
   >After you have created an AEM Screens fragment, you can edit the properties of your fragment. Click the fragment and click **Properties** from the action bar.

   **Editing Properties of a Screens Fragment**

    1. Navigate to the **ScreensFragment** (you created in the preceding steps) and click **Properties** from the action bar.
    
    1. Click the **Offline Config** tab, as shown in the figure below.

   You can add the **Client-side Libraries** (Java&trade; and css) and **Static Files** to your Experience Fragment.  

   The following example shows the addition of client-side libraries and the fonts as a part of static files to your Experience Fragment.  ![fragment](assets/fragment.gif)

1. **Using Experience Fragment as a Component in Screens Channel**

    1. Navigate to the Screens channel where you want to use the **Screens** fragment.
    1. Click the **TestChannel** and click **Edit** from the action bar.
    
    1. Click the components icon from the side tab.  
    1. Drag and drop the **Experience Fragment** to your channel.

   ![screen_shot_2019-07-29at123115pm](assets/screen_shot_2019-07-29at123115pm.png)

   e. Click the **Experience Fragment** component and click the top left (wrench) icon so you can open the **Experience Fragment** dialog box.

   f. Click the **Screens** live copy of the fragment you created in *Step 3* in **Path**.

   ![screen_shot_2019-07-26at82650pm](assets/screen_shot_2019-07-26at82650pm.png)

   f. Click the **Screens** live copy of the fragment you created in *Step 3* in the **Experience Fragment**.

   ![screen_shot_2019-07-26at82509pm](assets/screen_shot_2019-07-26at82509pm.png)

   h. Enter the milliseconds in **Duration**.

   i. Click the **Offline Config** from the **Experience Fragments** dialog box so you can define the client-side libraries and the static files.

   >[!NOTE]
   >
   >To add client-side libraries, or the static files in addition to what you configured in step (4), you can add from the **Offline Config** tab in the **Experience Fragment** dialog box.

   ![screen_shot_2019-07-26at82844pm](assets/screen_shot_2019-07-26at82844pm.png)

   j. Click the check mark so you can complete the process.

### Validating the Result {#validating-the-result}

After completion of preceding steps, you can validate your Experience Fragment in **ChannelOne** by:

1. Navigating to the **TestChannel**.
1. Selecting the **Preview** from the action bar.

View the content from the **Sites** page (live-copy of the Experience Fragment) in your channel, as shown in the figure below:   
![screen_shot_2018-06-08at120739pm](assets/screen_shot_2018-06-08at120739pm.png) 

## Propagating Changes to the Page {#propagating-changes-from-the-master-page}

***Live Copy*** refers to the copy (of the source), maintained by synchronization actions as defined by the rollout configurations.

Because the Experience Fragment you created is a live copy from the **Sites** pages, and you change that particular fragment from the primary page, you view the changes in your channel. Or, view the destination where you have used the Experience Fragment.

>[!NOTE]
>
>For more information on Live Copy, see Reusing Content: Multisite Manager and Live Copy.

Follow the steps below to propagate changes from the primary channel to your destination channel:

1. Click the Experience Fragment from the **Sites** (primary) page and click the pencil icon so you can edit the items in the Experience Fragment.

   ![screen_shot_2018-06-08at122655pm](assets/screen_shot_2018-06-08at122655pm.png)

1. Click the Experience Fragment and click the wrench icon so you can open the dialog box to edit the images.

   ![screen_shot_2018-06-08at25031pm](assets/screen_shot_2018-06-08at25031pm.png)

1. The **Product Grid** dialog box opens.

   ![screen_shot_2018-06-08at25306pm](assets/screen_shot_2018-06-08at25306pm.png)

1. You can edit any of the images. For example, here the first image is replaced in this fragment.

   ![screen_shot_2018-06-08at25608pm](assets/screen_shot_2018-06-08at25608pm.png)

1. Click the Experience Fragment and click the Rollout icon so you can propagate changes to the fragment that is used in your channel.

   ![screen_shot_2018-06-08at31352pm](assets/screen_shot_2018-06-08at31352pm.png)

1. Click Rollout.

   Notice that the changes are rolled out.

   ![screen_shot_2018-06-08at32148pm](assets/screen_shot_2018-06-08at32148pm.png)

### Validating the Changes {#validating-the-changes}

Follow the steps below to confirm the changes in your channel:

1. Navigate to the **Screens** > **Channels** > **TestChannel**.

1. Click **Preview** from the action bar.

The following image illustrates the changes in your **TestChannel**:   
![screen_shot_2018-06-08at33351pm](assets/screen_shot_2018-06-08at33351pm.png)
