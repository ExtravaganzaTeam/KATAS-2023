# Title

External latency

## Status

**accepted**

## Context

People are travelling all over the world. The application to be useful and responsive all the time must have the lowest communication lattencies possible. Connecting to the datacente located on the other side of the Earth is rather time costly. Multiple datacenters located on multiple continents reduce this cost and helps application user to have fan from its functionality.  

## Decision

We decided to deploy system in different datacenters located on different continents all over the worlds.
The closer end user device is to the datacenter the shorter latencies are.  

## Consequences

Management of multiple datacenters deployments and maintenance increases the system maintenance cost significantly.  

Some mechanism of travel data synchronisation between datacenters is required when the traveler travels overseas and connects to application deployed in another datacenter.  

[Go back](./README.md)