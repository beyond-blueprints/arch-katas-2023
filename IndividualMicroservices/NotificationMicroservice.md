
![Initial Data Loader](https://github.com/beyond-blueprints/arch-katas-2023/blob/main/Diagrams/IndividualComponentDiagrams/NotificationService.drawio.png)

# Capability and Solution Description

The NotificationMicroservice is tasked with providing timely updates to customers regarding any changes within the source system. These updates encompass various aspects, including flight delays, gate changes, and more.

All update events, pushed by the MessageSubscriber Component of the DataPreparationMicroservice to the Event Streaming Cloud Service, will be consumed by this microservice.

The Consumer Component will process the event, converting it into a standardized message structure before pushing it onto the message queue. Serverless Lambda Functions will then retrieve these messages from the queue and interface with a cloud-based Notification Service. This Notification Service will send notifications to the user via SMS, email, and push notifications.

Serverless Functions will maintain DB records for the notifications which failed and FailedNotificationScheduledJob will pick those up and push it the queue again.


# Components
- EventConsumer
- Messaging Queue Cloud Service
- Serverless Functions On Cloud
- FailedNotificationScheduledJob
- Cloud Notification Service
- Relational DB Cloud Service


# Architectural Choice
- Microservice
- Cloud services
- Event Driven Architecture


