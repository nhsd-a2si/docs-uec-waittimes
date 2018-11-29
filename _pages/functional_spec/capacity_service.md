---
title: Capacity Service
toc: True
sidebar: overview_sidebar
permalink: capacity_service.html
---

## Workflow and Interactions
This section describes the interactions that happen as part of the capacity workflow. 
Below is the Capacity Service Infrastructure:

<image src="images/overview/Cap_service_infrastructure.png"/>  



###The Actors

There are a number of different systems involved in the end to end capacity process. These fall into the following categories:
* Consumer System
* National Infrastructure (including capacity components and existing NHS D Components)
* 3rd Party Provider Systems

<image src="images/overview/components.png"/>  


###Consumer Systems

The consuming system belongs to the service that is searching for an appropriate service for the patient. The system will participate in discovery of the appropriate service and discovery of its capacity (for example, wait time).  There are many examples of services that could be fulfilling this role for example NHS 111 System, IUC Clinical Hub, Ambulance Trusts, A&E or even a GP Service.


### National Infrastructure

When the Consumer calls wait times of a service a number of systems that are hosted by NHS Digital as national infrastructure need to be interacted with. These are as follows:

…* **National DoS
…* The national DoS can be used to discover the most appropriate service for the patient.

…* **DoS Proxy**
…* The DoS Proxy is essentially a proxy between existing DoS clients and the DoS system itself. Its purpose is to embellish the data returned from DoS. For the response that includes the recommendation for patient treatment, the DoS Proxy will try to add in waiting time data about the current capacity of the service being recommended from the Capacity Service.

…* **Capacity Service**
…* The Capacity Service is a cache of current capacity information. It offers a Rest API that allows the DoS Proxy (and other systems) to request the current capacity information for a service. It is this information (when available) that the DoS Proxy adds to the responses from the DoS system. The capacity service also allows other systems to set the current capacity information. Providers will also use this as an easy way to provide their capacity data. Ideally, a provider will use the Capacity Server API to push data in as timely a way as possible. The alternative is that the Capacity Service will have point to point integrations developed that will poll and pull data where possible. It is important to note that the capacity service has been developed to be independent of the DoS system, DoS Proxy etc. and exists as a standalone microservice.

…* **Capacity Info Reader
…* Capacity information reader provides a platform around the individual jobs that will be developed for each provider. The platform includes a scheduler for starting jobs at appropriate times and access to the capacity server to set the current data
