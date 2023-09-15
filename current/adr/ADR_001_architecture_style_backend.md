# Title

Architecture style for backend application

## Status

**accepted**

## Context

A new startup wants to build the next generation online trip management dashboard to allow travellers to see all of their existing reservations organized by trip either online (web) or through their mobile device.  

There are many challenges in the system both from the performance perspective and an integration side. The solution should gather analytical data, uses ML (machine learning) classification algorithm to filter email messages, be available all the time and all over the world. A lot of required stuff to provide and a lot of problems to solve.  

It is always difficult to find experienced people who has time to get involved in the venture.  

The domain itself is not well known for the team. Domain driven decomposition can be difficult to apply correctly at start.  

The following alternatives have been analysed to select appropriate architecture style:  

* monolithic appications were not taken under consideration because the system should be available, and responsible, and performant all time, and deployment time should be less than 5 minutes (for large monolitic applications these requirements can be challenging to achieve for higher load).

* event-driven architecture - very performant but not too much domain driven friendly. Its agility is good. Adding new processing units is quite easy as long as an additional coordination is not needed. Scales great. A lot of processing can be parallelised. The provided architecture is not simple to apply, you have to know what you are doing to do it well.  

* space-based architecture - good for applications that have variable load or inconsistent peak times. It is not a good choice for traditional large-scale relational database systems. Its very expensive and extremery complex solution. Great for high volume requests sent at the same time.

* microservices-architecture - has problems with latencies epecially when many data aggregations are needed because data comes from different microservices. Challenging to decompose when the business domain is not well known. It is better to start from coarse-grained services for greenfield systems to not drown in tasks related to infrastructure preparation itself at the very beginning.

* service-based architecture - more coarse-grained services than for microservices, but performance is still low. Good as a transitional step to microservices architecture.

* service oriented architecture - good for enterprise level scope when integration between systems is required. Involves people from all teams to create simple functionality (agility is very low). Too high level of abstraction impacts performance. Very expensive to maintain.

* server-less architecture - there is always a risk of 10% functionalities you will not able to implement because the service provider doesn't provide it. Vendor's APIs lock-in can be big disadvantage.

## Decision

Because of so many factors comes from requirements and taken into consideration we decided to select hybrid solution. Event-driven architecture based on broker topology and applied to independently deployable groups of processing units decomposed by following criterias:  
* a domain (e.g. trips, notification, integration connectors),  
* transaction coordination (to avoid distributed transactions),  
* data location (to avoid inter-service communication through event topics),  
* data processing characteristic.  

We have chosen this architecture because of event-driven architecture parallel processing characteristic.  

Its characteristics fit quite well into non-functional requirements. It is performant, elastic, deployment is very quick, response to change is quick as well, and it scales great.  

The nice characteristic of event-driven broker architecture is great load peaks distribution. The requests are not skipped because of lack of resources but were processed when the resoruces are available. Message queues allows to elastic scaling of processing units on operational level.

## Consequences

Some kind of custom error handling mechanism must be implemented e.g. based on error queues.  
End-to-end testing higly asynchronous systems is always challenging. Trying to test realistic kinds of scenarios can be tricky. The use of synthetic transactions or correlation IDs is required to allow monitoring of the whole solution.  

The adopted broker topology is very complex to understand. A lot of responsibility of coordination falls on developers.  

You should avoid build bottlenecks to build really performant system.  

You should avoid transaction coordination or even worse distributed transactions. Each event processor should works independently. The incomming and outgoing events are important to wire together coordination.  

The waking up new instanceof of processor needs some time to register to the broker to be ready to take over the processing of requests (orchestration happens on operation level - elastic scaling when message topic/queue starts filling up, you can span more instances of the service).  

Requires more coordination in component modification than for e.g. microservices.  

The proposed architecture needs future decomposition to achieve better level of scalability. It is worth to take under consideration critical components extraction as fine-grained, independently deployable processing units in the future, if needed.  


[Go back](./README.md)