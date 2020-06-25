---
title: Enclosed Corporate Network
description: Enclosed Corporate Network
---

# Enclosed Corporate Networks (Wired/Wireless) {#enclosed-corporate-networks}

The Enclosed Corporate Network SetUp is applicable to smaller, larger and enterprise Businesses. It can be theoretically more complex, but the logical Setup is shown in the figure below.

![](/help/using/assets/enclosed-network-1.png)


## Connecting AEM Screens Player to Direct Internet Access {#connecting-aem-screens-players}

Follow the steps below to ensure proper connection of the AEM Screen players in this configuration:

1. Make sure that each of the AEM Screen players is connected to the Routers Network.
1. Test the internet connection by calling an URL in your systems browser.

   >[!NOTE]
   >In case that you receive an error, check the network settings.There are basically two options for a proper network connection:
   >* DHCP
   >* Manual IP Configuration

1. Make sure that the Network Adapter Setting does match your Router Settings and check if the maximum amount of available IP addresses in your network is not reached.

1. Check if the Router is properly connected to the ISP Wide Area Network (Internet Link). This can also be identified using a Signal LED on Standard Routers.
1. In case the URL call is successful, you can continue installing the AEM Screens and register. Start AEM Screens.

   >[!NOTE]
   >**Troubleshooting Tip**
   >If AEM Screens does not connect properly and the expected content is not displayed:
   >
   >1. Check in your Internet Router firewall if there are any restrictions regarding `TCP/IP Port 80/443`.
   >1. Make sure that all required Ports are allowed.

## Requirements for Setting Up Enclosed Corporate Networks {#requirements-enclosed-networks}

The Enclosed Corporate Network Setup an be logically separated in two blocks:

* Wide Area Network (WAN) 
* Internal Local Area Network (LAN).

### Wide Area Network {#wan-connection}

The performance of the internet connection  besides the network reachability, is to provide sufficient bandwidth to operate AEM Screens nice and smoothly.
*Sufficient bandwidth* depends on the amount of connected AEM screens and on the usage of other consumers within the network, such as Smartphones, Tablets, Cashiers, Computers or Guest Wi-Fi networks.

>[!NOTE]
>All of the devices have a concurrent access to the internet connection and bandwidth is usually linearly decreases when you add more consumers or computers to the network.

### Local Area Network {#lan-connection}

The performance of the Local Area Network (LAN) has, besides the network reachability, is to provide sufficient bandwidth to operate AEM Screens nice and smoothly. 

In these days the LAN network within corporate organizations is usually at least matching a 1000 MBit/sec network, so that there should be sufficient bandwidth to connect many devices with good performance to the system. While using other active network Components it is mandatory that all of those do match to the network bandwidth requirements. 

For example,the network components should at least match 1000 Mbps standard and match the bandwidth provided by the Internet Access/Router specification.

### Other Corporate Networks Specifics {#other-networks}

Usually Corporate Networks have a load of devices connected, might be separated into various sub-networks and might have redundant or multiplexed Internet connections to provide sufficient performance for many thousand concurrent accesses.
This schema is simplified and fits in most cases to the environment available for the client.

In case that an Wi-Fi solution is envisaged to connect screen to the internet Link it is recommended to use modern Wi-Fi standards like `IEEE 802.11g` as a minimum. This standard supports connections up to 54 Mbps. Any *newer* Standards like `802.11h-n` are of better quality. If a Wi-Fi Repeater is required we do strongly recommend Mesh Wi-Fi Access-point technologies like Google Nest Mesh Wi-Fi or similar.
Other Wi-Fi repeating technologies ends up in a massive loss of bandwidth in the overall network.

## Downloading Media and Assets {#download}

AEM Screens provides a big Advantage to Digital Signage Users. It is downloading and locally saving all necessary Media Files, such as Images and Video. Due to this concept the major network traffic is occurring in case that there is new content to be displayed on a specific screen. 
For normal operation, e.g. having defined playlist that aren’t changed very often during the day, this offers a close to network independent operation, once all the files have been saved on the player. For those use-cases where there are more interactions with Sensors or other Triggers and content is very dynamic a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible Customer Experience. 

The following tables offer a good overview what network connectivity key data means for the performance that can be expected and potential waiting times.

>[!NOTE]
>All information has to bee seen as the consumption of each Device in the network requesting and downloading an internet source. Each of those requests add up and extend the Download Time.

![](/help/using/assets/enclosed-network-download.png)