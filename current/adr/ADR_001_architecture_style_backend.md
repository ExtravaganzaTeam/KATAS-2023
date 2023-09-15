[short text file; 1-2 pages long, one file per decision]

# Title

[short noun phrase]

## Status

**accepted**
[proposed, accepted, superseded]

## Context

[description of the problem and alternative solutions available (documentation)]

Other alternatives:
Monolithic appications were not taken under consideration because the system should be available, and responsible, and performant all time, and deployment time should be less than 5 minutes (for large monolitic applications these requirements can be challenging to achieve).

space-based architecture - good for applications that have variable load or inconsistent peak times. It is not a good choice for traditional large-scale relational database systems. Its very expensive and extremery complex solution. Great for high volume requests sent at the same time.

microservices-architecture - problems with latencies epecially when many aggregations data are needed - and comes from different microservices, difficult to implement when the business domain is not well known. It is better to start from corse grained services for green field systems.

service-based architecture - more corse-grained services than in microservices, but performance is still low

SOA - for enterprise level scope when integration happens. Involves people from all teams to create simple functionality (agility is very low). Too high level of abstraction impacts performance. Very expensive to maintain.

server-less architecture - there is always the rist of 10% functionalities you will not able to implement. I personally use it only for proof-of-concept work

## Decision

- Some of hybrid architecture of event-driven and service-based

[decision and justification (the “why”)]

performance, elasticity, deployment very quick, responds quickly to change.

the services are more macro-services like in service-based architecture

deployment is easy
performance and scalability are great.

event-driven architecture in its core system.
macro services selected by domain specific tasks e.g. notification, trips, integration connectors etc.

peaks of high throughpoot
The nice characteristic of event-driven broker architecture is great load peaks distribution.
broker rozkłada obciąenie i pozwala obsłuyć większą ilość ządań bez ich odrzucania

Message queues allows to elastic scales on operational level.

YOu can break down processors as a separete services in the future when it will be required.

## Consequences

[trade-offs and impact of decision]


Some kind of custom error handling mechanism must be implemented e.g. based on error queues.  
End-to-end testing higly asynchronous system is always challenging. Trying to test realistic kinds of scenarios can be tricky. The use of synthetic transactions or correlation IDs is required to allow monitoring of the whole solution.
The adopted broker topology is very complex to understand. A lot of responsibility of coordination falls on developers.
You should avoid build bottlenecks to build realy performant system.
You should avoid transaction coordination or even worse distributed transactions. Each event processor should works independently. The incomming and outgoing events are important to wire together coordination.

The waking up new instanceof of processor needs some time to register to the broker to be ready to take over the processing of requests (happens on operation level) - elastic scale when message topic/queue starts filling up you can span more instances of the service.   

Requires more coordination in componenet modification than for e.g. microservices.
Orchestration on processors level.

[Go back](./README.md)