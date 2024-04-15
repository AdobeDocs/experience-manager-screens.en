---
title: Security Checklist
description: Learn about the AEM Screens key security areas with a checklist of questions and considerations.
feature: Administering Screens
role: Admin
level: Intermediate
exl-id: 3d2835c8-d844-46fd-b35a-30feaced9dd8
---
# AEM Screens Security Checklist  {#security-checklist}

The AEM Screens Security Checklist page describes the key security areas with a checklist of questions and considerations.

## Checklist Table {#checklist-table}

| **Security Area** | **Checklist** |**Yes/No/NA**|
|---|---|---|
| **AEM and Screens Software updates** | **a.** *Has the latest Adobe Experience Manager (AEM) service pack been applied?* <br>**b.** *Has the latest AEM Screens Feature Pack been applied?* <br>**c.** *Are you using the latest available AEM Screens Player software from [AEM Screens Player Downloads](https://download.macromedia.com/screens/)?*|
| **Physical Security** | **a.** *Have you disabled all unnecessary ports?* <br>**b.** *Have you secured cabling and hardware?* <br>**c.** *Are you using any containers if applicable?*|
| **Network Security** | **a.** *Are you using an isolated subnet for your signage devices?* <br>**b.** *Does the isolated subnet allow access to the required endpoints including AEM, Adobe Analytics, or other required services?* <br>**c.** *Have you secured your Wi-Fi using enterprise best practices?* <br>**d.** *If using synchronized playback have you allowed TCP 24503 for WebSocket only on the primary devices?* <br>**e.** *Have you unblocked the range of IP addresses of the player devices so only authorized devices can access the registration service on the authoring instance?*|
| **Operating System Security** | **a.** *Have you upgraded to the latest version of the operating system and applied all necessary security patches?* <br>**b.** *Have you disabled all unnecessary services and removed unnecessary applications?* <br>**c.** *Have you enrolled the device into device management to enforce enterprise policies?* <br>**d.** *Have you locked down the device to single application (player) kiosk?* <br>**e.** *Do you have a Standard Operating Procedures (SOP) in place for installing OS security updates over time?*<br>**f.** *Have you followed the security best practices for the Operating System in use such as anti-malware software, non-administrative user?*|
| **Application Security** | **a.** *Have you disabled the Admin UI, Channel Switcher, and Activity UI for production?* <br>**b.** *Have you minimized the log level for production?* <br>**c.** *Are you using https for connecting to AEM?* <br>**d.** *Are you using a CA-signed certificate or an enterprise PKI? (not self-signed certificates)*<br>**e.** *Are you using TLS and not SSL v3?*<br>**f.** *Are you validating the registration token on device and AEM when registering?*<br> **g.** *Have you classified the data being used and that no PII or PHI exists on device?*<br> **h.** *Have you classified the data being used and that no Personally Identifiable Information (PII) or Protected Health Information (PHI) exists on device?*<br> **i.** *Have you configured monitoring E-mails, and do you have an SOP in place for responding to monitoring emails and handling non-pinging devices?*|
| **Access Control** | **a.** *Do you have a Role-Based Access Control (RBAC) identified and managed in-house?* <br>**b.** *Have you followed the principle of least privilege in providing access to authors, administrators, and players using best practices from Adobe?*|

### Downloading Security Checklist {#download-checklist}

To download the AEM Screens Security Checklist, select [here](/help/user-guide/assets/AEMScreens-SecurityChecklist.pdf).
