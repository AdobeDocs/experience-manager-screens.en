---
title: Analytics with AEM Screens
description: Learn about Adobe Analytics with Adobe Experience Manager Screens.
exl-id: cfb47e94-9f65-43f3-b197-07222f3f6424
---
# Analytics with AEM Screens {#analytics-screens}

>[!NOTE]
>
>Typical stakeholders for this activity are Marketing/Business Strategists.

AEM Screens can locally capture every trackable event that each player device runs. This data is locally stored until it can be uploaded to the cloud for processing. In addition to all the event data, a deviceID and timestamp are also added. This functionality ensures that data from one player is distinguishable from another player. And, data run at different times of the day can be evaluated separately, if desired.

There are two fundamental reasons that you may want to capture this data.

The first involves **feedback loops and machine learning** while the second involves the **creation of graphs, dashboards, and reports** that are intended for human consumption.

In the feedback loop use case, you do not need to be concerned with visual reports or dashboards but instead, you want to define rules that AEM can execute on for content modification. By consuming and processing all Screens player event data from a certain time period, you may define a rule that evaluates the effectiveness of image1 versus image2. By combining sales data with playback data, AEM may determine that image1 has a greater impact on sales and automatically instructs all players to use image1.

The second use case using analytics is to process playback events and usage data for human consumption by way of reports and dashboards.
You can use this data to create a Heat map of an interactive experience to determine the preferred journey map through the application. You can also choose to create a dashboard that provides a graphical interpretation of how many times consumers interact with the application.
