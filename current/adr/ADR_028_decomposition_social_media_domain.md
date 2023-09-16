# Title

Social media domain

## Status

**accepted**

## Context

Separation of concerns is a principle used in programming to separate an application into units, with minimal overlapping between the functions of the individual units. The separation of concerns is achieved using modularization, encapsulation and arrangement in software layers.  

## Decision

The social media domain was distinguished from the functional requirements for the application.  

Analyzing the functional requirements, we distinguished the following components included in the domain:  
* social media process - is responsible for sharing trip information on social media,  
* facebook connector - is responsible for integration with Facebook interface,  
* instagram connector - is responsible for integration with Instagram interface.  

The distinguished components are grouped in one independently deployable unit but are ready to perform next decomposition after learning more about the business domain and performing first performance tests.  

Each of the recognised components can be separated and transferred to independently deployable component but we don't want to over-architect the solution up-front.  

## Consequences

The independently deployable component will need to be managed and orchestrated.  

### Resources:

#### Component diagram

![Dynamic diagram](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/social_media_publisher_app_component.png "a title")  


[Go back](./README.md)