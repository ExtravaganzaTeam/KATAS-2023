# Title

Synchronization domain

## Status

**accepted**

## Context

Separation of concerns is a principle used in programming to separate an application into units, with minimal overlapping between the functions of the individual units. The separation of concerns is achieved using modularization, encapsulation and arrangement in software layers.

## Decision

The synchronization domain was separated from the functional requirements of the application.  
Synchronization tasks are very specific to deployment infrastructure.  

The separation of concerns helps development teams to distribute, plan, and manage work effectively.  

## Consequences

The independently deployable component will need to be managed and orchestrated.  


[Go back](./README.md)