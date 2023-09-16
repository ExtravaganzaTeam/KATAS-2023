# Title

Mobile UI domain

## Status

**accepted**

## Context

Separation of concerns is a principle used in programming to separate an application into units, with minimal overlapping between the functions of the individual units. The separation of concerns is achieved using modularization, encapsulation and arrangement in software layers.  

## Decision

The mobile ui domain was distinguished from the functional requirements for the application.  

Analyzing the functional requirements, we distinguished the following components included in the domain:  
* trip information viewer - is responsible for showing trips information to targeted person,  
* trip information connector - is responsible for receiving information about shared trips by traveler to targeted person,  
* notification viewer - is responsible for showing incomming notifications and allowing to select readed ones,  
* notification connector - is responsible for receiving notifications messages, and sending remove notification requests to server-side application,     
* trip dashboard viewer - is responsible for showing incomming and ongoing trips to traveler, and allowing trips sharing and updating,  
* trip dashboard connector - is responsible for receiving information about trips and sending trips update and trips sharing requests to server-side application,  
* scan sources viewer - is responsible for showing available sources to scan and allowing selection of preferred scan sources,  
* scan sources connector - is responsible for receiving information about available scan sources and sending selected scan source to update by server-side application,  
* preferred travel agency viewer - is responsible for providing preferred travel agency phone number,  
* preferred travel agency connector - is responsible for sending update requests about preferred travel agency phone number,  
* reports viewer - is resopnsible for showing reports metadata, and downloading generated end-of-year summary reports,  
* reports filtering configuration viewer - is resopnsible for showing reports filtering configuration and allowing its update,  
* reports connector - is responsible for receiving information about reports and sending report filtering criteria to update by server-side application,  
* mobile network connector - is responsible for calling preferred travel agency for help,  
* GPS data connector - is responsible for receiving GPS localisation data,  
* mobile BFF application - is responsible for listening on requests from mobile frontend applications.  

The domain consists of two independebly deployable applications. One is a mobile application and the other is server-side mobile BFF application component.  

The mobile application was divided into components that can be implemented independently by teams assigned to specific functionalities.  

The mobile BFF application should be managed by the same team implementing UI to speed up team work and not share responsibilities come from one domain between different teams (we don't want to synchronize work of multiple teams to provide simple functionality because it is not an efficient approach).  

## Consequences

The independently deployable component will need to be managed and orchestrated.  

### Resources:

#### Component diagram

![Dynamic diagram](https://github.com/ExtravaganzaTeam/KATAS-2023/blob/main/current/architecture/mobile_app_component.png "a title")  


[Go back](./README.md)