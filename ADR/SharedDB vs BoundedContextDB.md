# SharedDB vs BoundedContextDB

## Status

ACCEPTED

## Context

In the development of our microservices-based architecture, a crucial decision revolves around the database strategy. We need to determine whether to use a shared database for multiple microservices or to opt for a dedicated database per microservice. The goal is to align with the principle of bounded context and ensure seamless communication with the database via the respective microservice.

### Decision

Microservice Specific DB. Where necessary to access another DB communicate via the APIs the target Microservices exposes.

### Consequences
- Isolation and Bounded Context
- Improved performance and scalability.
- Ease of deployment and maintainance.
