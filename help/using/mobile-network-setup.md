---
title: Direct Mobile Network
description: The page describes Direct Mobile Network Setup
---

# Direct Mobile Network {#mobile-network-setup}

AEM Screens Players can also be connected using mobile or cellular networks running at least a 3G network.

Within the AEM Screens, the required content is physically downloaded to the player controller or Computer and properly stored within the underlying Operating System. Therefor the given bandwidth only impacts initial download times and does not influence the performance of Displays.

Connection of AEM Screens Players with a Cellular 3/4/5G Connect to your Mobile Service Data Provider. The benefit of this Setup is that the Mobile Router can be placed in a optimized spot to ensure best available Network coverage. This is usually in an elevated and open position with as less surrounding concrete or metal construction as possible.

This SetUp allows AEM Screen Users a great flexibility as there is no landline connection required to connect AEM Screens.

![](/help/using/assets/direct-mobile-1.png)

## Connecting AEM Screens Player to Direct Mobile Network {#connecting-aem-screens-players}

Follow the steps below to connect of AEM Screen players in this configuration:

1. Make sure that each of the AEM Screen players is connected to the Routers Network.

1. Test the internet connection by calling an URL in your systems browser.

   >[!NOTE]
   >In case that you get an error message, check the network settings.There are basically two options for a proper network connection:
   >* DHCP
   >* Manual IP Configuration

1. Make sure that the Network Adapter Setting does match to your Router Setting.
1. Check if the Router is properly connected to the ISP Wide Area Network (Internet Link) This can usually also be identified using a Signal LED on Standard Routers.
1. If all of the above is configured correctly and an error message is still appearing, check on your active network components like Switches or additional Routers if there is any Port restriction.
1. In case that the URL call was successful you can continue installing the AEM Screens and register it accordingly. Start AEM Screens.

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

The performance of the Internet Connection has, besides to the already described network reachability, to provide sufficient bandwidth to operate AEM Screens nice and smoothly. In detail, “sufficient” depends on the amount of connected AEM screens and on the usage of other consumers within the network, such as Smartphones, Tablets, Cashiers, Computers or Guest Wifi networks.
Keep in mind that all of the devices do have a concurrent access to the Internet connection and bandwidth is usually linearily decreasing whilst adding more consumers/computers to the network.
Besides the specific theoretical Network connection it has to be ensured, that the coverage of the mobile Router is at least “good” (please refer to your Mobile Router Manual). Also the underlying Monthly Plan has to cover enough Data Capacity and sufficient bandwidth to serve all connected clients within the connected LAN.
The Data networks provide standard bandwidth's having approx.. up to:
• 3G
o 42Mbit/sec
• 4G
o 150Mbit/sec
• 5G
o 1000Mbit/sec-10000Mbit/sec
While considering which Data Network should be used it is recommended to answer the following questions:
• How many clients are connected to the Router?
• How many Content Changes do I excpect and what are those average File Sizes?
As a follow up the needed Data Package has to be at least:
Data Package Capacity = # of Clients * (# of Content Files * Average File Size)
Please make sure that there is enough Buffer.
Attention: For initial upload of Media Files, e.g. while integrating new players, a higher amount of Data and an increased Download Time have to be expected and being reflected in the above assumptions.
As a thumb rule, a 4G network with “good” coverage and unlimited Data should match the most common installations in this Network Setup


### Local Area Network {#lan-connection}

The performance of the LAN has, besides to the already described network reachability, to provide sufficient Bandwith to operate AEM Screens nice and smoothly. In these days the LAN network is usually at least matching a 100MBit/sec network, so that there should be sufficient Bandwith to connect many devices with good performance to the system. Whilst using other active Network Component it is mandatory that all of those do match to the network bandwith requirements. E.g. the Network Components should at least match 100Mbit/s standard and match the Bandwith provided by the Internet Access/Router specification.

## Downloading Media and Assets {#download}

AEM Screens provides a big Advantage to Digital Signage Users. It is downloading and locally saving all necessary Media Files, such as Images and Video. Due to this concept the major network traffic is occurring in case that there is new content to be displayed on a specific screen.
For normal operation, e.g. having defined playlist that aren’t changed very often during the day, this offers a close to network independent operation, once all the files have been saved on the player.
For those use-cases where there are more interactions with Sensors or other Triggers and content is very dynamic a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible Customer Experience.
The following tables offer a good overview what network connectivity key data means for the performance that can be expected and potential waiting times.
All information has to bee seen as the consumption of each Device in the network requesting and downloading an internet source. So each of those request do add up and extend the Download Time.

![](/help/using/assets/download-times-mobile.png)



