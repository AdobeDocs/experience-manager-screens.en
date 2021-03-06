---
title: Testing and Quality Assurance
seo-title: Testing and Quality Assurance for AEM Screens
description: The page describes Testing and Quality Assurance for AEM Screens Best Practices Guide
seo-description: The page describes Testing and Quality Assurance for AEM Screens Best Practices Guide
exl-id: cc3bfb88-1341-43f8-b247-6a41f1d1a963
---
# Testing and Quality Assurance {#testing-quality}

>[!NOTE]
>Typical stakeholder for this activity is an A/V Integrator.

As we get closer to actual deployment of the digital signage network, we should create a Test and QA Plan that addresses every element of the network including all hardware components, all software components and all networking components.
In the phase, entire test systems should be built and fully tested.

A checklist should be created which identifies all the previously defined KPI's and measured the deliverable against them.

>[!NOTE]
>
>This phase should also be used as a tool for creating an install and user guide which can later be shipped with the equipment and kept on site for future reference.

The following elements should be considered:

## 1. Mechanical Considerations {#mechanical-considerations}

The following mechanical considerations are recommended:

* display mounting
* player mounting
* ventilation
* peripheral attachments
* cable management
* device networking

## 2. Software Considerations {#software-considerations}

The following software considerations are recommended:

* device registration
* media publishing
* playback
* database dependencies (previously defined)


## 3. Device Management Considerations {#device-management-considerations}

AEM Screens includes a Device Control Center module which allows for the management of Screens player application end points.
      
This refers to any *player* hardware device that has the Screens player application installed and is registered to an instance of AEM.
This module allows you to:

1. Monitor player application error logs
1. Manage remote screen shots
1. Manage content downloads
1. Manage application restart issues

To learn  in detail about ***Device Control Center***, refer to [Troubleshooting Device Control Center](https://helpx.adobe.com/experience-manager/6-5/screens/using/monitoring-screens.html) in **AEM Screens User Guide**.

>[!CAUTION]
>
> You should not use Device Control Center to:
> 1. Install new versions of the player application
> 1. Monitor system level resources
> 1. Troubleshoot system level errors
> 1. Allow for remote desktop intervention


>[!NOTE]
>
> Adobe recommends that dedicated, 3rd party Device Management platforms should be used for all deployments.

The specific platform chosen depends on a number of factors including the ***target operating system***, ***project requirements*** and ***number of end points***.
     
Few examples are:

* Google Chrome Device Management
* TeamViewer
* AirWatch
* 42Gears
* Proprietary AV Integrator Middleware
