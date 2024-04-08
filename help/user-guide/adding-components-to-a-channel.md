---
title: Adding Components to a Channel
description: Learn more about adding components to channels in an AEM Screens project.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: 56dbe098-05db-4fc3-977f-e50a0a312d64
---
# Adding Components to a Channel{#adding-components-to-a-channel}

Components are the fundamental elements of the AEM (Adobe Experience Manager) experience. You can use several components and add it to your channel in an AEM Screens project.

## Components in AEM Screens {#components-in-aem-screens}

AEM Screens provide different AEM components that can be used in a Screens project.

### Viewing AEM Screens Components {#viewing-aem-screens-components}

Whenever you create an AEM Screens project, you see a list of default components that can be added to the project.

To view the default components to your Screens project, follow the steps below:

1. Select the channel. For example, **`We.Retail In Store`** > **Channels** > **Idle Channel**.

1. Select **Edit** from the action bar.
1. In the AEM Editor, select the **+** icon from the side bar.
1. All the components that are included by default in an AEM Screens project displays, as shown in the figure below.

![screen_shot_2017-12-18at21350pm](assets/screen_shot_2017-12-18at21350pm.png)

### Adding a New Component {#adding-a-new-component}

AEM provides several other components. You can always add other components (not included by default) to your project, given that those are compatible with AEM Screens.

The following example shows the addition of a Livefyre component to an AEM Screens project:

1. Select the channel where you want to add a component. For example, **`We.Retail In Store`** > **Channels** > **Idle Channel**.

1. Select **Edit** from the action bar.
1. Select **Design** mode.
1. Select the entire design editor on the right and select the settings symbol so you can open the **Parsys Design** dialog box.
1. You can select the components that you want to import to your AEM Screens project. The following example shows the addition of **Livefyre** component to an AEM Screens project.

![adding_components](assets/adding_components.gif)

>[!NOTE]
>
>Similarly, you can add any number of other new components that are compatible with AEM Screens to your project.

## Understanding AEM Screen Components {#understanding-aem-screen-components}

The following section explains the AEM Screens components that you can use in your project.

>[!NOTE]
>
>To view the properties of any component, select the component and select the hammer icon to open/view properties.

### Application {#application}

The **Application** component allows you to add an application to your channel.

Application component has the following properties:

| **Property** |**Description** |
|---|---|
| ***Application Path*** |Select the absolute path where the application exists. |
| ***Duration (milliseconds)*** |Select the duration of the application. By default, the duration is set to -1, that means the element runs forever (that is, single page application). Setting the duration value >0, shows the element for the specified duration and then moves on to the next one. |

The following example shows how to embed an application component along with the preview of its properties:

![adding_componentsapplication](assets/adding_componentsapplication.gif)

>[!NOTE]
>
>Refer to the example above to view properties of each of the components below.

### Channel {#channel}

The **Channel** component lets you add an entire channel to your project.

The Channel component has the following properties:

<table>
 <tbody>
  <tr>
   <td><strong>Property</strong></td>
   <td><strong>Description</strong></td>
  </tr>
  <tr>
   <td><strong><em>Channel Path</em></strong></td>
   <td>Select this absolute path where the application exists.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Duration (milliseconds)</em></strong></td>
   <td>Select the entire duration of the channel. Setting the duration as -1 indicates that the embedded channel runs its full length in a particular channel.</td>
  </tr>
 </tbody>
</table>

### Embedded Page {#embedded-page}

An **Embedded Page** allows you to add an embedded page to your project. For example, it can be a web application or a product catalog.

The Embedded page has the following properties:

<table>
 <tbody>
  <tr>
   <td><strong>Property</strong></td>
   <td><strong>Description</strong></td>
  </tr>
  <tr>
   <td><strong><em>Page Path<br /> </em></strong></td>
   <td>Select this absolute path where the channel exists.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Duration (milliseconds)</em></strong></td>
   <td>Select the entire duration of the channel. Setting the duration as -1 indicates that the embedded channel runs its full length in a particular channel.</td>
  </tr>
 </tbody>
</table>

### Embedded Sequence {#embedded-sequence}

>[!NOTE]
>
>To learn in detail about embedded sequences, see [Embedded Sequences](embedded-sequences.md) under Authoring Screens section.

An Embedded Sequence allows you to add an embedded sequence channel inside your existing channel (with other assets).

The Embedded Sequence has the following page properties:

<table>
 <tbody>
  <tr>
   <td><strong>Property</strong></td>
   <td><strong>Description</strong></td>
  </tr>
  <tr>
   <td>Channel Path</td>
   <td>Select the absolute path of the sequence that you want to include in your channel.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Duration (milliseconds)</em></strong></td>
   <td>Select the entire duration of the channel. Setting the duration as -1 indicates that the embedded channel runs its full length in a particular channel.</td>
  </tr>
  <tr>
   <td><strong><em>Strategy</em></strong></td>
   <td>Set it to <strong>original</strong> or <strong>single</strong>. Setting the value to <strong>original</strong> means that the subsequence runs fully on each cycle of the parent sequence. The other possible value is <strong>single</strong>. Such value only shows one item of the subsequence on each run. For example, the first item on the first loop, and the second item on the second loop.</td>
  </tr>
 </tbody>
</table>

### Dynamic Embedded Sequence {#dynamic-embedded-sequence}

A dynamic embedded sequence lets you add a sequence similar to the above mentioned except by channel role.

To learn about embedded sequences, see [Embedded Sequences](embedded-sequences.md) under Authoring Screens section.

The dynamic embedded sequence has the following properties:

