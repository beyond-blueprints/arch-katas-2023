# Event Driven Architecture vs Service Based Architecture

## Status

ACCEPTED

## Context

Need to make a critical architectural decision regarding how system will handle data updates that require immediate visibility(< 5 min) to the end-users.  Aim is to reduce resource consumption, minimize costs, and avoid continuous polling of data source systems to ensure real-time updates to the users.

### Decision

Event Driven Architecture and publisher/subscribe model to be followed primarily to address data updates and notifications. Services to be used only when necessary like to fetch data for the user just logged in for prepare dataset for the user who just registered etc.

### Consequences
- Real Time Updates
- Efficient Resource Utilization
- Cost effective

