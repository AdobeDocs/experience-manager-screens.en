---
title: Introduction to Standard Network Setups
seo-title: Introduction to Standard Network Setups
description: The page describes Standard Network Setups
seo-description: The page describes Standard Network Setups
---

# Managing Network Traffic {#managing-network-traffic}

A Network Setup can have various structures. This section provides an overview of the network structures deployed in an environment. There are different setups that are sometimes implemented from scratch.

This section highlights an introduction to proxy servers followed by the different network structures that are setup withing different organizations. 

>[!NOTE]
>**AEM Screens Network Requirements**
>The AEM Screens Communicates directly with the AEM Cloud Service, therefore there is a need to establish a stable connection between those two nodes. Firewalls are absolutely mandatory for commercial Internet Access and the Customer needs to know which Communication Ports need to be opened in Firewalls and other IT-Security related network components that are within control of the Customer.

## Proxy Servers {#proxy-servers}

A proxy server is a dedicated computer or a software system running on a computer that acts as an intermediary between an endpoint device, such as a computer, and another server from which a user or client is requesting a service. The proxy server can exist in the same machine as a firewall server or it can be on a separate server, which forwards requests through the firewall.

An advantage of a proxy server is that it's cache can serve all users. If one or more Internet sites are frequently requested, these are likely to be in the proxy's cache, which will improve user response time. A proxy can also log its interactions, which can be helpful for troubleshooting.

## Understanding the Standard Network Setups {#network-setups}

To implement a network Setup, you must refer to the following scenarios with strengths and deployment details. 

There are three major types of Network setups:

1. [Direct Internet Network (Wired/Wireless)](/help/using/direct-internet-network.md)
1. [Direct Mobile Network](/help/using/mobile-network.md)
1. [Mobile Network with Mobile Data Router and Active Network Components](/help/using/mobile-network-router.md)
1. [Enclosed Corporate Network (Wired/Wireless)](/help/using/enclosed-corporate-network.md)

The following table outlines the different types of network setups with advantages and disadvantages:

<table>
 <tbody>
  <tr>
   <td><strong>Network Setup</strong></td>
   <td><strong>Advantages</strong></td>
   <td><strong>Disadvantages</strong></td>
  </tr>
  <tr>
   <td><strong>Direct Internet Access</strong></td>
   <td>Easy and straight forward to SetUp
<br>Good choice for mid-size or larger Installations
<br>Dedicated Network can be encapsulated
<br>Few Points of failure
<br>Relatively Cheap
<br>Good scalability</td>
   <td>Appropriate Internet Data Plan mandatory</td>
  </tr>
    <tr>
   <td><strong>Direct Mobile Network</strong></td>
   <td>Easy and straight forward to SetUp
<br>Good choice for mid-size or larger installations
<br>Good scalability
<br>Encapsulated Screens
</td>
   <td>Appropriate Internet connection mandatory</td>
  </tr>
    <tr>
<tr>
   <td><strong>Mobile Network with Mobile Data Router and Active Network Components</strong></td>
   <td>Easy and straight forward to SetUp
<br>Good choice for mid-size or larger installations
<br>Dedicated Network can be encapsulated
<br>Few Points of failure
<br>Relatively Cheap
<br>Good scalability</br></td>
   <td>Appropriate Internet Data Plan mandatory</td>
  </tr>
    <tr>

   <td><strong>Enclosed Corporate Network</strong></td>
   <td>High flexibility and scalability
<br>Highly secure due to different Lines of Defense
<br>Encapsulated networks
<br>Easy to Monitor and Maintain
<br>Reliable</td>
   <td>Complicated and expensive
<br>Network specialists or System Integrator recommended</td>
  </tr>
  </tr>
 </tbody>
</table>


