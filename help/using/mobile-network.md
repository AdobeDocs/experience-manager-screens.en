---
title: Direct Mobile Network
description: The page describes Direct Mobile Network Setup
---

# Direct Mobile Network {#mobile-network-setup}

AEM Screens Players can also be connected using mobile or cellular networks running at least a 3G network.

Within the AEM Screens, the required content is physically downloaded to the player controller or computer and properly stored within the underlying Operating System. Therefore, the given bandwidth only impacts initial download times and does not influence the performance of Displays.

Connection of AEM Screens Players with a Cellular 3/4/5G connect to your Mobile Service Data Provider. The benefit of this Setup is that the Mobile Router can be placed in a optimized spot to ensure best available network coverage. This is usually in an elevated and open position with as optimum surrounding concrete or metal construction as possible.

This SetUp allows AEM Screen users a great flexibility as there is no landline connection required to connect to AEM Screens.

The following diagram shows the Direct Mobile Network Setup and consists of one singular network connection segment, the connection of each player to the mobile/cellular data network.

![](/help/using/assets/direct-mobile-1.png)

## Connecting AEM Screens Player to Direct Mobile Network {#connecting-aem-screens-players}

Follow the steps below to connect AEM Screens players in this configuration:

1. Make sure that each of the AEM Screen players is connected to the Routers Network.

1. Test the internet connection by calling an URL in your systems browser.

   >[!NOTE]
   >In case that you get an error message, check the network settings.There are basically two options for a proper network connection:
   >* DHCP
   >* Manual IP Configuration

1. Make sure that the Network Adapter Setting match to your Router setting.

1. Check if the Router is properly connected to the ISP Wide Area Network (Internet Link) This can also be identified using a Signal LED on Standard Routers.

1. In case that the URL call is successful you can continue installing the AEM Screens and register. Start AEM Screens.

   >[!NOTE]
   >**Troubleshooting Tip**
   >If AEM Screens does not connect properly and does not show the expected content:
   >
   >1. Check in your Internet Router Firewall if there are any restrictions regarding `TCP/IP Port 80/443`.
   >1. Make sure that all needed Ports are allowed.


## Requirements for Setting Up Mobile Network SetUp {#requirements-direct}

The network Setup can be logically separated in two blocks:

* Mobile Internet Connection

* Local Area Network

### Mobile Internet Connection {#mobile-internet-connection}

The performance of the Internet Connection besides network reachability provides sufficient bandwidth to operate AEM Screens smoothly. 

*Sufficient* depends on the amount of connected AEM screens and on the usage of other consumers within the network, such as Smartphones, Tablets, Cashiers, Computers or Guest WIFI networks.

>[!NOTE]
>All of the devices have a concurrent access to the Internet connection and bandwidth linearly decreases while adding more consumers or computers to the network.

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
>Make sure that there is enough Buffer.
>For initial upload of Media Files, e.g. while integrating new players, a higher amount of Data and an increased Download Time have to be expected and being reflected in the above assumptions.A 4G network with *good* coverage and *unlimited* data should match the most common installations in this Network Setup.


### Local Area Network {#lan-connection}

The performance of the Local Area Network (LAN) besides the network reachability, is to provide sufficient bandwidth to operate AEM Screens smoothly. The LAN network is usually at least matches a 100 Mbps network, so that there should be sufficient bandwidth to connect many devices with good performance to the system. 

While using other active network components, it is mandatory that all of those do match to the network bandwidth requirements. For example, the network components should at least match 100 Mbps standard and match the bandwidth provided by the Internet Access/Router specification.

## Downloading Media and Assets {#download}

AEM Screens provides a big advantage to Digital Signage Users. It downloads and locally saves all necessary media files, such as images and videos. Due to this, major network traffic occurs in case there is new content to be displayed on a specific screen.
For normal operation, for instance, a defined playlist that is not frequently updated during the day, offers a close to network independent operation, once all the files have been saved on the player.
For those use-cases where there are more interactions with Sensors or other Triggers and content is very dynamic a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible Customer Experience.

The following table provides an overview of network connectivity key data responsible for the performance that can be expected and potential waiting times.

>[!NOTE]
>All information refers to the consumption of each device in the network requesting and downloading an internet source. Each of those requests add up and extend the Download Time.

![](/help/using/assets/download-times-mobile.png)



