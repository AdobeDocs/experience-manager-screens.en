---
title: Mobile Network Setup
description: The page describes Mobile Network Setup
---

# Mobile Network Setups {#mobile-network-setup}

AEM Screens Players can also be connected using mobile or cellular networks running at least a 3G network.

Within the AEM Screens, the required content is physically downloaded to the Player Controller or Computer and properly stored within the underlying Operating System. Therefor the given bandwidth is only impacts initial download times and does not influence the performance of Displays.

Connection of AEM Screens Players with a Cellular 3/4/5G Connect to your Mobile Service Data Provider. The benefit of this Setup is that the Mobile Router can be placed in a optimized spot to ensure best available Network coverage. This is usually in an elevated and open position with as less surrounding concrete or metal construction as possible.

This SetUp allows AEM Screen Users a great flexibility as there is no landline connection required to connect AEM Screens.

![](/help/using/assets/mobile-network-1.png)

>[!NOTE]
>**Troubleshooting Tip**
>If AEM Screens does not connect properly and does not show the expected content:
>
>1. Check in your Internet Router Firewall if there are any restrictions regarding `TCP/IP Port 80/443`.
>1. Make sure that all needed Ports are allowed and retry.


## Requirements for Setting Up Mobile Network SetUp {#requirements-direct}

The network Setup as described in 5.5 can be logically separated in three block. The WAN/Outer World/Internet Connection Block(here mobile Data Connection), the internal LAN/Local Area Network and optional subsections of the LAN separated by Active Network Components.
To provide best possible performance it has to be ensured that both section do match to recommended minimum standards.
What does “good Performance” mean in the AEM Screens Environment?
AEM Screens provides a big Advantage to Digital Signage Users. It is downloading and locally saving all necessary Media Files, such as Images and Video. Due to this concept the major network traffic is occurring in case that there is new content to be displayed on a specific screen.
For normal operation, e.g. having defined playlist that aren’t changed very often during the day, this offers a close to network independent operation, once all the files have been saved on the player.
For those use-cases where there are more interactions with Sensors or other Triggers and content is very dynamic a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible Customer Experience.
The following tables offer a good overview what network connectivity key data means for the performance that can be expected and potential wayting times.
All information has to bee seen as the consumption of each Device in the network requesting and downloading an internet source. So each of those request do add up and extend the Download Time.


### WAN / Internet Connection {#wan-connection}

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


### LAN Connection {#lan-connection}

The performance of the LAN has, besides to the already described network reachability, to provide sufficient bandwidth to operate AEM Screens nice and smoothly. In these days the LAN network is usually at least matching a 100MBit/sec network, so that there should be sufficient bandwidth to connect many devices with good performance to the system. Whilst using other active Network Component it is mandatory that all of those do match to the network bandwidth requirements. E.g. the Network Components should at least match 100Mbit/s standard and match the bandwidth provided by the Internet Access/Router specification.
In case that an WiFI solution is envisaged to connect screen to the internet Link it is recommended to use modern WIFI standards like IEEE 802.11g as a minimum. This standard supports connections up to 54Mbit. Any “newer” Standards like 802.11h-n are of better quality. If a Wifi Repeater is required we do strongly recommend Mesh Wifi Access-point technologies like Google Nest Mesh Wifi or similar.
Other WiFi repeating technologies ends up in a massive loss of bandwidth in the overall network.
