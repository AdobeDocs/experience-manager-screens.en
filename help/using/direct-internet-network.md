---
title: Direct Internet Access
description: Direct Internet Access
---

# Direct Internet Network (Wired/Wireless) {#direct-internet-access}

The Direct Internet Access SetUp contains an entry access point for internet access in order to reach the AEM Cloud services that AEM Screens needs to connect to. 

The standard Ports for AEM Screens communication are:
* `http (TCP Port 80)`
Or,
* `ssl-secured https (TCP Port 443)`

Ports may vary due to configuration of your dedicated AEM configuration set up. Within this SetUp, all devices are directly connected to your internet router as shown in the figure below.

![](/help/assets/direct-access-2.png)

The configuration also includes an Internet Access by any Internet Service Provider (ISP) and it’s Internet Line. Most ISP’s provide an Internet Router covering the Internet Modem, Network Switch, WIFI Access-point, Firewall and other Network functionalities (depending on manufacturer and model).

## Connecting AEM Screens Player to Direct Internet Access {#connecting-aem-screens-players}

Follow the steps below to connect of AEM Screen players in this configuration:

1. Make sure that each of the AEM Screen players is connected to the Routers Network.
1. Test the internet connection by calling an URL in your systems browser.

   >[!NOTE]
   >In case that you get an error message, check the network settings.There are basically two options for a proper network connection:
   >* DHCP
   >* Manual IP Configuration

1. Make sure that the Network Adapter Setting does match to your Router Setting and check if the Maximum amount of available IP addresses in your network is not reached.

1. Check if the Router is properly connected to the ISP Wide Area Network (Internet Link) This can usually also be identified using a Signal LED on Standard Routers.
1. In case that the URL call is successful, you can continue installing the AEM Screens and register it accordingly. Start AEM Screens.

   >[!NOTE]
   >**Troubleshooting Tip**
   >If AEM Screens does not connect properly and does not show the expected content:
   >
   >1. Check in your Internet Router Firewall if there are any restrictions regarding `TCP/IP Port 80/443`.
   >1. Make sure that all needed Ports are allowed.

## Requirements for Setting Up Direct Access Network {#requirements-direct}

The Direct Access Network Setup an be logically separated in two blocks:

* Wide Area Network

* Local Area Network

### Wide Area Network {#wan-connection}

The performance of the internet connection besides to the network reachability, is to provide sufficient bandwidth to operate AEM Screens nice and smoothly.

*Sufficient* depends on the amount of connected AEM screens and on the usage of other consumers within the network, such as Smartphones, Tablets, Cashiers, Computers or Guest WIFI networks.

>[!NOTE]
>All of the devices do have a concurrent access to the internet connection and bandwidth usually linearly decreases when you add more consumers/computers to the network.

### Local Area Network {#lan-connection}

The performance of the Local Area Network (LAN), besides the network reachability, provides sufficient bandwidth to operate AEM Screens nice and smoothly. 

The LAN network is usually at least matching a 100 MBit/sec network, so that there is sufficient bandwidth to connect many devices with good performance to the system.
In case that a WIFI solution is envisaged to connect AEM Screens to the internet Link it is recommended to use modern WIFI standards like IEEE 802.11g as a minimum. This standard supports connections up to 54 Mbps. Any *newer* Standards like 802.11h-n are of better quality. 

>[!NOTE]
>If a WIFI Repeater is required we do strongly recommend Mesh WIFI Access-point technologies like Google Nest Mesh WIFI or similar. Other WiFi repeating technologies ends up in a massive loss of bandwidth in the overall network.

## Downloading Media and Assets {#download}

AEM Screens provides a big advantage to Digital Signage Users. It downloads and locally saves all necessary media files, such as images and videos. Due to this concept the major network traffic occurs when there is new content to be displayed on a specific screen.
For normal operation, for example, having defined playlist that are not changing very often during the day, this offers a close to network independent operation, once all the files have been saved on the player.
For those use-cases where there are more interactions with sensors or other triggers and content is very dynamic a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible Customer Experience.

The following table provides an overview on network connectivity key data.

>[!NOTE]
>The information allows you to view the consumption of each device in the network requesting and downloading an internet source. Each of those requests add up and extend the Download Time.

![](/help/assets/download-times-direct.png)

