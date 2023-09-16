# Title

Internal throughput

## Status

**accepted**

## Context

The proposed solution is distributed in its nature. There are always troughput and letency problems in internal communication on datacenter level. We should 'help' the infrastructure to work as performant as possible, with optimal resources consumption.  

The events can be processed one by one on the broker level but it is not an optimal approach to inter-services communication. The other solution is to group events together and pushes it to the broker when the defined criterias happen e.g. time criteria, numerical criteria etc.  

When the events buffer is full the group of events is pushed to or from the broker. If proposed criterium doesn't happen the time criteria happens e.g. push group of events every 50ms if events exist.  

## Decision

To optimise application throughput in local datacenter network we decided to not forward events one at a time on broker level, but instead to group events together when communication with broker happens, to reduce the number of network round trips and speed up processing significantly.  

## Consequences

Components connected to broker directly must be prepared for processing events in groups. Possible failure of a broker or a component will result in the need to process the group of events again. Events payload must be immutable.  