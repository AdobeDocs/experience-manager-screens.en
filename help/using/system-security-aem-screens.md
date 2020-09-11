---
title: Security Checklist for AEM Screens
seo-title: Security Checklist for AEM Screens
description: The page describes Security Checklist for AEM Screens
seo-description: The page describes Security Checklist for AEM Screens
---

# System Security Considerations for AEM Screens {#security-checklist}

>[!IMPORTANT]
>This is an internal Git Resource.

This page highlights the System Security Considerations for AEM Screens.


## White Paper for AEM Screens Security {#white-paper}

This section describes the white paper. (Pending White Paper attachment)


## FAQs for AEM Screens Security {#faqs-screens}

The following FAQs assume an authenticated, registered player architecture using HTTPS as the communication protocol between player and AEM Server.

### FAQ 1 {#faq1}

Can player traffic be re-routed to a malicious server and instructed to download and play malicious media content?

**Answer**

It is not possible because the HTTPs connection identifies both ends of the connection and encrypts it. If you try to be in the middle and intercept it, you only see encrypted content, and if you try to impersonate the server, the player will refuse you because your certificate is different.

  
### FAQ 2 {#faq2}

Should I use HTTP or HTTPs?

**Answer**

Use HTTPs. This is a must-have if you are concerned about security. With HTTPs the communication is encrypted between player and server, and intercepting the content or modifying it will pretty much be impossible.


### FAQ 3 {#faq3}

On a content download, is there any sort of signing of the content or hash?

**Answer**

Every asset is signed (SHA) by the server and then validated by the player for the same hash to guarantee integrity.
If the hash does not match, we try to re-validate 3 times. After 3 attempts, we consider the download command to be invalid.


### FAQ 4 {#faq4}

Is AEM Server secure?

**Answer**

Ans 4. Assuming you are on AMS, we take care of all the server security using the same features as Sites or Assets.


### FAQ 5 {#faq5}

Is the Device secure?

**Answer**

A physically compromised player can theoretically be manipulated to play any content. You could also just plug the player out and plug in a USB/HDMI stick.

So it is recommended putting the devices out of reach, preferably in a secured container, with cabling secured as well. Also disable any IR-remote ports.

If device OS is not updated regularly, the OS may be left exposed to security holes and allow remote attacks over the network.

>[!NOTE]
>
>It is recommended to instrument the devices with decent remote update and control capabilities (remote desktop, MDM solution, etc.). It is also recommended to use a private network, not exposed to the public WIFI for instance.

  
### FAQ 6 {#faq6}

How would a hacker attempt to compromise a player?

**Answer**

The only way to compromise a player device is to:

1. compromise the DNS to impersonate the server on his hostname, and, 
1. compromise 
   1. the certificate server-side to impersonate the server 
   1. device and impersonate the certificate client-side

>[!IMPORTANT]
>Even if a device is compromised, you can still easily revoke it's credentials so that it cannot connect to AEM anymore.





