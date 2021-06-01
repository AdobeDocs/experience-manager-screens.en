---
title: Mobile Network with Mobile Data Router and Active Network Components
description: The page describes Mobile Network with Mobile Data Router and Active Network Components
---

# Mobile Network with Mobile Data Router and Active Network Components {#mobile-network-setup}

Adobe AEM Screens Players can also be connected using mobile or cellular networks running at least a 3G network.

Within AEM Screens, the required content is physically downloaded to the player controller or computer and properly stored within the underlying Operating System. Therefore, the given bandwidth only impacts the initial download times, as well as content updates, and does not influence the performance of regular playback of Displays.

The benefit of this setup is that the Mobile Router can be placed in a optimized spot to ensure best available network coverage. This is usually in an elevated and open position with as few surrounding concrete or metal construction as possible.
This setup allows AEM Screen users flexibility as there is no landline required to connect to AEM Screens. This is particularly interesting for ephemeral or mobile setups.

The following diagram shows the Mobile Network with Mobile Data Router and Active Network Components configuration and contains an Internet access of any of the AEM Screens controllers by direct Internet access using an own 3/4/5G Data Link.

![](/help/using/assets/mobile-network-1.png)

## Connecting AEM Screens Player to Mobile Network with Mobile Data Router and Active Network Components {#connecting-aem-screens-players}

Follow the steps below to ensure proper connection of the AEM Screen players in this configuration:

The configuration allocates an Internet Access for every AEM Screens Controller by direct Internet Access using a dedicated 3/4/5G Data Link.

1. Make sure that the Mobile Data Router is properly connected to the cellular Data Network as indicated within the Operating System and each of the AEM Screen players is connected to the Routers Network.
1. Test the internet connection by calling a URL in your systems Browser.
   >[!NOTE]
   >In case that you receive an error, check the network settings.There are basically two options for a proper network connection:
   >* DHCP
   >* Manual IP Configuration

1. Make sure that the Network Adapter Setting matches your Router Setting.

1. Check if the Router is properly connected to the ISP Wide Area Network (Internet Link) This can also be identified using a Signal LED on Standard Routers.
1. In case the URL call is successful, you can continue installing the AEM Screens and register. Start AEM Screens.

   >[!NOTE]
   >**Troubleshooting Tip**
   >If AEM Screens does not connect properly and the expected content is not displayed then check in your Internet Router firewall if there are any restrictions regarding `TCP/IP Port 80/443`.


## Setting Up Mobile Network with Mobile Data Router and Active Network Components {#requirements-direct}

The network Setup can be logically separated in two blocks:

* Mobile Internet Connection

* Local Area Network

### Mobile Internet Connection {#mobile-internet-connection}

The performance of the Internet connection, besides the already described network reachability, has to provide sufficient bandwidth to perform AEM Screens content downloads smoothly.

*Sufficient* depends on the amount of connected AEM screens devices and on the usage of other consumers within the network, such as Smartphones, Tablets, Cashiers, Computers or Guest Wi-Fi networks.
Keep in mind that all the devices do have a concurrent access to the Internet connection and bandwidth is usually linearly decreasing whilst adding more consumers/computers to the network.
Besides the specific theoretical Network connection, it has to be ensured that the coverage of the mobile Router is at least “good”. Also the underlying Monthly Plan has to cover enough Data Capacity and sufficient bandwidth to serve all connected clients within the connected LAN.

The following table highlights the ata networks with their standard bandwidth:

|Data Network|Bandwidth|
|--- |--- |
|3G|42 Mbps|
|4G|150 Mbps|
|5G|1000 - 10000 Mbps|

While considering which Data Network should be used it is recommended to answer the following questions:

* How many clients are connected to the Router?

* How many Content Changes are expected and what are those average File Sizes?

>[!NOTE]
>
>The needed Data Package has to be at least:
>
>`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>
>For initial upload of Media Files, for example, while integrating new players, a higher amount of Data and an increased Download Time have to be expected and being reflected in the above assumptions. A 4G network with *good* coverage and unlimited Data should match the most common installations in this Network Setup.


### Local Area Network {#lan-connection}

The performance of the LAN, besides the already described network reachability, has to provide sufficient bandwidth to operate AEM Screens content downloads smoothly. In these days the LAN network is usually at least matching a 100 Mbps network, so that there should be sufficient bandwidth to connect many devices with good performance to the system. While using other active network component it is mandatory that all of those do match to the network bandwidth requirements.

For example, the Network Components should at least match 100 Mbps standard and match the bandwidth provided by the Internet Access/Router specification.

In case that an Wi-Fi solution is envisaged to connect screen to the Internet Link it is recommended to use modern Wi-Fi standards like IEEE 802.11g as a minimum. This standard supports connections up to 54 Mbps. Any *newer* Standards like 802.11h-n are of better quality. If a Wi-Fi Repeater is required we do strongly recommend Mesh Wi-Fi Access-point technologies like Google Nest Mesh Wi-Fi or similar.

## Downloading Media and Assets {#download}

AEM Screens provides a big advantage to Digital Signage Users. It downloads and locally saves all necessary Media Files, such as Images and Video. Due to this concept the major network traffic is occurring in case that there is new content to be displayed on a specific screen.
For normal operation, for example, having defined playlist that is not updated frequently during the day, this offers a close to network independent operation, once all the files have been saved on the player.
For those use-cases where there are more interactions with Sensors or other Triggers and content is very dynamic a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible Customer Experience.
The following tables offer a good overview what network connectivity key data means for the performance that can be expected and potential waiting times.

>[!NOTE]
>
>All information refers to the consumption of each device in the network requesting and downloading an internet source. Each of those requests add up and extend the Download Time.

![](/help/using/assets/mobile-router-download.png)
