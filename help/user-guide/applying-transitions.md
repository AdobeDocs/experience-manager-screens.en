---
title: Applying Transitions
description: Learn how to apply transitions to your AEM Screens projects.
contentOwner: jsyal
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 757e6751-8008-487f-be89-9f53ac898928
---
# Applying Transitions {#applying-transitions}

This section describes how you can apply the **Transition** component in-between different assets (images and videos) and embedded sequences in a channel.

>[!CAUTION]
>
>To learn in detail about the properties for the **Transition** component, see [Transitions](adding-components-to-a-channel.md#transition).

## Adding Transition Component to Assets in a Channel {#adding-transition}

Follow the steps below to add a transition component to your AEM Screens project:

>[!NOTE]
>
>**Prerequisites**
>
>Create an AEM Screens project **TestProject** with a channel **TestTransition**. Also, set up a location and a display to view the output.

1. Navigate to the Channel **TestTransition** and click **Edit** from the action bar.

   ![image1](assets/transitions1.png)

   >[!NOTE]
   >
   >The **TestTransition** channel already has a few assets (images and videos) in it. For example, the **TestTransition** channel includes three images and two videos, as shown below:
   
   ![image2](assets/transitions2.png)
   

1. Drag and drop the **Transition** component to your editor.

   >[!CAUTION]
   >
   >Before you add the transition to your assets in your channel, make sure you do not add the transition before the first asset in the sequential channel. The first item in your channel must be an asset and not a transition.

   ![image3](assets/transitions3.png)

   >[!NOTE]
   >
   >By default, the properties of the transition component such as **Type** is set to **Fade** and the **Duration** is set to *1600 milliseconds*. Also, it is not advisable to set a transition duration time that is longer than the asset it is being applied to.

1. Also, if you add an **Embedded Sequence** component (that includes a sequence channel) to this channel editor, you can add a transition component at the end. Doing so ensures that the content plays in the correct order, as seen in the following image:

   ![image3](assets/transitions5.png)
