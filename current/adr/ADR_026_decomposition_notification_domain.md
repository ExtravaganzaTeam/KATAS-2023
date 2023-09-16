# Title

Notification domain

## Status

**accepted**

## Context

Separation of concerns is a principle used in programming to separate an application into units, with minimal overlapping between the functions of the individual units. The separation of concerns is achieved using modularization, encapsulation and arrangement in software layers.  

## Decision

The notification domain was distinguished from the functional requirements for the application.  

Analyzing the functional requirements, we distinguished the following components included in the domain:  
* notification automatic remover - is responsible for removing notification automaticly after configurable time e.g. 10 days. Notifications should be removed automatically when traveler did not receive them within the time specified in the configuration,
* travel change capture process - is responsible for storing and removing notifications when the specified events occured in system,  
* travel change notifier process - is responsible for instant notification about travel changes. It returns notifications after user application starts and reloads as well.  

All of the distinguished components operates on the same operational database which stores notifications.  

They are all grouped in one independently deployable unit but are ready to perform next decomposition after learning more about the business domain and performing first performance tests.  

Each of the recognised components can be separated and transferred to independently deployable component but we don't want to over-architect the solution up-front.  

## Consequences

The independently deployable component will need to be managed and orchestrated.  

### Resources:

#### Component diagram

![Dynamic diagram](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/notification_app_component.png "a title")  


[Go back](./README.md)