---
title: Managing Network Traffic
description: The page describes Standard Network Setups and how to manage network traffic.
exl-id: b6d8f4a3-fca2-4556-9455-b9e27b138154
---
# Managing Network Traffic {#managing-network-traffic}

A Network Setup can have various structures. This section describes the most usual network setups and generalized approaches followed within an Organization.

This guide highlights an introduction to proxy servers followed by the varied network structures that are set up within different organizations. 

>[!NOTE]
>**AEM Screens Network Requirements**
>AEM Screens communicates directly with the AEM as a Cloud Service, therefore it is required to establish a stable connection between the two nodes. Firewalls are mandatory for commercial Internet access. As a customer, understand which communication ports must be opened in these firewalls and other IT-Security-related network components.

## Overview to Proxy Servers {#proxy-servers}

An Internet connection relies on the usage of a proxy server. A proxy server is a dedicated computer or a software system running on a computer. It acts as an intermediary between an endpoint device, such as a computer, and another server from which a user or client is requesting a service. The proxy server can exist in the same machine as a firewall server or it can exist on a separate server, which forwards requests through the firewall.

An advantage of a proxy server is that its cache can serve all users. If one or more Internet sites are frequently requested, these sites are likely to be in the proxy's cache. Such caching further improves user response time. A proxy can also log its interactions, which can be used for troubleshooting.

When a proxy server receives a request for an Internet resource (such as a Web page or while connecting to an AEM Publisher), it scans its local cache of previously called urls. If it finds the page, it returns it to the user without forwarding the request to the Internet. If the page is not in the cache, the proxy server acts as a client on behalf of the user and requests the page from the server in the Internet. When the content is returned, the proxy server relates it to the original request and forwards it to the user.

## Understanding the Standard Network Setups {#network-setups}

To implement a Network Setup, see the following scenarios with their strengths and deployment details. 

This Guide highlights four different kinds of Network Setups within an Organization:

* **[Direct Internet Network (Wired/Wireless)](/help/using/direct-internet-network.md)**
* **[Direct Mobile Network](/help/using/mobile-network.md)**
* **[Mobile Network with Mobile Data Router and Active Network Components](/help/using/mobile-network-router.md)**
* **[Enclosed Corporate Network (Wired/Wireless)](/help/using/enclosed-corporate-network.md)**

The following table outlines the different types of network setups with advantages and disadvantages:

|Network Setup|Advantages|Disadvantages|
|--- |--- |--- |
|**Direct Internet Network (Wired/Wireless)**|Easy and straight forward to SetUp<br>Good choice for mid-size or larger Installations<br>Dedicated Network can be Encapsulated<br>Few Points of failure<br>Relatively Inexpensive<br>Good Scalability|Mandatory Internet Data Plan|
|**Direct Mobile Network**|Easy to SetUp<br>Good Choice for Mid-size or Larger Installations<br>Good Scalability<br>Encapsulated Screens|Mandatory Internet connection|
|**Mobile Network with Mobile Data Router and Active Network Components**|Easy to SetUp<br>Good Choice for Mid-size or Larger Installations<br>Dedicated Network can be Encapsulated<br>Few Points of Failure<br>Relatively Inexpensive<br>Good scalability|Mandatory Internet Data Plan|
|**Enclosed Corporate Network (Wired/Wireless)**|High flexibility and scalability<br>Highly Secure due to Different Lines of Defense<br>Encapsulated Networks<br>Easy to Monitor and Maintain<br>Reliable|Complicated and Expensive<br>Recommended for Network Specialists or System Integrators|
