---
title: Testing and Quality Assurance
description: Learn about testing and quality assurance for AEM Screens in the Best Practices Guide.
exl-id: cc3bfb88-1341-43f8-b247-6a41f1d1a963
---
# Testing and Quality Assurance {#testing-quality}

>[!NOTE]
>Typical stakeholder for this activity is an A/V Integrator.

As you get closer to deployment of the digital signage network, create a Test and QA plan that addresses every element of the network including all hardware components, all software components, and all networking components.
In the phase, entire test systems should be built and fully tested.

A checklist should be created which identifies all the previously defined KPIs and measured the deliverables against them.

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
1. Manage remote screenshots
1. Manage content downloads
1. Manage application restart issues

To learn  in detail about ***Device Control Center***, refer to [Troubleshooting Device Control Center](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/troubleshooting/monitoring-screens) in **AEM Screens User Guide**.

>[!CAUTION]
>
>Do not use Device Control Center to:

> 1. Install new versions of the player application
> 1. Monitor system level resources
> 1. Troubleshoot system level errors
> 1. Allow for remote desktop intervention


>[!NOTE]
>
> Adobe recommends that dedicated, third-party Device Management platforms be used for all deployments.

The specific platform chosen depends on several factors including the ***target operating system***, ***project requirements***, and ***number of end points***.
     
A few examples are the following:

* Google Chrome Device Management
* TeamViewer
* AirWatch
* `42Gears`
* Proprietary AV Integrator Middleware
