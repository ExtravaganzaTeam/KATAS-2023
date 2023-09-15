# Title

Auto scaling

## Status

**accepted**

## Context

There is only average number of active users per week non-functional requirement given. There is no exact information how the load will be spreaded during the week or day. There is no information about load peaks.  

To be prepared on a temporary increase in resource utilization some mechanism of auto scaling is required on production environment.

## Decision

We diecided to use auto scaling of services to increase or decrease the desired number of servers nodes required to manage expected load. Supporting larger number of nodes running than needed all the time is not cost efficient at all. When the load decreases server nodes are released.

It addresses local load peaks problem.

## Consequences

We need to prepare application for auto scaling capabilities. One of the advises is to use a stateless services.
