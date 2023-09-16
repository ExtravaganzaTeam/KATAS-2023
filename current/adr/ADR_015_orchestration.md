# Title

Orchestration

## Status

**accepted**

## Context

Containers like Docker provides a simple and efficient way to create and deploy containers and are great to use on local developement environments but are not perfect solutions for more complex use cases.  

The orchestration tools like Kubernetes are perfect choice to use and manage containers at scale. They allow to manage applications lifecycle and  applications monitoring in multiple datacenters. Are widely used in datacenters.  

Deploying dozens or hundreds of applications by hand in multiple datacenters is very iritating activity. We should avoid it as much as possible.  

Implementing our own tools is not a scope of the project.

## Decision

The application is distributed it its nature so we need some mechanism of managing multiple components automatically for development and production deployment activities.

We decided to use kubernetes orchestration tool to ease application deployment and orchestration across different datacenters. It gives some kind of infrastructure abstration managing the resources on your behalf. Developers can focus on writing application code and not the underlying compute, networking or storage infrastructure. It gives monitoring tools like health checks and automatic restarts of containers that have failed or stopped. They comes with a set of very handfull command line tools.

## Consequences

[trade-offs and impact of decision]
The kubernetes infrastructure is rich but requires quite a lot of attention. It is not a 'fire-and-forget' solution. Tools are powerful but sometimes difficult to use. Additional knowledge is required.

Considered cloud providers must support this class of solutions.  

[Go back](./README.md)