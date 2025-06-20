---
title: AEM Screens Project Roles and Responsibilities
description: Learn about AEM Screens project roles and responsibilities.
exl-id: 9377625b-529a-4b46-89d9-f526de398639
---
# Project Roles and Responsibilities {#roles-responsibilities}

As an experienced AEM implementor, you likely have seen the roles being referred to as *Authors*, *Developers*, and *IT Technicians*.

In a typical AEM Screens project, the roles are further refined as they each serve an important purpose in the project.

The following diagram shows the roles that you can expect to see throughout the guide.

![](/help/assets/project-roles-revised.png)

>[!NOTE]
>
> Many of these roles could be either in-house or outsourced, depending on how each project is set up.

## Defining Roles {#roles}

The following section provides an overview of the target audience:

### Adobe {#adobe-audience}

Adobe includes Adobe Managed Services resources like the CSE (Customer Success Engineer) and Adobe Support.

### AEM Implementors {#aem-implementors}

AEM Implementors are responsible for performing development and integration tasks to develop the user experience, custom templates, and back-end integrations for AEM.

Custom features required to address end-customer UX (User Experience) parameters are also captured and delivered through this process.

AEM Implementors will typically deploy custom functionality in phases over time to locations. For example, they might first establish support for playback of basic looped video or static graphic content. The next phase includes enabling the ability to support playback of localized content through dynamic templates and metadata tags. Other phases incorporate support for interactive elements by way of touch screens, sensors, dynamic triggers, and so on.

### Audio-Video Integrators {#av-integrators}

The Audio-Video Integrator is the Hardware Vendor-Partner. They are the party that deals with retail design and site preparation, including hardware acquisition, configuration, and deployment. It is typically a contracted third party who has access to a Network Operations Center (NOC). Often the Audio-Video Integrator is the project owner due to its continuous involvement post-launch.

An Audio-Video Integrator is responsible for conducting discovery with end-customers to define requirements, determining project scope to design, build, and effectively manage deployments around digital signage hardware.

>[!NOTE]
>
> You must have an Audio Video Integrator as part of your AEM Screens deployment.

#### Considering Hardware Partner {#selecting-hardware-partner}

It is crucial to click the right Hardware Partner. The following questions must be considered:

1. What are the terms of Service level agreement?

1. What is Global coverage?

1. Is it 24-hour support?

1. How are the devices managed?

1. What are the active monitoring and warning systems?

### Business Strategists {#business-strategist}

The Business Strategists represent the decision makers at the company. This role is heavily involved in the discovery and requirements stages and is the main driver of the project. 

They are the ones defining requirements and setting up KPI metrics. Business Strategy could be the following:

* Marketing or,
* Sales Manager Digital Strategy Manager Creatives / Content Management.

The Creatives and Content Management team work closely with the Strategy team and turn requirements into client experiences. They drive the overall UX design and curate contents that complements the brand.

The Creatives and Content Management could be the following:

* Creative Agency or,
* Brand Manager

### Project Managers {#project-managers}

Project Managers typically manage the entire deployment for your AEM Screens deployment. A project manager is the point person for the entire implementation of the designated project. They perform major responsibilities such as setting timelines and handling team needs. They also affect communications, addressing challenges, and ensuring that goals are met.

>[!NOTE]
>
>To learn in detail about different roles and responsibilities and the target audience for a digital signage project, visit **[Project Roles and Responsibilities](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/digital-signage-network/project-roles-responsibilities)**.


## Project Stages {#project-stages}

To support a successful digital signage deployment, it is customary to segment the project into three stages. These stages are commonly referred to as **Days**. They are not literal days but designations for each major stage of the project.

1. The first stage is referred to as *Day Zero*. This stage includes all pre-sales and discovery efforts that are required for defining the project scope.
1. The second stage, *Day One*, refers to all activities included in the deployment effort.
1. The third and final stage is *Day Two*. It refers to all ongoing operations and support elements as part of the total solution.

