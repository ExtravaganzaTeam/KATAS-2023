# Title

Data storages

## Status

**accepted**

## Context

There is always a question where to store the data. Is one type of database perfect to do all types of operations? Sometimes they are computationally complex, sometimes requires different computational power. There are many factors comes from different needs of the data processing application and the data nature itself.

## Decision

We decided to store data in two different types of databases for two different data processing pursposes. One is a relational database to store operational data and the other is no-sql database to store analytical data.

We don't want the processing of operational and analytical data to interfere each other. This processing has different nature, different data structures, and needs different processing power.

The amount of analytical data can grow at a much higher rate than the operational data. The operational data is updated and deleted while analytical data is stored for much longer time to create reports and provide to partners systems.  

## Consequences

The use of various data storage solutions requires the team to acquire the required knowledge if it does not already have it.

The overall maintenance cost is higher.  

[Go back](./README.md)