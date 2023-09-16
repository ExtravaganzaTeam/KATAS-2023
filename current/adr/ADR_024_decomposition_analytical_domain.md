# Title

Analytical domain

## Status

**accepted**

## Context

Separation of concerns is a principle used in programming to separate an application into units, with minimal overlapping between the functions of the individual units. The separation of concerns is achieved using modularization, encapsulation and arrangement in software layers.  

## Decision

The analytical domain was distinguished from the functional requirements for the application.  
Analytical domain is different it its nature from operational tasks. Another approach and tools are required to reach its goals.  
The team working on these tools need to have unique skills.  
Processing analytical data is characterized by unique needs regarding the resources used.  

Analyzing the functional requirements, we distinguished the following components included in the domain:  
* analytical data capture process - is responsible for analytical data capture from trips,  
* report provider process - is responsible for reports filtering criteria storing and generated reports metadata providing,  
* report generator - is responsible for generating end-of-year summary reports,  
* analytical data provider process - is responsible for providing analytical data to external systems (the application's primary source of income).  

All of the distinguished components operates on the same analytical database which stores analytical data about trips and optional filtering report criteria for traveler.  

They are all grouped in one independently deployable unit but are ready to perform next decomposition after learning more about the business domain and performing first performance tests.  

Each of the recognised components can be separated and transferred to independently deployable component but we don't want to over-architect the solution up-front.  

## Consequences

The independently deployable component will need to be managed and orchestrated.  

### Resources:

#### Component diagram

![Dynamic diagram](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/analytical_app_component.png "a title")  


[Go back](./README.md)