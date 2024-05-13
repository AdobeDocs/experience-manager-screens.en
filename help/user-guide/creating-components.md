---
title: Creating Components
description: Learn about how AEM components are used to hold, format, and render the content made available on your webpages.
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
topic-tags: developing
feature: Developing Screens
role: Developer
level: Intermediate
exl-id: 4d673039-4963-458a-89e9-023a993dd354
---
# Creating Components {#creating-components}

AEM components are used to hold, format, and render the content made available on your webpages.

>[!NOTE]
>
>To learn about the details of creating AEM components, see Developing AEM components.

## Authoring Channels {#authoring-channels}

The channel is the central object of content delivered to a set of displays. Therefore, a Content Author would typically open a channel in the editor to add or modify content. Because the Channel is a ***`cq:Page`***, it follows the same traditional UX pattern to add and change components on the channel.

However, because components within a channel are typically rendered full screen, the authoring experience suffers when trying to edit single components or compose new orders. Therefore, the channel relies on selectors to render different views of the components. The authoring environment uses the edit selector to activate the custom channel rendering.

For example, `http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html](http://localhost:4502/editor.html/content/screens/we-retail/channels/idle.edit.html`

The user does not have to take care of adding the selector to the URL while editing. A client-side logic is listening to the layer switch event and adds the selector if the channel has the dedicated resource type *screens/core/components/channel*.

## Rendering Components {#rendering-components}

To enable proper authoring, components must provide the following two renderings:

| **Component** |**Renditions** |
|---|---|
| *my-component/my-component.html* |production rendering |
| *my-component/edit.html* |editing rendering in a smaller view |

The built-in components use the following client library categories:

| **Component** |**Client Library** |
|---|---|
| *cq.screens.components.edit* |CSS and JS that has to be loaded during authoring |
| *cq.screens.components.production* |CSS and JS that has to be loaded when the channel is running |
| *cq.screens.components* |shared CSS and JS |

>[!NOTE]
>
>To develop custom components, use the ***[AEM Screens sample component template](https://github.com/Adobe-Marketing-Cloud/aem-screens-component-template)***.
