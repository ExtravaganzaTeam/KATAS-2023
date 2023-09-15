# Title

Versioning

## Status

**accepted**

## Context

During its lifespan, the application requires improvements, bugs fixes etc. New versions of application must be released and some mechanism of tracking changes is required.  

One of the choices for versioning is a semantic versioning concept. It is based on major, minor, and patch version numbers.  

The popular alternative to semantic versioning is a calendar versioning. It invites its adopters to define their scheme considering how time impacts their project. The scheme structure is similar to semantic versioning, but what each segment means is more fluid. In most cases the major number is linked to the year of the release. For minor and micro numbers, adopters use ad-hoc strategies and combine notations from semantic versioning.

The application version and communication protocol version changes differently for the same service and should be tracked independently (not all changes to code impact service contract).

## Decision

For application components versioning we decided to use semantic versioning.

For communication protocol versioning we decided to use semantic versioning.

Developers find it easier to work with a semantic versioning scheme because it is more intuitive given that it is closer to the code.

## Consequences

As a project grows, more considerations have to be made to define a versioning scheme that communicates effectively with users.

To release applications consist of multiple compoenents with different versions, it is needed to apply version management mechanism to know exactly what version of the component should be a part of a release.