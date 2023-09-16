# Title

Application containerization

## Status

**accepted**

## Context

The development of distributed applications is always challenging when the integration part beetwen components is important. How to allow different teams working on different components to work together ?

Building the whole solution infrastructure on developers local environments is possible but managing configuration changes and applications updates is very expensive. It takes each developer time, creates frustration with constant changes and requires constantly keeping the applications in sync.
We don't want it. We want the developers to be focused on application development.

## Decision

We decided to use containers to help developers in their day-to-day work. The application is distributed it its nature so we need some automatic management mechanism for multiple components. Containerization allows developers to create and deploy applications faster and more securely. It provides portability between different platforms (developers can work on different operation systems they like the most and know the best).

## Consequences

Additional layer of abstraction and knowledge is required to use containers. Hardware acceleration for containers not always is enough to bear the weight of the application run in a container.  

[Go back](./README.md)
