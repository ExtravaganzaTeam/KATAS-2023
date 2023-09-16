# Title

Trip email source domain

## Status

**accepted**

## Context

Separation of concerns is a principle used in programming to separate an application into units, with minimal overlapping between the functions of the individual units. The separation of concerns is achieved using modularization, encapsulation and arrangement in software layers.  

## Decision

The trip email source domain was distinguished from the functional requirements for the application.  

Analyzing the functional requirements, we distinguished the following components included in the domain:  
* email receiver - is responsible for receiving travel-related emails forwarded by traveler and extracting usefull information from them,  
* email tracker - is responsible for tracking email messages and extracting usefull information from emails related to travels,  
* machine learning classification model - is responsible for classification email messages as a travel-related,  
* email register process - is responsible for registering or removing email addresses identified for tracking by the traveler.  

Email tracker and email register process components operate on the same operational database which stores emails addresses identified for tracking in one, separate, dedicated for the domain database schema.  

All distinguished domain components are grouped in one independently deployable unit but are ready to perform next decomposition after learning more about the business domain and performing first performance tests.  

Each of the recognised components can be separated and transferred to independently deployable component but we don't want to over-architect the solution up-front.  

## Consequences

The independently deployable component will need to be managed and orchestrated.  

### Resources:

#### Component diagram

![Dynamic diagram](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/trip_e-mail_source_app_component.png "a title")  


[Go back](./README.md)