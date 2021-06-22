---
title: Direct Mobile Network
description: The page describes Direct Mobile Network Setup
exl-id: 6775bd10-7625-422f-a7af-4f7b8793fa42
---
# Direct Mobile Network {#mobile-network-setup}

AEM Screens Players can also be connected using mobile or cellular networks running at least a 3G network.

Within AEM Screens, the required content is physically downloaded to the player controller or computer and properly stored within the underlying Operating System. Therefore, the given bandwidth only impacts initial download times, as well as content updates, and does not influence the performance of regular playback of Displays.

The benefit of connecting AEM Screens Players over Cellular 3/4/5G to your Mobile Service Data Provider is that the Mobile Router can be placed in a optimized spot to ensure best available network coverage. This is usually in an elevated and open position with as few surrounding concrete or metal construction as possible.

This setup allows AEM Screen users a great flexibility as there is no landline connection required to connect to AEM Screens. This is particularly interesting for ephemeral or mobile setups.

The following diagram shows the Direct Mobile Network Setup and consists of one singular network connection segment and the connection of each player to the mobile or cellular data Network.

![](/help/using/assets/direct-mobile-1.png)

## Connecting AEM Screens Player to Direct Mobile Network {#connecting-aem-screens-players}

Follow the steps below to ensure proper connection of the AEM Screen players in this configuration:

1. Make sure that each of the AEM Screen players is connected to the Router's Network.

1. Test the internet connection by calling an URL in your systems browser.

   >[!NOTE]
   >In case that you get an error message, check the network settings and cross-check if there is a sufficient network link and the Operating System firewall is configured to allow network access using the configured AEM Screens communication Ports.

1. In case that the URL call is successful you can continue installing the AEM Screens and register. Start AEM Screens.

## Setting Up Direct Mobile Network {#requirements-direct}

The network Setup can be logically separated in two blocks:

* Mobile Internet Connection

* Local Area Network

### Mobile Internet Connection {#mobile-internet-connection}

The performance of the Internet connection besides network reachability provides sufficient bandwidth to operate AEM Screens smoothly. 

In Direct Mobile Network, each Player is connected with a singular Mobile Data Card to the providers data Network.

The following table highlights the ata networks with their standard bandwidth:

|Data Network|Bandwidth|
|--- |--- |
|3G|42 Mbps|
|4G|150 Mbps|
|5G|1000 - 10000 Mbps|

While considering which Data Network should be used it is recommended to answer the following questions:

The available Network speed depends on the specific Mobile Data provider plan and with the available coverage that is reached at the location of the AEM Screens Controller.
While following this setup, it has also to be taken into consideration that besides the available bandwidth some Mobile Data Provider Plans limit the available amount of Data coming across the connecting within a specific period of time. It has to be ensured that there is enough capacity in amount of Data and bandwidth.
As a follow up the needed Data Package has to be at least:

`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`


>[!IMPORTANT]
>For initial upload of Media Files, e.g. while integrating new players, a higher amount of Data and an increased Download Time have to be expected and being reflected in the above assumptions. A 4G network with *good* coverage and *unlimited* data should match the most common installations in this Network Setup.

>[!NOTE]
>A minimum 3G plan with good network coverage should lead to acceptable download performance for an AEM Screens player. If there is only fair coverage available at a specific location it is to take into consideration to switch the overall Network Setup to [Mobile Network with Mobile Data Router and Active Network Components](/help/using/mobile-network-router.md).


### Local Area Network {#lan-connection}

The performance concerns of the Local Area Network (LAN), besides the network reachability, are to provide sufficient bandwidth to operate AEM Screens smoothly. The recommendation for the LAN network speeds is to start at 100 Mbps networks at least, so that there is sufficient bandwidth to connect many devices with good performance to the system. 

While using other active network components, it is mandatory that all of those do match to the network bandwidth requirements. For example, the network components should at least match 100 Mbps standard and match the bandwidth provided by the Internet access or Router specification. Otherwise the total bandwidth will be limited by the weakest link in the network chain.

## Downloading Media and Assets {#download}

AEM Screens provides a big advantage to Digital Signage Users. It downloads and locally saves all necessary media files, such as images and videos. The major network traffic occurs when there is new content to be displayed on a specific display.

For normal operations, for example, a defined playlist that updates frequently during the day - offers a close to network independent operation, once all the files have been saved on the player.

For scenarios, where there are more interactions with sensors or triggers and dynamic content, a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible customer experience.

The following table provides an overview on network connectivity key data.

>[!NOTE]
>
>All information refers to the consumption of each device in the network requesting and downloading an internet source. Each of those requests add up and extend the Download Time.

![](/help/using/assets/download-times-mobile.png)
