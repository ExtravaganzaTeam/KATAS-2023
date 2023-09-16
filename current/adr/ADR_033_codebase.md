# Title

Codebase

## Status

**accepted**

## Context

The described issue was classified as an architectural decision because it comes directly from adopted software architecutre. The choice of software architecture influences the set of best practices that should be adopted in the project.  

The rules for choosing the number of repositories for a monolithic project are usually very simple — put the entire codebase in one repository, and that’s it.  

However, as the project grows, developers may decide to split the monolithic project into microservices. Choosing the number of repositories becomes a little more difficult. 

Perhaps the most obvious strategy for distributed architectures like a microservices is to put each microservice and each shared library into a separate repository. Then set up the CI and CD pipelines for each repository, where every repository represents a unit of deployment.  

This separation of application components gives us a number of advantages:  
* fast IDE - the larger the codebase in the one solution, the more computer resources your favorite IDE will need, which will affect your performance,  
* fast Git - version control systems like Git and others will work faster with small repos than with large ones,  
* clear separation of responsibilities - repositories are strict and clear boundaries that separate the entire codebase of an application. It is easy to assign a responsible team for each repository and track who is responsible for what.  

On the other hand, the multiple repository approach has several disadvantages:
* complicated development lifecycle - the development lifecycle is straightforward unless developers implement a feature that spans multiple repositories,  
* code duplication - development teams can start implementing the same or similar functionality in their repositories independently,  
* hard to enforce system consistency - when different teams work in different repositories, it is difficult to keep the entire system in a consistent state e.g. services use different frameworks, 
services use different versions of libraries, services use different design patterns, approaches and best practices.  

## Decision

We decided to apply multiple small repositories for each of developed components to support efficient IDE support for developers work.  

## Consequences

Every repository must have CI and CD pipelines.  

[Go back](./README.md)