>[!NOTE]
>
>While this guide puts emphasis primarily on *Day One* and *Day Two*, attention to all three stages is necessary to run a successful digital signage project.
>
>To learn about project pre-production, project initiation, and project progression, watch a video on **[Project Management and Deployment](https://experienceleague.adobe.com/en/docs/experience-manager-screens/user-guide/digital-signage-network/project-management-and-deployment)**.

## RACI Chart {#raci-chart}

The following is a sample RACI chart using the role definitions.

>[!NOTE]
>
>You do not need to follow the chart exactly. Instead, it is intended to provide an example of common tasks and considerations in an AEM Screens project.

### RACI definitions {#raci-definitions}

* **Responsible**: Does the work to complete the task.

* **Accountable**: Delegates work and are the last party to review the task before it is completed.

* **Consulted**: Reviews the task or deliverable to provide input.

* **Informed**: Kept informed of progress on the task but is not involved in the details of the deliverable.

The following is a sample RACI chart using the role definitions and provides an example of common tasks and considerations in an AEM Screens project.

The following table summarizes the **Day Zero: Pre-sales Considerations**:

| **Phase** | **Audio-Video Integrator** |**AEM Implementor** | **Business Strategy** | **Content Management**|
|---|---|---|---|---|
| Team Formation and Vendor Selection | I |I | RA |  RA |
| Agreement on Roles and Responsibilities |  RA |  RA | RA |  RA |
| Alignment on Strategic Goals |  CI |  I | RA |  RA |
| Reporting Needs and ROI Identification |  I |  C | RA |  C |
| Site Visits and Hardware Requirements |  RA |  I | C |  C |
| Support Process Definition |  C |  I | RA |  I |
| Define Scope of Work and Project Plan |  RA |  RA | C |  C |

The following table summarizes the **Day One: Project Implementation (Application Design)**:

| **Phase** | **Audio-Video Integrator** |**AEM Implementor** | **Business Strategy** | **Content Management**|
|---|---|---|---|---|
| Agreement on Roles and Responsibilities | RA |RA | RA |  RA |
| Alignment on Project Plan and Schedule |  RA |  RA | C |  C |
| Evaluate Current Server Environments |  I |  RA | I |  I |
| UX Design Requirements |  I |  RA | C |  RA |
| Technical Requirements Validation |  I |  RA | RA |  C |
| Architecture Design |  I |  RA | I |  I |
| Validate Data Structure with UI Design |  I |  RA | C |  C |
| Application Development | RA |RA | RA |  RA |
| AEM Screens Project Setup |  I |  RA | C |  I |
| Analytics Implementation |  I |  RA | C |  - |
| Testing and Deployment |  RA |  C | RA |  I |
| Server Configuration |  I |  RA | I |  I |
| Content Update Plan |  I |  RA | C |  C |
| Plan for pilot to production transition |  RA |  RA | I |  I |
| Knowledge Transfer |  RA |  RA | I |  I |

The following table summarizes the **Day One: Project Implementation (Retail Readiness)**:

| **Phase** | **Audio-Video Integrator** |**AEM Implementor** | **Business Strategy** | **Content Management**|
|---|---|---|---|---|
| Hardware Ordering and Storage | RA |I | I |  I |
| Retail Onboarding Schedule |  I |  I | C |  RA |
| Staging User Acceptance Testing |  I |  C | RA |   |
| Hardware Bulk Configuration |  RA |  I | C |  I |
| Agreement on Post Launch Support |  RA |  C | RA |  C |

The following table summarizes the **Day One: Day One: Project Implementation (Hardware)**:

| **Phase** | **Audio-Video Integrator** |**AEM Implementor** | **Business Strategy** | **Content Management**|
|---|---|---|---|---|
| Agreement on Roles and Responsibilities | RA |  RA | RA | RA |
| Retail Design includes wiring operations | - |  - | - |  - |
| Player Hardware Selection | RAC |  - | - |  - |
| Device Management of primary  | RA |  I | - |  - |
| Device Ordering & Storing & Configuring | RA |  CI | I | - |
| Support Process Definition | RA |  I | RA |  C |

>[!NOTE]
>
>Roles change during Day Two (Post Launch Support).

* **Author**: Content Management + Strategy

* **Developer**: Typically a member of the AEM Screens implementation team, or handoff to an internal development team

* **Technician**: Either contracted by the Audio-Video Integrator or is part of the same company.

The following table summarizes the **Day Two: Post Launch Support RACI Chart**:

| **Phase** | **Author** |**Developer** | **Technician** |
|---|---|---|---|
| *Day Two: Post-Launch Support* |
| Agreement on Roles and Responsibilities |  RA |  RA | RA |
| Tier 1 Support |  I |  I | RA |
| Tier 2 Support |  I |  C | RA |
| Tier 3 Support |  I |  RA | C |
| Content Update |  RA |  I | I |
| Evaluate UX success and identify areas of improvement |  RA |  C | I |
