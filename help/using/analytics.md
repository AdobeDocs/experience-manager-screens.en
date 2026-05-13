---
title: Analytics with AEM Screens
description: Learn about Adobe Analytics with Adobe Experience Manager Screens.
exl-id: cfb47e94-9f65-43f3-b197-07222f3f6424
TQID: https://experienceleague.adobe.com/i7B7E5Kyno2U-ZTxEOPfhrr9W7fqYTWTV5vvcteRicY
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
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
