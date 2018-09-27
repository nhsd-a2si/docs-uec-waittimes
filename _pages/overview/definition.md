---
title: Definitions of Capacity and Demand
sidebar: overview_sidebar
permalink: definition.html
toc: false
---

### Definitions for Capacity and Demand

|Term             |Definition                                |
|-----------------|------------------------------------------|
| Live / real time information| This is not a technical definition (see *Non-functional Requirements* for response time requirements).<br><br> Whenever the word **live** is suffixed to an operational measure, for example **live wait time** or **real time demand**, it is meant to represent that the data item is real-time (or as close as possible to) from the point of view of the user receiving the information.  For this reason, in this project **live** and **real time** are defined using tolerances given by the users during research activities.<br><br> Live or real time, in this case **30 minutes** (or less), is measured from timestamp at source (the service where the patient is presenting) to when displayed or shared with patient.<br><br> **Live wait times are measured from source to patient**.
| Demand| The requirement for service, usually measured at the start of a clinical pathway and using signposting and referring services as a source.  For example, number of people calling NHS 111.|
| Capacity | Service availability to deliver care.  For example, number of appointment slots available on Mondays.|
|Delay | This is the basic concept underlying concept for **Wait Time**, **Delay in transfer of care**, **Handover time**, **Turnaround time**, etc.  It is also, by definition, a queue in the system.  See [Delayed transfers of care: a quick guide](https://www.kingsfund.org.uk/topics/measurement-and-performance/delayed-transfers-care-quick-guide).|
|Throughput | Number of patients attending a service (incoming flow) vs. number of patients leaving (i.e. being discharged) the same service.  Check definitions for [Patient Flow and Throughput]( https://scholar.google.co.uk/scholar?q=definition+of+patient+flow+and+throughput&hl=en&as_sdt=0&as_vis=1&oi=scholart&sa=X&ved=0ahUKEwjtnPCdjLPVAhVCbRQKHYt9B5IQgQMIJjAA).|
| Wait Time (Display)| It is a delay in receiving care viewed from the perspective of the patient.  It can be modelled as a pause in the patient journey (as no care is being received at this point).|
| Delay in transfer of care | Time measured from the perspective of the service delivering care, it is a delay in starting the handover process.  From the patient's perspective, the journey has not been interrupted.  See also **Handover time**.|
| Handover time | The time taken to complete the handover process.  The time lapsed between a service requesting the handover and the process actually taken place is referred to as a **Delay in transfer of care**. |
| Turnaround time | Time needed to make an ambulance available for the next episode of care. [Definition of this metric can be found here]( https://www.england.nhs.uk/statistics/wp-content/uploads/sites/2/2013/04/Daily-SitRep-Guidance-2013-14.doc).|
| Patient flow | Process-oriented view of the patient journey through the healthcare service. [Improving patient flow]( http://www.health.org.uk/sites/health/files/ImprovingPatientFlow_fullversion.pdf).<br><br>*The term ‘flow’ describes the progressive movement of people, equipment and information through a sequence of processes. In healthcare, the term generally denotes the flow of patients between staff, departments and organisations along a pathway of care*.|
| Patient journey | Person-oriented view of the pathway.  From the patient's perspective, the journey is defined by all the services involved in delivering care, in other words, the services forming the care pathway.|

                                   
