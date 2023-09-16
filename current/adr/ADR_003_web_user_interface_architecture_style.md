# Title

Web user interface architecture style

## Status

**accepted**

## Context

The traditional layered architecture can cause issues when it comes to delivering software effectively. Frontend teams, backend teams na event database teams must work together. Simple change requires work cooperation between three different teams.  

Alternatives to choose are:  
* monolitic frontend - most common for single page applications when there is a dedicated frontend team. Having multiple teams share responsibiilty for monolithic frontend can be challenging due to the multiple sources of contention.  
* micro frontends - different parts of frontend can be worked on and deployed independently. The key decompositional techniques are widget-based decomposition and page-based decomposition. They are a good choose for teams where you are trying to move away from a layered architecture.  

## Decision

We have chosen widget-based decomposition pattern to implement rich web interface for SPA (signle page application) because we have full-stack teams and we want to give them space to work independently. Widgets can be independently changed and teams can contribute to the same UI.  

The widget decomposition pattern is incredibly useful if you are building a rich web-based user interface, and I would strongly suggest the use of widgets in any situation in which you are making use of a SPA (single page application) framework and want to break up responsibilities for the frontend, moving toward a micro frontend approach.  

## Consequences

There is still a need of some sort of assembly layer to pull widgets together. This could be as simple as making use of server-side or client-side templates.  

You can incrementally update the frontent UI (each widget separately) but you can end up with a lot of duplicatio between dependencies, which in turn can lead to a large bloat in terms of page load size. A simple small change in the dependencies of one widget could result in a whole host of new dependencies being included in the application, drastically inflating the page size.  

[Go back](./README.md)