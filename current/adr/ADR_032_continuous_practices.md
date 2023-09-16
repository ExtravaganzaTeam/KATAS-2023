# Title

Continuous practices

## Status

**accepted**

## Context

[description of the problem and alternative solutions available (documentation)]

Continuous practices are very important nowadays in software development process.  

**Continuous integration**  

Developers practicing continuous integration merge their changes back to the main branch as often as possible. The developer's changes are validated by creating a build and running automated tests against the build. By doing so, you avoid integration challenges that can happen when waiting for release day to merge changes into the release branch.  

Continuous integration puts a great emphasis on testing automation to check that the application is not broken whenever new commits are integrated into the main branch.  

**Continuous delivery**

It is an extension of continuous integration since it automatically deploys all code changes to a testing and/or production environment after the build stage. On top of automated testing, you have an automated release process and you can deploy your application any time by clicking a button.  

In theory, with continuous delivery, you can decide to release daily, weekly, fortnightly, or whatever suits your business requirements. However, if you truly want to get the benefits of continuous delivery, you should deploy to production as early as possible to make sure that you release small batches that are easy to troubleshoot in case of a problem.  

**Continuous deployment**

Continuous deployment goes one step further than continuous delivery. With this practice, every change that passes all stages of your production pipeline is released to your customers. There's no human intervention, and only a failed test will prevent a new change to be deployed to production.  

Continuous deployment is an excellent way to accelerate the feedback loop with your customers and take pressure off the team as there isn't a "release day" anymore. Developers can focus on building software, and they see their work go live minutes after they've finished working on it.  

Along with continuous integration and continuous delivery (CI/CD), companies need to practice continuous application performance testing to fully realize the benefits of DevOps. Proper instrumentation is crucial to ensuring you are collecting rock-solid metric data, and having a repeatable process for collecting is something that will benefit you regardless of how you are finding correlation.


## Decision

We have decided to apply continuous practices to help developers in their day-to-day work and help business to get feedback from end user/customers as fast as possible.  

Agile approach gives the project team a lot of benefits:  
* increased value proposition - offer an increased value proposition compared to traditional software development methods. It is possible by adding visibility, adaptability of business value and risk throughout the development process,  
* faster product delivery (faster time to market) - allows products to be rolled out quickly and changes to be easily made at any point during the development process,  
* flexibility - the incremental nature of Agile software development means that projects are completed in shorter sprints, making them more manageable, which brings flexibility to adopt changes if needed,  
* risk reduction - prioritize and organize the backlog of stories according to the customer’s vision well in advance,  
* superior quality - cross-functional and self-organizing teams which share ownership and keep constant communication, which ultimately reduces technical debt, i.e., the cost of the additional rework.

Distributed applications consisting of many elements that are independent execution units require tools supporting the process of continuous building, testing and deployment to achieve high agility of the application development process. Providing small changes more often significantly improves user experience and allows you to test their reactions to new functionalities, which is very valuable in the case of an agile approach.

## Consequences

Requires the use of additional tools and adequate work organization, but the benefits from them are priceless for the project.

[Go back](./README.md)