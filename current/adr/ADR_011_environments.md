# Title

Environments

## Status

**accepted**

## Context

To the project goes smoothly we need different environments for different purposes. The development team members needs its environment to work, the test team members needs their own environment to do tests, the integration activities needs their own environment to do integration tasks.

The solution to the problem is to prepare dedicated environments to specific tasks e.g development, tests, staging and production.

The use of one environment only for tests, staging and development activities is not efficient at all. It blocks product development when the team size is greather than one or two members, and makes many integration collisions. The conception of developing on production environment was very popular in late ninetees. Support teams made changes directly on the production to keep the system running. It was a very risky practice.


## Decision

We decided to have different environments for different activities to ease the work of team members.  
The local development environment on developers machines.  
The test environment for testing purposes.  
The staging environment for production environment mirroring. The data on staging environment should be mimic (impersonal).
The production environment to support production activities.
For integration tasks developers should connect to staging environment. If it will be not enough the dedicated integration environment can be took into consideration.

## Consequences

Increased infrastructure complexity. Higher infrastructure cost.
