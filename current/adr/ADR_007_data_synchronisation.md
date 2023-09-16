# Title

Data synchronisation

## Status

**accepted**

## Context

The traveler is travelling all over the world. The system is deployed to multiple datacenters spreaded geographically between different continents.
The problem is how to synchronise data between datacenters for people travelling overseas.

We can sychronise all data, analytical and operational but it is very expensive solution that consumes hardware resources (e.g. network bandwidth, servers power, etc.). This kind of synchronisation creates new problems with reports generation.  
We can synchronise only part of data we need at the moment.  

## Decision

We decided to synchronise only part of the data about current journey undertaken by a traveler. When the traveler is "back home" (the trip has finished) the data is moved to the desitnation datacenter.  

The data travels with the traveler.

## Consequences

Some mechanism of data synchronisation is required.  

When the traveler changes his "home location" because he moves overseas his data needs to be transfered to a new "home location" as well.  

The generation of reports is easier because analytical data are strored always in datacenter located on the same continent.  

[Go back](./README.md)