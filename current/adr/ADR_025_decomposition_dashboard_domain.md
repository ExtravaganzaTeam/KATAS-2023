# Title

Dashboard domain

## Status

**accepted**

## Context

Separation of concerns is a principle used in programming to separate an application into units, with minimal overlapping between the functions of the individual units. The separation of concerns is achieved using modularization, encapsulation and arrangement in software layers.  

## Decision

The analytical domain was distinguished from the functional requirements for the application.  
It is organized around trips data processing.  

Analyzing the functional requirements, we distinguished the following components included in the domain:  
* travel update process - is responsible for updating travels data and marks travel points,  
* trip capture process - is responsible for capturing information about trips,  
* trip automatic remover process - is responsible for removing completed trips,  
* trip information publisher proces - is responsible for preparing and delivering trip shared information,  
* trip dashboard data provider process - is responsible for providing data to dashboard the traveler can see on his device or in web browser,  
* problem reporter process - is responsible for registering and managing preferred travel agency telephone number.  

All of the distinguished components operates on the same operational database which stores trips data and preferred travel agency telephone number in one, separate, database schema.

They are all grouped in one independently deployable unit but are ready to perform next decomposition after learning more about the business domain and performing first performance tests.  

Each of the recognised components can be separated and transferred to independently deployable component but we don't want to over-architect the solution up-front.  

## Consequences

The independently deployable component will need to be managed and orchestrated.  

### Resources:

#### Component diagram

![Dynamic diagram](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/dashboard_app_component.png "a title")  


[Go back](./README.md)