# Monolith vs Microservices

## Status

ACCEPTED

## Context

Road warriors can be built using a microservices or monolith architetcure.
The road warrirors application will have 2 million active users per week with 15 million overall and the key feature of the application is a travel dashboard that shows the details on current and upcoming trips. 

This translates to following requirements:

Differential Scalability: Different components of the application architecture have varied scalability needs, like trip service is expected to handle much higher traffic vs customer service.

Separation of Concerns: Separating background jobs like analytics, data processing, data load into different services will help shield the customer facing services from any fault, abrupt computation needs of background jobs.

### Decision

Road Warriors design will leverage Microservices to address varying scalability needs and ensure a clear separation of concerns

### Consequences
- Microservices pattern will add design complexity and lead to higher effort.
