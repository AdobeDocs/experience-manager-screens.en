---
title: Mobile Network with Mobile Data Router and Active Network Components
description: The page describes Mobile Network with Mobile Data Router and Active Network Components
---

# Mobile Network with Mobile Data Router and Active Network Components {#mobile-network-setup}

Adobe AEM Screens Players can also be connected using Mobile or cellular networks running at least a 3G network.
Within the AEM Screens, the required content is physically downloaded to the player controller or computer and properly stored within the underlying Operating System. Therefore, the given bandwidth only impacts the initial download times and does not influence the Display Systems performance at all.

The Benefit of this Setup is that the Mobile Router can be placed in a optimized spot to ensure best available Network coverage. This is usually in an elevated and open position with as less surrounding concrete or metal construction as possible.
This SetUp allows AEM Screen Users a great flexibility as there is no landline required to connect AEM Screens.

![](/help/using/assets/mobile-network-1.png)

## Connecting AEM Screens Player to Mobile Network with Mobile Data Router and Active Network Components {#connecting-aem-screens-players}

Follow the steps below to connect of AEM Screen players in this configuration:

The configuration contains of an Internet Access of any of the AEM Screens Controllers by direct Internet Access using an own 3/4/5G Data Link.
The proper connection of the AEM Screen players in this configuration is simple:

1. Make sure that the Mobile Data Router is properly connected to the cellular Data Network as indicated within the Operating System and each of the AEM Screen players is connected to the Routers Network.
1. Test the internet connection by calling an URL in your systems Browser.
   >[!NOTE]
   >In case that you get an error message, check the network settings.There are basically two options for a proper network connection:
   >* DHCP
   >* Manual IP Configuration

1. Make sure that the Network Adapter Setting matches your Router Setting.

1. Check if the Router is properly connected to the ISP Wide Area Network (Internet Link) This can also be identified using a Signal LED on Standard Routers.
1. In case that the URL call was successful you can continue installing the AEM Screens and register it accordingly. Start AEM Screens.

   >[!NOTE]
   >**Troubleshooting Tip**
   >If AEM Screens does not connect properly and does not show the expected content:
   >
   >1. Check in your Internet Router Firewall if there are any restrictions regarding `TCP/IP Port 80/443`.
   >1. Make sure that all needed Ports are allowed.


## Requirements for Setting Up Mobile Network with Mobile Data Router and Active Network Components {#requirements-direct}

The network Setup can be logically separated in two blocks:

* Mobile Internet Connection

* Local Area Network

### Mobile Internet Connection {#mobile-internet-connection}

The performance of the Internet Connection has, besides to the already described network reachability, to provide sufficient bandwidth to operate AEM Screens nice and smoothly.

*Sufficient* depends on the amount of connected AEM screens and on the usage of other consumers within the network, such as Smartphones, Tablets, Cashiers, Computers or Guest WIFI networks.
Keep in mind that all of the devices do have a concurrent access to the Internet connection and bandwidth is usually linearly decreasing whilst adding more consumers/computers to the network.
Besides the specific theoretical Network connection it has to be ensured, that the coverage of the mobile Router is at least “good”. Also the underlying Monthly Plan has to cover enough Data Capacity and sufficient bandwidth to serve all connected clients within the connected LAN.
The Data networks provide standard bandwidth with:

**3G**
* 42 Mbps

**4G**
* 150 Mbps

**5G**
* 1000 Mbps-10000 Mbps

While considering which Data Network should be used it is recommended to answer the following questions:

* How many clients are connected to the Router?

* How many Content Changes are expected and what are those average File Sizes?

>[!NOTE]
>The needed Data Package has to be at least:
`Data Package Capacity = # of Clients * (# of Content Files * Average File Size)`

>[!IMPORTANT]
>For initial upload of Media Files, for example, while integrating new players, a higher amount of Data and an increased Download Time have to be expected and being reflected in the above assumptions. A 4G network with *good* coverage and unlimited Data should match the most common installations in this Network Setup.


### Local Area Network {#lan-connection}

The performance of the LAN has, besides to the already described network reachability, to provide sufficient bandwidth to operate AEM Screens nice and smoothly. In these days the LAN network is usually at least matching a 100 Mbps network, so that there should be sufficient bandwidth to connect many devices with good performance to the system. Whilst using other active Network Component it is mandatory that all of those do match to the network bandwidth requirements.

For example, the Network Components should at least match 100 Mbps standard and match the bandwidth provided by the Internet Access/Router specification.
In case that an WIFI solution is envisaged to connect screen to the Internet Link it is recommended to use modern WIFI standards like IEEE 802.11g as a minimum. This standard supports connections up to 54 Mbps. Any *newer* Standards like 802.11h-n are of better quality. If a WIFI Repeater is required we do strongly recommend Mesh WIFI Access-point technologies like Google Nest Mesh WIFI or similar.

## Downloading Media and Assets {#download}

AEM Screens provides a big advantage to Digital Signage Users. It downloads and locally saves all necessary Media Files, such as Images and Video. Due to this concept the major network traffic is occurring in case that there is new content to be displayed on a specific screen.
For normal operation, e.g. having defined playlist that aren’t changed very often during the day, this offers a close to network independent operation, once all the files have been saved on the player.
For those use-cases where there are more interactions with Sensors or other Triggers and content is very dynamic a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible Customer Experience.
The following tables offer a good overview what network connectivity key data means for the performance that can be expected and potential waiting times.

>[!NOTE]
>All information refers to the consumption of each device in the network requesting and downloading an internet source. Each of those requests add up and extend the Download Time.

![](/help/using/assets/mobile-router-download.png)



