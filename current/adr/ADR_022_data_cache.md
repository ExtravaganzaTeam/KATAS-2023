# Title

Data cache

## Status

**accepeted**

## Context

[description of the problem and alternative solutions available (documentation)]

There are two possible solutions for data caching. Local cache and distributed cache. Distributed cache has some challenges in face of latency and performance. Many distributed cache vendors (e.g. Hazelcast, Ignite) avoid performance comparisons with local data structures like hash maps. Distributed caches like Redis are very popular but have huge performance tradeof when more data needs to be find. Many requests sent by network slower down dramatically data availability. Definitely this kind of solutions are not for real-time systems.    

## Decision

To not read data about selected sources for scaning for trips (emails, travel systems) over and over again we decided to load the data from operational database once, at the service start, and keep it in local memory.

## Consequences

The adopted solution requires some mechanism of continuous cache synchronisation with underlying operational database.


[Go back](./README.md)