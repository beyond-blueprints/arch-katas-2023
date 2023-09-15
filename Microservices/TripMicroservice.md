
![Initial Data Loader](https://github.com/beyond-blueprints/arch-katas-2023/blob/main/Diagrams/IndividualComponentDiagrams/TripService.drawio.png)

# Capability and Solution Description

The TripMicroService is dedicated to handling user (client) requests and serves as the backend for populating the Road Warriors Trip dashboard. Its primary responsibilities include communicating with a NoSQL database to retrieve pre-prepared trip data, which is made ready for serving by the DataPreparationMicroservice.

The query results will be cached to enhance response times. In cases where updates are received from data sources, the cache will be invalidated for the respective customer. Customers will have the capability to manually add, edit, or remove bookings within a trip or the trip itself. These updates will be reflected in the database, and the associated cache will be invalidated accordingly.


# Components
- TripService
- TripUpdateService
- Cache Cluster on Cloud
- NoSQL DB Cloud Service


# Architectural Choice
- Microservice
- Cloud services


