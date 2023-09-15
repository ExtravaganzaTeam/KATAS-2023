[short text file; 1-2 pages long, one file per decision]

# Title

Data synchronisation

## Status

**accepted**

## Context

[description of the problem and alternative solutions available (documentation)]

The traveler is travelling all over the world. The system is deployed to multiple datacenters spreaded geographically between different continents.
The problem is how to synchronise data between datacenters for people travelling overseas.

We can sychronise all data, analytical and operational but it is very expensive solution that consumes hardware resources (e.g. network bandwidth, servers power, etc.). This kind of synchronisation creates new problems with reports generation.  
We can synchronise only part of data we need at the moment.  

## Decision

[decision and justification (the “why”)]

We decided to synchronise only part of the data about current journey undertaken by a traveler.

## Consequences

[trade-offs and impact of decision]



The data travels with the traveler.