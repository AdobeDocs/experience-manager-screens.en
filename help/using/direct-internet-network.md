---
title: Direct Internet Access
description: Direct Internet Access
---

# Direct Internet Network (Wired/Wireless) {#direct-internet-access}

The Direct Internet Network contains an entry access point for Internet access in order to reach the AEM Cloud Services that AEM Screens needs to connect to. 

The standard Ports for AEM Screens communication are:
* `http (TCP Port 80)`
<br>Or,</br>

* `ssl-secured https (TCP Port 443)`

Ports may vary due to configuration of your dedicated AEM configuration set up. Within this SetUp, all devices are directly connected to your Internet router as shown in the figure below.

![](/help/assets/direct-access-2.png)

The configuration also includes an Internet access by any Internet Service Provider (ISP) and it’s Internet line. Most ISP’s provide an Internet Router covering the Internet Modem, Network Switch, WIFI access point, firewall and other Network functionalities (depending on manufacturer and model).

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

## Requirements for Setting Up Direct Access Network {#requirements-direct}

The Direct Internet Network is logically separated into two blocks:

* Wide Area Network 

* Local Area Network 

### Wide Area Network {#wan-connection}

The performance of the Internet connection besides the network's reachability is to provide sufficient bandwidth to operate AEM Screens.

*Sufficient* depends on the number of connected AEM screens and on the usage of other consumers within the network, such as smartphones, tablets, cashiers, computers or guest WIFI networks.

>[!NOTE]
>All of the devices mentioned above, have a concurrent access to the Internet connection and the bandwidth decreases linearly when you add more consumers or computers to the network.

### Local Area Network {#lan-connection}

The performance of the Local Area Network (LAN), besides the network's reachability provides sufficient bandwidth to operate AEM Screens. 

The LAN network usually at least matches a 100 Mbps network, so that there is sufficient bandwidth to connect many devices with good performance to the system.
In case that a WIFI solution is envisaged to connect AEM Screens to the Internet Link it is recommended to use modern WIFI standards like `IEEE 802.11g` as a minimum. This standard supports connections up to 54 Mbps. Any *newer* Standards like `802.11h-n` are of better quality. 

>[!NOTE]
>If a WIFI Repeater is required, it is strongly recommended a Mesh WIFI access point like Google Nest Mesh WIFI or similar. Other WiFi repeating technologies end up in a massive loss of bandwidth in the overall network.

## Downloading Media and Assets {#download}

AEM Screens provides a big advantage to Digital Signage Users. It downloads and locally saves all necessary media files, such as images and videos. The major network traffic occurs when there is new content to be displayed on a specific display.

For normal operations, for example, a defined playlist that updates frequently during the day - offers a close to network independent operation, once all the files have been saved on the player.

For scenarios, where there are more interactions with sensors or triggers and dynamic content, a fast and reliable network connection is essential for an immediate screen reaction to ensure best possible customer experience.

The following table provides an overview on network connectivity key data.

>[!NOTE]
>The information allows you to view the consumption of each device in the network requesting and downloading an Internet source. Each of those requests add up and extend the Download Time.

![](/help/assets/download-times-direct.png)

