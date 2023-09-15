[short text file; 1-2 pages long, one file per decision]

# Title

Data distribution between datacenters

## Status

**accepted**

## Context

[description of the problem and alternative solutions available (documentation)]

The application must work internationally.
Travellers are travelling overseas very ofter. To avoid a communication latency problem existing between end user device and datacenter some mechanism of application distribution between different datacenters located on different continents is required.

## Decision

[decision and justification (the “why”)]
We decided to deploy application components to different datacenters spreaded across different continents. The closer the user application is to the server services the lower latencies are.  

We don't want the user to wait long for a response from the application. The application should be responsible to increase user satisfaction with its operation.

We decided to transfer only travelling data (from operational database) batween datacenters spreaded geographically across different continents 

## Consequences

[trade-offs and impact of decision]
The synchyronization application component must be maintained to support different versions of communication protocol (it is not possible to update all synchronization components deployed to all datacenters in the same time).