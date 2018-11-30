---
title: Capacity Service
toc: True
sidebar: overview_sidebar
permalink: capacity_service.html
---

## Workflow and Interactions
This section describes the interactions that happen as part of the capacity workflow.
Below is the Capacity Service Infrastructure:

<image src="images/functional/Cap_service_infrastructure.png"/>  



### The Actors

There are a number of different systems involved in the end to end capacity process. These fall into the following categories:
* Consumer System
* National Infrastructure (including capacity components and existing NHS D Components)
* 3rd Party Provider Systems

<image src="images/functional/components.png"/>  


### Consumer Systems

The consuming system belongs to the service that is searching for an appropriate service for the patient. The system will participate in discovery of the appropriate service and discovery of its capacity (for example, wait time).  There are many examples of services that could be fulfilling this role for example NHS 111 System, IUC Clinical Hub, Ambulance Trusts, A&E or even a GP Service.


### National Infrastructure

When the Consumer calls wait times of a service a number of systems that are hosted by NHS Digital as national infrastructure need to be interacted with. These are as follows:

**National DoS**
The national DoS can be used to discover the most appropriate service for the patient.

**DoS Proxy**
The DoS Proxy is essentially a proxy between existing DoS clients and the DoS system itself. Its purpose is to embellish the data returned from DoS. For the response that includes the recommendation for patient treatment, the DoS Proxy will try to add in waiting time data about the current capacity of the service being recommended from the Capacity Service.

**Capacity Service**
The Capacity Service is a cache of current capacity information. It offers a Rest API that allows the DoS Proxy (and other systems) to request the current capacity information for a service. It is this information (when available) that the DoS Proxy adds to the responses from the DoS system. The capacity service also allows other systems to set the current capacity information. Providers will also use this as an easy way to provide their capacity data. Ideally, a provider will use the Capacity Server API to push data in as timely a way as possible. The alternative is that the Capacity Service will have point to point integrations developed that will poll and pull data where possible. It is important to note that the capacity service has been developed to be independent of the DoS system, DoS Proxy etc. and exists as a standalone microservice.

**Capacity Info Reader**
Capacity information reader provides a platform around the individual jobs that will be developed for each provider. The platform includes a scheduler for starting jobs at appropriate times and access to the capacity server to set the current data

### 3rd Party Provider Systems
The provider system is the system that is collates, calculates and sends service wait times to the NHS Digital Capacity Info Reader.


## Data Validation

** Capacity Info Reader – Storing capacity information from multiple services **

This is used to collect and store wait time information to the Capacity Service with the following attributes:

|Attributes       |Value         |Mandatory (Y/N)|Validation          |
|-----------------|--------------|---------------| -------------------|
|serviceId | Identifier of the service |Yes |MUST match the DoS service identifier. Duplicate fields are rejected|
|waitingTimeMins| Waiting time in minutes |Yes| Wait time in minutes is mandatory (positive, null or zero).  MUST be supplied, cannot be blank. Also has to be 0 or above. Wait time has an upper limit of 24 hours.  Duplicate fields are rejected|
| lastUpdated| Date time representing a timestamp for when this wait time was recorded.| Yes| Last Updated is not in the future and is not more than 30 minutes old.  Duplicate fields are rejected|
|Number of people waiting| Numeric |No |Numeric number of people waiting field can be blank, but if provided MUST be >=0.  Duplicate fields are rejected. |


** Capacity Service - Retrieving capacity information for multiple services**

This is used to retrieve wait time information from to the DoS Proxy with the following validation rules:
* Validation results are returned to calling service with an appropriate response code
* Waiting times of zero minutes will not be returned to calling service
* Wait times that are over 30 minutes old are deemed redundant and are no longer returned by the Capacity Service.

** Waiting Time Calculation **

Waiting times are to be calculated at source by provider systems and meet the following minimum quality criteria (MQC).  This criterion will evolve as learnings are acquired during beta implementations.
* **Wait times have been measured from patient arrival to treatment** and not from arrival to assessment.  Pre-aggregated information items have to be calculated (for example, longest, average, etc. and what data items and values). Wait times for A&E is interpreted as wait time for treatment rather than wait times for initial assessment. There is a risk here if services are calculating wait time from arrival to initial assessment, this calculation is not representative of the service clinical throughput and it will not achieve the behavioural nudge as it may encourage patients to attend already stretched services and creates negative patient experience by undermining confidence in the accuracy of the wait time provided
* **Capacity data providers have to meet the definition of live wait time** - see Definitions for Demand and Capacity - Live wait times are measured from source to patient and its data items have to be timestamped at the source.

## Error Processing
Note: The content for this page is currently under development and will be published in due course.  

## User Privileges
Note: The content for this page is currently under development and will be published in due course.  

## Monitoring, Analysis and Reporting
Note: The content for this page is currently under development and will be published in due course.  
