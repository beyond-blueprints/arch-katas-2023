# Relational DB vs Non-relational DB

## Status

ACCEPTED

## Context

When user lands on dashboard the trip data is to be served to the user reading from DB. This DB could be either SQL or NoSQL.  The data to be pushed to this DB wont be transactional data and neither the queries would be complex. This application needs a database which would be highly scalable, flexible, highly available, with fast read and write. 

### Decision

Given the contextual requirements, a NoSQL database offers the necessary capabilities to fulfill the application's needs, providing a highly scalable, flexible, and highly available database system with efficient read and write performance.

### Consequences
- Eventually Consistent Systems due to the distributed nature of NoSQL  databases. Highly available and faster read/write performance. If there is a need for an occasional complex queries during development then team can will have to work on optimizing it.
