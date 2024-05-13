---
title: Embedded Sequences
description: Learn about embedded sequences for channels that let you add components in the parent channel. Or, reuse the content from a different channel and embed it into the parent channel.
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: authoring
docset: aem65
feature: Authoring Screens
role: Admin, Developer
level: Intermediate
exl-id: cdfaee19-15d9-4bcb-bc85-0b43c59d88d2
---
# Embedded Sequences {#embedded-sequences}

Using ***Embedded Sequences***, for channels, lets a user add components in the parent channel and also to reuse the content from a different channel and embed it into the parent channel.

## Adding Embedded Sequences {#adding-embedded-sequences}

You have the option of adding the following components to your sequence channel:

* Embedded Sequence
* Dynamic Embedded Sequence

>[!NOTE]
>
>To learn about using other components in your Screens project, see [Adding Components to a Channel](adding-components-to-a-channel.md).

### Adding an Embedded Sequence {#adding-an-embedded-sequence}

You can add an embedded sequence to your channel. An embedded sequence is another channel that includes assets like images or videos. Adding an embedded sequence allows the user to add the sequence to a channel by ***Channel Path***.

>[!NOTE]
>***Channel Path*** defines an explicit reference to the channel.
>To learn more about *Channel Path*, see [Channel Assignment](channel-assignment.md) in Authoring Screens.

Follow the steps below to add an embedded sequence to your channel:

1. Click the channel where you want to embed a page. For example, **`We.Retail` In-Store** > **Channels** > **Idle Channel**.

1. Click **Edit** from the action bar.
1. In the editor mode, click the components icon from the left side bar so you can add the embedded page. Drag and drop the **Embedded Sequence** to the editor.
1. Double-click the **Embedded Sequence** component so you can add the channel to your original sequence channel.
1. Click the **Channel Path** of the channel.
1. Click the **Duration (milliseconds)** for your embedded channel in the **Sequence** tab. By default, the duration is set to **-1**, that means the embedded channel is fully run. If the user specifies a duration, then the subsequence is interrupted (that is, it cuts off) at the specified time.

1. Set the **Metered Playback Strategy** to **normal**.

By default, it is set to **normal**. Setting the value to **normal** (Play all items) means that the subsequence runs fully on each cycle of the parent sequence. The other possible value is **Play a single item**. That value only shows one item of the subsequence on each run. For example, the first item on the first loop, and the second item on the second loop.

>[!IMPORTANT]
>
>Assign the channel that is used in the embedded sequence to the same display.
>
>Follow the steps below after you have added an embedded sequence to your channel from the preceding steps:
>
>1. Navigate to the display and click the display from the **Locations** folder.
>1. Click **Dashboard** from the action bar.
>1. On the display dashboard, click **+ Assign Channels** from the **ASSIGNED CHANNELS & SCHEDULED PANELS** so you can open the **Channel Assignment dialog box**.
>
>1. Click the path of the channel that you used in the embedded sequence, in **Channel Path**.
>1. Make sure that the **Priority** is lower than the main channel.
>
>1. Do not click any **Supported Events**.
>1. Click **Save** when done.
>

The following example shows the addition of an embedded sequence (**Idle Channel - Night**) to an existing channel (**Idle Channel**).

![new2](assets/new2.gif)

### Adding a Dynamic Embedded Sequence {#adding-a-dynamic-embedded-sequence}

You can add a dynamic embedded sequence to your channel. A dynamic embedded sequence is similar to an embedded sequence but allows the user to follow a hierarchy where changes/updates made to one channel is propagated to other one in relation. It follows a parent-child hierarchy and also includes assets like images or videos. Adding a dynamic sequence allows the user to add a channel by Channel Role.

>[!NOTE]
>
>***Channel Role*** defines the context of the display.
>
>To learn more about *Channel Role*, see [Channel Assignment](channel-assignment.md) in Authoring Screens.

Follow the steps below to add an embedded sequence to your channel:

1. Click the channel where you want to embed a dynamic sequence. For example, **`We.Retail` In-Store** > **Channels** > **Idle Channel**.

1. Click **Edit** from the action bar.
1. In the editor mode, click the components icon from the left side bar so you can add the dynamic embedded sequence. Drag and drop the **Dynamic** **Embedded Sequence** to the editor.

1. Double-click the **Dynamic** **Embedded Sequence** component so you can add the page to your sequence channel.

1. Enter the **Channel Assignment Role**.
1. Set the **Metered Playback Strategy** to **normal**. By default, it is set to **normal**. Setting the value to **normal** (Play all items) means that the subsequence runs fully on each cycle of the parent sequence. The other possible value is **Play a single item**. That value only shows one item of the subsequence on each run. For example, the first item on the first loop, and the second item on the second loop.

1. Click the **Duration (milliseconds)** in the **Sequence** tab for your embedded channel in the sequence.

![latest](assets/latest.gif)