<table>
 <tbody>
  <tr>
   <td><strong>Property</strong></td>
   <td><strong>Description</strong></td>
  </tr>
  <tr>
   <td><strong><em>Channel Assignment Role</em></strong><br /> </td>
   <td>Enter the channel role.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Duration (milliseconds)</em></strong></td>
   <td>Select the entire duration of the channel. Setting the duration as -1 indicates that the embedded channel runs its full length in a particular channel.</td>
  </tr>
  <tr>
   <td><strong><em>Strategy</em></strong></td>
   <td>Set it to <strong>original</strong> or <strong>single</strong>. Setting the value to <strong>original</strong> means that the subsequence runs fully on each cycle of the parent sequence. The other possible value is <strong>single</strong>. Such value would only show one item of the subsequence on each run. For example, the first item on the first loop, and the second item on the second loop.</td>
  </tr>
 </tbody>
</table>

### Experience Fragment {#experience-fragment}

An Experience Fragment lets you add an Experience Fragment (group of one or more components including content and layout that can be referenced within pages) to your AEM Screens channel. Drag and drop the component to AEM Editor and select the Experience Fragment.

To learn more about how to create an Experience Fragment and apply it to an AEM Screens project, see [Using Experience Fragments](experience-fragments-in-screens.md).

![exp](assets/exp.gif)

| **Property** |**Description** |
|---|---|
| **Experience Fragment** |
| ***Experience Fragment*** |Select the Experience Fragment. |
| ***Duration*** |Select the entire duration of the Experience Fragment that plays in the channel. |
| **Offline Config** |
| ***Client-side Libraries*** |JavaScript and CSS files. |
| ***Static Files*** |Static files that you can add as offline configs to your Experience Fragment. |

>[!NOTE]
>
>The **Client-side Libraries** and the **Static Files** that you add from this component are in addition to already configured **Client-side Libraries** and the Static Files that are added from the Experience Fragment's **Properties**.

### Image {#image}

An Image allows you to add an image to your channel.

The image asset has three tabs namely **Image**, **Accessibility**, and **Sequence**:

| **Property** |**Description** |
|---|---|
| **Image** |
| ***Image Asset*** |Select the image asset. |
| ***Title*** |Title of the image. |
| ***Link To*** |Add a link to the image. |
| ***Description*** |Brief description for the image. |
| ***Size*** |Size of the image. |
| **Accessibility** |
| ***Alternative Text*** |Alternative text to the image. |
| **Sequence** |
| ***Duration*** |By default the duration is set to *8000 milliseconds*. If you want to change the playback duration of the image, update the **Duration** field. |

### Transition {#transition}

The Transition component allows you to add a transition to your Screens project.

The following image shows the transition component (added via drag and drop) to the editor.

![screen_shot_2019-07-25at104237am](assets/screen_shot_2019-07-25at104237am.png)

Select the transition icon and select the **Configure** (wrench icon) to open the **Transition** dialog box. This dialog box includes three tabs:

* **Transition**
* **Sequence**
* **Activation**

>[!NOTE]
>
>By default, the sequence is set to 600 milliseconds. You can update the transition sequence to other values using the **Sequence** tab.

![transition](assets/transition.gif)

The transition component has the following properties:

<table>
 <tbody>
  <tr>
   <td><strong>Property</strong></td>
   <td><strong>Description</strong></td>
  </tr>
  <tr>
   <td><strong>Transition</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Type</em></strong></td>
   <td><p>The type of the transition between the element before and the one after. The transition <strong>Type</strong> includes the following options:</p>
    <ul>
     <li><strong>Normal</strong></li>
     <li><strong>Fade</strong></li>
     <li><strong>Slide in from Right</strong></li>
     <li><strong>Slide in from Left</strong></li>
     <li><strong>Slide in from Top</strong></li>
     <li><strong>Slide in from Bottom</strong></li>
    </ul> </td>
  </tr>
  <tr>
   <td><strong>Sequence</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Duration</em></strong></td>
   <td>Select the entire duration of the transition. By default, it is set to 600 milliseconds.</td>
  </tr>
  <tr>
   <td><strong>Activation</strong></td>
   <td></td>
  </tr>
  <tr>
   <td><strong><em>Active From</em></strong></td>
   <td>Timestamp that describes from when the transition can be active.<br /> </td>
  </tr>
  <tr>
   <td><strong><em>Active Until</em></strong></td>
   <td>Timestamp that describes until when the transition can be active.</td>
  </tr>
  <tr>
   <td><strong><em>Schedule</em></strong></td>
   <td>Add a pre-defined schedule.</td>
  </tr>
 </tbody>
</table>

### Video {#video}

The Video component allows you to add a video to your Screens project.

The video component has the following properties:

<table>
 <tbody>
  <tr>
   <td><strong>Property</strong></td>
   <td><strong>Description</strong></td>
  </tr>
  <tr>
   <td><em><strong>Video asset</strong></em></td>
   <td>Select the link to the video.</td>
  </tr>
  <tr>
   <td><em><strong>Duration</strong></em></td>
   <td>Select the duration of the video. By default, the duration is set to -1, that means the element runs forever. Setting the duration value >0, shows the element for the specified duration and then moves on to the next one.<br /> </td>
  </tr>
  <tr>
   <td><em><strong>Rendering</strong></em></td>
   <td><p>If the video aspect ratio does not fit the screen, you can adjust the rendering to either <strong>contain</strong> or <strong>cover</strong>.</p> <p><em>Contain</em> means that the full video is displayed and the missing areas are padded with a black border.</p> <p><em>Cover</em> means that the video covers the whole viewport, but some parts that overflow on the sides are hidden.</p> </td>
  </tr>
  <tr>
   <td><em><strong>Size</strong></em></td>
   <td>Size of the video.</td>
  </tr>
 </tbody>
</table>
