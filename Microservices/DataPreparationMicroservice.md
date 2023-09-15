
![Initial Data Loader](https://github.com/beyond-blueprints/arch-katas-2023/blob/main/Diagrams/IndividualComponentDiagrams/InitialDataLoader.drawio.png)

# Capability and Solution Description

The Initial Data Loader sets up trip data for a user immediately after registration. The system notifies the user that their data is being synchronized across various systems and will be ready on the dashboard within a few minutes.

The DataLoader communicates with the Data Orchestrator, which in turn communicates with various systems such as GDS (Apollo/SABRE), existing airline, hotel, and car rental interfaces. It also polls whitelisted emails to gather booking details data, applying appropriate filters. This service-based data fetching occurs only during the initial data setup after a user registers. Once the data is fetched, it is moved into a message channel cloud service. A serverless aggregator reads the message groups from the queue and updates the trip data for that customer in the NoSQL Cluster on the Cloud. 



![Data Updates](https://github.com/beyond-blueprints/arch-katas-2023/blob/main/Diagrams/IndividualComponentDiagrams/DataUpdatesConsumer.drawio.png)


# Architectural Characteristics

All mail exchange servers, GDS, and existing interfaces (airline, hotel, and car rental) provide a subscription feature. This feature allows Road Warriors to retrieve updates on changes or updates in the source system based on the subscribed topics. Road Warriors will utilize the details received from the source systems, converting them into standardized, clean messages, and pushing them to a message queue. The TripAggregator will pick up these messages for further processing. Additionally, these updates are sent as complete events in the Cloud Event Streaming Service. The NotificationService and BigDataAnalyticsService consume these data update events. Such a pubsib model will make sure the data flows into Road Warriors as soon as there is an update in the source system and TripAggregator will update the NoSQL DB. UI will be served from this DB. 

# Components
- InitialDataLoader
- Orchestrator
- EmailPoller
- ExternalDataSources
- Messaging Queue Cloud Service
- TripAggregator
- NoSQL DB Cloud Service
- MessageSubscriber
- Cache Cloud Service
- Event Stream Cloud Service


# Architectural Choice
- Microservice
- Publisher/Subscribe Model for updates.
- Service based integration for initial data setup
- Cloud services

