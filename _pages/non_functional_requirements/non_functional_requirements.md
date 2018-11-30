---
title: Non-Functional Requirements
toc: True
sidebar: overview_sidebar
permalink: non_functional_requirements.html
summary: "Details of non-functional requirements (NFRs) that describe system attributes such as security, reliability, maintainability, scalability, and usability"
---

## Security: Authentication, authorisation and access control
Provider systems SHALL resist unauthorized, accidental or unintended usage and provide access only to legitimate users. 

Please refer to the [Security guidance](security_guidance.html) page for technical details.
 
## Security: Encryption
Provider systems SHALL encrypted all data in transit

## Audit & provenance 
Provider systems SHALL audit all API access and actions. 
Please refer to the [cross organization audit and provenance](audit.html) page for technical details. 

## Scalability: Data Volumes
Provider systems MUST meet the agreed volumetric performance targets.  Please refer to the [Volumetric guidance](volumetric_guidance.html) page for technical details. 

## Performance: Response times 
Provider systems SHALL provide real time live waiting times every 5 minutes to ensure it presents real time activity.

## Monitoring
Provider systems SHALL automatically monitor the quality of the data feed and generate a notification whenever a change in the state of a component has occurred.

## Availability 
Provider systems SHALL meet the agreed availability targets (service time and/or hours and planned downtime) as defined in the [operational level agreement](ola.html) (OLA). 

## Recoverability 
Provider systems SHALL meet the agreed recoverability targets as documented in the [Operational Level Agreement](ola.html) (OLA). 

## Clinical Risk Management
Provider and consumer systems SHALL comply with NHS Digital [Clinical Risk Management Standards](https://digital.nhs.uk/services/solution-assurance/the-clinical-safety-team/clinical-risk-management-standards), in particular DCB0160.

## Data retention 
Provider systems SHALL retain data in line with existing relevant Informational Governance and data protection regulation. 

## Usability 
Provider and consumer systems SHOULD follow the [ISO 13407](https://www.iso.org/standard/21197.html) / [ISO 9241-210](https://www.iso.org/standard/52075.html) to explain a user-centred design process. 

## Accessibility 
Provider and consumer systems MUST maintain a compliance of minimum Double “A” of the WCAG 1.0 (or equivalent in WCAG 2.0) or, as stipulated by UK Government guidelines, for all user interfaces. Please see the [Web Accessibility Initiative](https://www.w3.org/WAI/) for more details. 

Please refer to the [UEC Technical Standards](https://developer.nhs.uk/apis/uec-tech-standards/index.htmlhttps://developer.nhs.uk/apis/uec-tech-standards/index.html) for details. 


 
