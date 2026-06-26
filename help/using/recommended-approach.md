---
title: Recommended Approach
description: Learn about the recommended approach in an AEM Screens project.
exl-id: 28aacffa-e9c9-4ccb-8038-720bb3e02a3f
TQID: https://experienceleague.adobe.com/r0WE0DQZx3dtGGlNaX9DUX3ckvu2ZdseJLy8-sDJZXQ
product_v2:
  - id: a27b4747-2f72-4fb7-9936-be5d11dd2c4a
    internal-label: Experience Manager Screens
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ae478996-b206-4712-9b0c-dc78a2644453
    internal-label: Integrations
  - id: f18e6c98-d21a-4444-b84b-f327ce464de4
    internal-label: Integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: fc314d1d-7cb9-4a38-8dbd-8f9b6478f40d
    internal-label: Content strategy
---
# Recommended Approach {#recommended-approach}

>[!IMPORTANT]
>This content is valid for AEM on-premise/AMS (AEM 6.5LTS and AEM 6.5). For AEM as a Cloud Service Screens content refer to the [AEM as a Cloud Service guide](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/screens-as-cloud-service/overview/introduction).

It is best practice to think of any enterprise-level AEM Screens project as a long-term undertaking. A project duration of one or more years is likely, particularly if the solution allows for complex user interaction or is deployed to various devices and locations.

## Guidelines for Developing a Digital Signage Strategy {#signage-strategy}

See the few recommendations before developing and deploying a digital signage project:

* **Scope Control**:
 If the desired solution is ambitious, it is recommended that you divide the deliverables into discrete phases to control the scope of the project.

* **Defined Use Cases**:
 Project phases should deliver tightly defined use-cases with clearly identified success criteria. 

* **Incremental Deliverables**:
 Focus on delivering features incrementally.

* **Estimating Desired Outcome**:
 Start with out-of-the-box AEM Screens features before building custom components and integrations. Always brainstorm if the desired outcome can be reached using the components and features that come standard with AEM Screens.

* **Defining Pilots, Rollouts, and POCs**:
 Develop a Proof of Concept (POCs) and adapt as needed through a pilot and rollout.

* **Pre-defining content strategy**:
 Establish a content strategy, including short-term and long-term goals. Also, align brand goals/KPIs with feature improvements.

  >[!NOTE]
  >
  > Upfront costs are often higher on an AEM Screens project because of the need to invest in hardware, fixtures, and site designs. Therefore, keeping initial content solutions simpler can help manage budget expectations.

* **Estimating Large-Scale Deliverables**:
 If the solution is delivered on a large scale, roll out the components of the application to carefully chosen pilot locations for trial use. Deliver to new locations and devices as the application passes validation.

  >[!NOTE]
  >
  > Start collecting analytics during the pilot so that business teams can validate the success of the solution against the specific metrics they are trying to achieve. Knowing how the pilot is performing helps the business team determine what improvements must be made.

* **Splitting Deliverables into measurable tasks**:
 Splitting the delivery of features into measurable tasks allows for feedback, provides more achievable targets, and reduces overall project risks. 

* **Developing a Roadmap**:
 If your client wants a feature-rich product, deliver a slice of the planned functionality early in the project and schedule other features for future phases. A feature-heavy first deliverable carries greater risk and is more difficult to validate with the client.

* **Understanding the Scope of Custom Integrations**:
 Interactive components with touch screen interaction, motion sensor, or RFID require significant custom development in the implementation method. A slideshow, video advertisement, or static menu can be delivered as graphical content or HTML on a Screens channel.

