---
title: Managing Network Traffic
description: The page describes Standard Network Setups and how to manage network traffic.
---

# Managing Network Traffic {#managing-network-traffic}

A Network Setup can have various structures. This section describes the most usual network setups within an organization's network setup. 

This guide highlights an introduction to proxy servers followed by the varied network structures that are setup within different organizations. 

>[!NOTE]
>
>**AEM Screens Network Requirements**
>
>The AEM Screens communicates directly with the AEM as a Cloud Service, therefore there is a need to establish a stable connection between the two nodes. Firewalls are absolutely mandatory for commercial Internet access and as a customer you must understand which communication ports are required to be opened in firewalls and other IT-Security related network components.

## Overview to Proxy Servers {#proxy-servers}

An Internet connection relies on the usage of a Proxy Server. A Proxy Server is a dedicated computer or a software system running on a computer that acts as an intermediary between an endpoint device, such as a computer, and another server from which a user or client is requesting a service. The proxy server can exist in the same machine as a firewall server or it can be on a separate server, which forwards requests through the firewall.

An advantage of a proxy server is that it's cache can serve all users. If one or more Internet sites are frequently requested, these are likely to be in the proxy's cache, it improves user response time. A proxy can also log its interactions, which is used for troubleshooting.

## Understanding the Standard Network Setups {#network-setups}

To implement a network Setup, you must refer to the following scenarios with their strengths and deployment details. 

There are four major types of Network setups:

1. [Direct Internet Network (Wired/Wireless)](/help/using/direct-internet-network.md)
1. [Direct Mobile Network](/help/using/mobile-network.md)
1. [Mobile Network with Mobile Data Router and Active Network Components](/help/using/mobile-network-router.md)
1. [Enclosed Corporate Network (Wired/Wireless)](/help/using/enclosed-corporate-network.md)

The following table outlines the different types of network setups with advantages and disadvantages:

|Network Setup|Advantages|Disadvantages|
|--- |--- |--- |
|Direct Internet Network (Wired/Wireless)|Easy and straight forward to SetUp<br>Good choice for mid-size or larger Installations<br>Dedicated Network can be Encapsulated<br>Few Points of failure<br>Relatively Inexpensive<br>Good Scalability|Mandatory Internet Data Plan|
|Direct Mobile Network|Easy to SetUp<br>Good Choice for Mid-size or Larger Installations<br>Good Scalability<br>Encapsulated Screens|Mandatory Internet connection|
|Mobile Network with Mobile Data Router and Active Network Components|Easy to SetUp<br>Good Choice for Mid-size or Larger Installations<br>Dedicated Network can be Encapsulated<br>Few Points of Failure<br>Relatively Inexpensive<br>Good scalability|Mandatory Internet Data Plan|
|Enclosed Corporate Network (Wired/Wireless)|High flexibility and scalability<br>Highly Secure due to Different Lines of Defense<br>Encapsulated Networks<br>Easy to Monitor and Maintain<br>Reliable|Complicated and Expensive<br>Recommended for Network Specialists or System Integrators|
