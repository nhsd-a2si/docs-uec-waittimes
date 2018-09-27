---
title: Definitions of Capacity and Demand
sidebar: overview_sidebar
permalink: definition.html
toc: false
---

### Definitions for Capacity and Demand

|Term             |Definition                                |
|-----------------|------------------------------------------|
| Live / real time information| This is not a technical definition (see Non-functional Requirements for response time requirements). Whenever the word **live** is suffixed to an operational measure, for example **live wait time** or **real time demand**, it is meant to represent that the data item is real-time (or as close as possible to) from the point of view of the user receiving the information.  For this reason, in this project **live** and **real time** are defined using tolerances given by the users during research activities. Live or real time, in this case **30 minutes** (or less), is measured from timestamp at source (the service where the patient is presenting) to when displayed or shared with patient. **Live wait times are measured from source to patient**.
| Demand| The requirement for service, usually measured at the start of a clinical pathway and using signposting and referring services as a source.  For example, number of people calling NHS 111.|
| Capacity | Service availability to deliver care.  For example, number of appointment slots available on Mondays.|
|Delay | This is the basic concept underlying concept for **Wait Time**, **Delay in transfer of care**, **Handover time**, **Turnaround time**, etc.  It is also, by definition, a queue in the system.  See Delayed transfers of care: a quick guide.|
|Throughput | Number of patients attending a service (incoming flow) vs. number of patients leaving (i.e. being discharged) the same service.  Check definitions for Patient Flow and Throughput.|
| Wait Time (Display)| It is a delay in receiving care viewed from the perspective of the patient.  It can be modelled as a pause in the patient journey (as no care is being received at this point).  


                                   
