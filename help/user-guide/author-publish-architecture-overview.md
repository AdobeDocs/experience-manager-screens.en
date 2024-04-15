---
title: Author and Publish Architectural Overview
description: AEM Screens architecture resembles a traditional AEM Sites architecture. Content is authored on an AEM author instance and then forward-replicated to multiple publish instances.
content-type: reference
topic-tags: administering
products: SG_EXPERIENCEMANAGER/6.5/SCREENS
docset: aem65
feature: Administering Screens
role: Admin, Developer
level: Intermediate
exl-id: ba23eb8e-bbde-4a6e-8cfb-ae98176ed890
---
# Author and Publish Architectural Overview {#author-and-publish-architectural-overview}

This page highlights the following topics:

* **Introduction to Publish Servers**
* **Architectural Overview**
* **Registration Process**

## Prerequisites {#prerequisites}

Before you begin with author servers and publish servers, you should have prior knowledge of:

* **AEM Topology**
* **Creating and Managing AEM Screens Project**
* **Device Registration Process**

>[!NOTE]
>
>This AEM Screens functionality is only available if you have installed AEM 6.4 Screens Feature Pack 2. To get access to this Feature Pack, you must contact Adobe Support and request access. After you have permission, download it from Package Share.

## Introduction {#introduction}

AEM Screens architecture resembles a traditional AEM Sites architecture. Content is authored on an AEM author instance and then forward-replicated to multiple publish instances. Devices on AEM Screens can now connect to an AEM publish farm via load balancer. Multiple AEM publish instances can be added to continue to scale the publish farm.

*For example*, an AEM Screens content author issues a command on the authoring system for a particular device. That device is configured to interact with a publish farm or an AEM Screens content author that obtains information about devices that are configured to interact with publish farms.

The following diagram illustrates both the author environment and the publishing environment.

![screen_shot_2019-03-04at30236pm](assets/screen_shot_2019-03-04at30236pm.png)

## Architectural Design {#architectural-design}

There are five architectural components facilitating this solution:

* ***Replicating content*** from author to publish for display by devices

* ***Reverse*** replicating binary content from the publishing environment (received from devices) to the authoring environment.
* ***Sending*** commands from author to publish via specific REST APIs.
* ***Messaging*** between publish instances to synchronize device information updates and commands.
* ***Polling*** by the author of publish instances to obtain device information via specific REST APIs.

### Replication (Forward) of Content and Configurations  {#replication-forward-of-content-and-configurations}

Standard replication agents are used to replicate AEM Screens channel content, location configurations, and device configurations. This allows authors to update the content of a channel and optionally go through some sort of approval workflow before publishing channel updates. A replication agent must be created for each publish instance in the publish farm.

The following diagram illustrates the replication process:

![screen_shot_2019-03-04at33935pm](assets/screen_shot_2019-03-04at33935pm.png)

>[!NOTE]
>
>A replication agent must be created for each publish instance in the publish farm.

### Screens Replication Agents and Commands  {#screens-replication-agents-and-commands}

Custom Screens specific replication agents are created to send commands from the Author instance to the AEM Screens device. The AEM Publish instances serve as an intermediary to forward these commands to the device.

This allows authors to continue to manage the device such as, send device updates and take screenshots from the author environment. The AEM Screens replication agents have a custom transport configuration, like standard replication agents.

### Messaging between Publish Instances  {#messaging-between-publish-instances}

Often a command is only meant to be sent to a device a single time. However, in a load-balanced publish architecture, it is unknown which publish instance the device is connecting to.

Therefore, the author instance sends the message to all Publish instances. However only a single message should then be relayed to the device. To ensure correct messaging, communication must take place between publish instances. This is achieved using *Apache ActiveMQ Artemis*. Each publish instance is placed in a loosely coupled Topology using Oak-based Sling discovery service and ActiveMQ is configured so that each publish instance can communicate and create a single message queue. The AEM Screens device polls the AEM publish farm by way of the load balancer and picks up the command from the top of the queue.

### Reverse Replication {#reverse-replication}

Often, following a command, some sort of response is expected from the Screens device to be forwarded to the Author instance. To achieve this AEM ***Reverse replication*** is used.

* Create a reverse replication agent for each publish instance, akin to the standard replication agents and the AEM Screens replication agents.
* A workflow launcher configuration listens for nodes modified on the AEM publish instance and in turn triggers a workflow to place the Device's response in the AEM publish instance's outbox.
* A reverse replication in this context is only used for binary data ( such as, log files and screenshots) provided by the devices. Non-binary data is retrieved by polling.
* Reverse replication poll from the AEM author instance retrieves the response and saves it to the author instance.

### Polling of Publish Instances  {#polling-of-publish-instances}

The author instance must be able to poll the devices to get a heartbeat and know the health status of a connected device.

Devices ping the load balancer and get routed to a publish instance. The status of the device is then exposed by the AEM publish instance through a Publish API served @ **api/screens-dcc/devices/static** for all active devices and **api/screens-dcc/devices/<device_id>/status.json** for a single device.

The author instance polls all publish instances and merges the device status responses into a single status. The scheduled job that polls on author is `com.adobe.cq.screens.impl.jobs.DistributedDevicesStatiUpdateJob` and can be configured based on a cron expression.

## Registration {#registration}

Registration continues to originate on the AEM author instance. AEM Screens Device is pointed to the author instance and registration is completed.

After a device is registered on the AEM author environment, the device configuration and channel/schedule assignments are replicated to the AEM publish instances. The AEM Screens Device configuration is then updated to point to the Load Balancer in front the AEM publish farm. This is intended to be a one-time setup. After the Screens Device is successfully connected to the publish environment, it can continue to receive commands originating from the author environment. There should be no need to ever connect the AEM Screens device to the AEM author environment directly.

![screen_shot_2019-02-25at15218pm](assets/screen_shot_2019-02-25at15218pm.png)

### The Next Steps {#the-next-steps}

When you understand the architectural design of author and publish setup in AEM Screens, see [Configuring Author and Publish for AEM Screens](author-and-publish.md) for more details.
