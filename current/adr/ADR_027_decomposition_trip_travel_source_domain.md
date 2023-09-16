# Title

Trip travel source domain

## Status

**accepted**

## Context

Separation of concerns is a principle used in programming to separate an application into units, with minimal overlapping between the functions of the individual units. The separation of concerns is achieved using modularization, encapsulation and arrangement in software layers.  

## Decision

The trip travel source domain was distinguished from the functional requirements for the application.  

Analyzing the functional requirements, we distinguished the following components included in the domain:  
* travel system process - is responsible for processing requests and responses from external travel systems with which the application is to integrate,  
* SABRE connector - is responsible for integration with SABRE system interface,  
* APOLLO connector - is responsible for integration with APOLLO system interface,  
* travel agency connector - is responsible for integration with the agency's existing airline, hotel, and car rental system interface.  

The adopted solution makes it easier to attach new data sources and remove existing ones by adding a new or removing an existing connector component.  

Only the travel system process component operates on operational database to store travel systems sources to be scanned for traveler. The domain has its own database schema.  

The domain components are all grouped in one independently deployable unit but are ready to perform next decomposition after learning more about the business domain and performing first performance tests.  

Each of the recognised components can be separated and transferred to independently deployable component but we don't want to over-architect the solution up-front.  

## Consequences

The independently deployable component will need to be managed and orchestrated.  

### Resources:

#### Component diagram

![Dynamic diagram](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/trip_travel_source_connector_app_component.png "a title")  


[Go back](./README.md)