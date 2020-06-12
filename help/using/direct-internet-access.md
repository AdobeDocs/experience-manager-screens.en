---
title: Direct Internet Access
description: Direct Internet Access
---

# Direct Internet Access {#direct-internet-access}

The Direct Internet Access SetUp contains an entry access point for Internet access in order to reach the AEM Cloud services that AEM Screens needs to connect to. 

The standard Ports for AEM Screens communication are:
* `http (TCP Port 80)`
Or,
* `ssl-secured https (TCP Port 443)`

Ports may vary due to configuration of your dedicated AEM configuration. Within this SetUp, all devices are directly connected to your internet router as shown in the figure below.

![](/help/assets/direct-access-2.png)

The configuration also includes an Internet Access by any Internet service Provider and it’s Internet Line. Most ISP’s do provide an Internet Router covering the Internet Modem, Network Switch, WIFI Access-point, Firewall and other Network functionalities (depending on manufacturer and model).

>[!NOTE]
>**Troubleshooting Tip**
>If AEM Screens does not connect properly and shows the expected content:
>
>1. Check in your Internet Router Firewall if there are any restrictions regarding `TCP/IP Port 80/443`.
>1. Make sure that all needed Ports are allowed and retry.

## Requirements for Setting Up Direct Access Network {#requirements-direct}

The Direct Access Network Setup an be logically separated in two block. The WAN/Outer World/Internet Connection Block and the internal LAN/Local Area Network.

### WAN / Internet Connection {#wan-connection}

The performance of the Internet Connection has, besides to the already described network reachability, to provide sufficient bandwidth to operate AEM Screens nice and smoothly. In detail, “sufficient” depends on the amount of connected AEM screens and on the usage of other consumers within the network, such as Smartphones, Tablets, Cashiers, Computers or Guest WIFI networks.
Keep in mind that all of the devices do have a concurrent access to the Internet connection and bandwidth is usually linearly decreasing whilst adding more consumers/computers to the network.

### LAN Connection {#lan-connection}

The performance of the LAN has, besides to the already described network reachability, to provide sufficient bandwidth to operate AEM Screens nice and smoothly. In these days the LAN network is usually at least matching a 100MBit/sec network, so that there should be sufficient bandwidth to connect many devices with good performance to the system.
In case that an WIFI solution is envisaged to connect screen to the internet Link it is recommended to use modern WIFI standards like IEEE 802.11g as a minimum. This standard supports connections up to 54Mbit. Any *newer* Standards like 802.11h-n are of better quality. If a WIFI Repeater is required we do strongly recommend Mesh WIFI Access-point technologies like Google Nest Mesh WIFI or similar.
Other WiFi repeating technologies ends up in a massive loss of bandwidth in the overall network.

## Downloading Media and Assets {#download}

AEM Screens provides a big advantage to Digital Signage Users. It is downloading and locally saving all necessary media files, such as images and videos. Due to this concept the major network traffic is occurring in case that there is new content to be displayed on a specific screen.
For normal operation, for example, having defined playlist that are not changing very often during the day, this offers a close to network independent operation, once all the files have been saved on the player.
For those use-cases where there are more interactions with sensors or other triggers and content is very dynamic a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible Customer Experience.

The following table provides an overview on network connectivity key data:

![](/help/assets/direct-access-1.png)

>[!NOTE]
>The information allows you to view the consumption of each device in the network requesting and downloading an internet source. So each of those request do add up and extend the download Time.