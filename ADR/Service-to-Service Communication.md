# Service-to-Service Communication

## Status

ACCEPTED

## Context

To establish the guidelines for enabling effective communication between microservices. Currently, the system comprises a limited number of microservices, making it appropriate to deliberate on an efficient communication strategy that aligns with the system's size and projected growth. The amount of inter services communication is minimal given the event driven architecture being followed.

### Decision

System to use API Gateway

### Consequences
- The use of an API Gateway allows us to handle the communication needs effectively, maintaining a streamlined architecture. However, it's important to revisit this decision as the system evolves and the number of microservices grows. As the system scales, we may need to reassess and potentially introduce a Service Mesh to manage the communication in a more sophisticated manner.
