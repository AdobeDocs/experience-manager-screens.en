---
title: Mobile Network with Mobile Data Router and Active Network Components
description: The page describes Mobile Network with Mobile Data Router and Active Network Components
exl-id: a6b44a04-438d-49d4-ac98-32629c11dcdb
---
# Mobile Network with Mobile Data Router and Active Network Components {#mobile-network-setup}

Adobe AEM Screens Players can also be connected using mobile or cellular networks running at least a 3G network.

Within AEM Screens, the required content is physically downloaded to the player controller or computer and properly stored within the underlying Operating System. Therefore, the given bandwidth only impacts the initial download times and content updates, and does not influence the performance of regular playback of Displays.

The benefit of this setup is that the mobile router can be placed in an optimized spot to ensure the best available network coverage. This spot is usually in an elevated and open position, with as few surrounding concrete or metal structures as possible.
This setup gives AEM Screen users flexibility because there is no landline required to connect to AEM Screens. It is also interesting for ephemeral or mobile setups.

The following diagram shows the Mobile Network with Mobile Data Router and Active Network Components configuration. It contains an Internet access of any of the AEM Screens controllers by direct Internet access using an own 3/4/5G Data Link.

![](/help/using/assets/mobile-network-1.png)

## Connecting AEM Screens Player to Mobile Network with Mobile Data Router and Active Network Components {#connecting-aem-screens-players}

Follow the steps below to ensure proper connection of the AEM Screen players in this configuration:

The configuration allocates an Internet access for every AEM Screens Controller by direct Internet access using a dedicated 3/4/5G Data Link.

1. Make sure that the Mobile Data Router is properly connected to the Cellular Data Network as indicated within the Operating System. And, ensure that each of the AEM Screen players is connected to the Routers Network.
1. Test the Internet connection by calling a URL in your system's Browser.

   >[!NOTE]
   >In the case that you receive an error, check the network settings. There are basically two options for a proper network connection:
   >* DHCP
   >* Manual IP Configuration

1. Make sure that the Network Adapter Setting matches your Router Setting.

1. Check if the Router is properly connected to the Internet Service Provider's Wide Area Network (Internet Link). You can check using a Signal LED on Standard Routers.
1. In case the URL call is successful, you can continue installing the AEM Screens and register. Start AEM Screens.

   >[!TIP]
   >You may encounter that the AEM Screens connection is not working properly. The expected content is not displayed. In such cases, check your Internet Router firewall if there are any restrictions regarding `TCP/IP Port 80/443`.


## Setting Up Mobile Network with Mobile Data Router and Active Network Components {#requirements-direct}

The network Setup can be logically separated in two blocks:

* Mobile Internet Connection

* Local Area Network

### Mobile Internet Connection {#mobile-internet-connection}

The performance of the Internet connection, besides the already described network reachability, has to provide sufficient bandwidth to perform AEM Screens content downloads smoothly.

*Sufficient* depends on the number of connected AEM Screens devices. It also depends on the usage of other consumers within the network, such as Smartphones, Tablets, Cashiers, Computers, or Guest Wi-Fi networks.
Keep in mind that all the devices do have a concurrent access to the Internet connection and bandwidth is linearly decreasing while adding more consumers/computers to the network.
Besides the specific theoretical Network connection, it has to be ensured that the coverage of the mobile Router is at least *good*. Also, the underlying Monthly Plan has to cover enough Data Capacity and sufficient bandwidth to serve all connected clients within the connected LAN.

The following table highlights the data networks with their standard bandwidth:

|Data Network|Bandwidth|
|--- |--- |
|3G|42 Mbps|
|4G|150 Mbps|
|5G|1000 - 10000 Mbps|

While considering which Data Network should be used, Adobe recommends that you answer the following questions:

* How many clients are connected to the Router?
* How many Content Changes are expected and what are those average File Sizes?

>[!NOTE]
>
>The needed Data Package has to be at least:
>
>`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>
>For initial upload of Media Files while integrating new players, a higher amount of Data and an increased Download Time have to be expected. It is also reflected in the above assumptions. A 4G network with *good* coverage and unlimited Data should match the most common installations in this Network Setup.


### Local Area Network {#lan-connection}

The performance of the LAN, besides the already described network reachability, has to provide sufficient bandwidth to operate AEM Screens content downloads smoothly. In these days, the LAN network is usually at least matching a 100-Mbps network, so that there should be sufficient bandwidth to connect many devices with good performance to the system. While using other Active Network Components, it is mandatory that all of them match the network bandwidth requirements.

For example, the Network Components should at least match the 100 Mbps standard and match the bandwidth provided by the Internet Access/Router specification.

In case that a Wi-Fi solution is envisaged to connect screen to the Internet Link it is recommended to use modern Wi-Fi standards like IEEE `802.11g` as a minimum. This standard supports connections up to 54 Mbps. Any *newer* Standards like `802.11h-n` are of better quality. If a Wi-Fi Repeater is required, Adobe recommends Mesh Wi-Fi Access-point technologies like Google Nest Mesh Wi-Fi or similar.

## Downloading Media and Assets {#download}

AEM Screens provides a significant advantage to Digital Signage Users. It downloads and locally saves all necessary Media Files, such as Images and Video. Due to this concept, the major network traffic is occurring in the case that there is new content to be displayed on a specific screen.
For normal operation, having a defined playlist that is not updated frequently, it offers near network-independent operation when all the files are saved on the player.
For use cases where there are more interactions with Sensors or other Triggers and content is dynamic, a fast and reliable network connection is essential for an immediate screen reaction. It ensures the best possible Customer Experience.
The following tables offer a good overview of what network connectivity key data means for the performance that can be expected and potential waiting times.

>[!NOTE]
>
>All information refers to the consumption of each device in the network requesting and downloading an Internet source. Each of those requests adds up and extends the Download Time.

![](/help/using/assets/mobile-router-download.png)
