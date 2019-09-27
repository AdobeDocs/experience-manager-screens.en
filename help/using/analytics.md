---
title: Anaytics with AEM Screens
seo-title: Anaytics with AEM Screens
description: The page describes Anaytics with AEM Screens
seo-description: The page describes the anaytics with AEM Screens
---

# Analytics with AEM Screens {#analytics-screens}

>[!NOTE]
>
>Typical stakeholders for this activity is a Marketing/Business Strategist.

AEM Screens offers the ability to locally capture every trackable event that each player device executes. This data will be locally stored until it can be uploaded to the cloud for processing. In addition to all the event data, a deviceID and timestamp are also added. This ensures that data from one player can be distinguished from another player and data executed at different times of the day can be evaluated separately if desired.

There are two fundamental reasons we may want to capture this data. 

The first involves **feedback loops and machine learning** while the second involves the **creation of graphs, dashboards and reports** that are intended for human consumption.

In the feedback loop use case, we are not concerned with visual reports or dashboards but instead, want to define rules that AEM can execute on for content modification. By consuming and processing all Screens player event data from a certain time period, we may define a rule that evaluates the effectiveness of image1 versus image2. By combining sales data with playback data, AEM may determine that image1 has a much greater impact on sales and automatically instructs all players to use image1.

The second use case using analytics is to process playback events and usage data for human consumption via reports and dashboards.
We may use this data to create a heatmap of an interactive experience to determine the preferred journey map through our application. We may also choose the create a dashboard that provides a graphical interpretation of how many times consumers interact with our application.

