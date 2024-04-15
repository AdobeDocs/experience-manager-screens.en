---
title: Offline Channels
description: Learn more about how AEM Screens player provides offline support for channels by using ContentSync technology.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
docset: aem65
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 5ad1046f-8b64-490b-9966-ce9008180d54
---
# Offline Channels {#offline-channels}

The Screens player provides offline support for the channels by using the ***ContentSync*** technology.

The players use a local http server to serve the unzipped content.

When a channel is configured to run *online*, the player serves the channel-resources by accessing the AEM server. However, when the channel is configured to run *offline*, the player serves the channel-resources from a local http server.

The workflow for the process is the following:

1. Parse the desired pages.
1. Collect all related assets.
1. Package everything in a zip file.
1. Download the zip and extract it locally.
1. Display local copy of the content.

## Update Handlers {#update-handlers}

The ***ContentSync*** uses update handlers to parse and collect all necessary pages and assets for a specific project. AEM Screens uses the following update handlers:

### Common Options {#common-options}

* *type*: the update handler type to use
* *path*: path to the resource
* *[targetRootDirectory]*: target folder in the zip file

<table>
 <tbody>
  <tr>
   <td><strong>Type</strong></td> 
   <td><strong>Description</strong></td> 
   <td><strong>Options</strong></td> 
  </tr>
  <tr>
   <td><code>channels</code></td> 
   <td>collects a channel</td> 
   <td>extension: extension of the resource to collect<br /> [pathSuffix='']: suffix to add to the channel path<br /> </td> 
  </tr>
  <tr>
   <td><code>clientlib</code></td> 
   <td>collect the specified client library</td> 
   <td>[extension='']: can be either css or js, to collect only the former, or only the latter</td> 
  </tr>
  <tr>
   <td><code>assetrenditions</code></td> 
   <td>collect the asset renditions</td> 
   <td>[renditions=[]]: list of renditions to collect. Defaults to the original rendition</td> 
  </tr>
  <tr>
   <td><code>copy</code></td> 
   <td>copy the specified structure from path</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

### Testing ContentSync Configuration {#testing-contentsync-configuration}

Follow the steps below to test the ContentSync configuration:

1. Open `https://localhost:4502/libs/cq/contentsync/content/console.html`
1. Select your config in the list
1. Select Clear Cache
1. Select Update Cache
1. Select Download Full
1. Extract the zip file
1. Start a local server in the extracted folder 
1. Open your start page and check your app status

## Enabling Offline Config for a Channel {#enabling-offline-config-for-a-channel}

Follow the steps below to enable offline config for a channel:

1. Inspect the channel content and check if it is requested from an AEM Instance (Online).

   ![chlimage_1-24](assets/chlimage_1-24.png)

1. Navigate to the channel dashboard.
1. Select **...** in the **CHANNEL INFORMATION** Panel.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Navigate to the channel properties.
1. Under the ((Channel)) tab, make sure that the checkbox is disabled, then select **Save & Close**.

   ![screen_shot_2017-12-19at122422pm](assets/screen_shot_2017-12-19at122422pm.png)

   Before content is properly deployed to the device, select the **Update Offline Content**.

   ![screen_shot_2017-12-19at122637pm](assets/screen_shot_2017-12-19at122637pm.png)

   The **Offline** status under **PROPERTIES** also updates accordingly.

   ![screen_shot_2017-12-19at124735pm](assets/screen_shot_2017-12-19at124735pm.png)

1. Inspect the channel content and check if it is requested from the local Player-Cache. 

   ![chlimage_1-26](assets/chlimage_1-26.png)

>[!NOTE]
>
>To learn more about the template for custom offline resource handlers and the minimum requirements in the `pom.xml` for that specific project, see [Template for Custom Handlers](/help/user-guide/developing-custom-component-tutorial-develop.md#custom-handlers) in **Developing a Custom Component for AEM Screens**.
