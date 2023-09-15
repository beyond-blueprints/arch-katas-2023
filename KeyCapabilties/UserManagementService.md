
![Initial Data Loader](https://github.com/beyond-blueprints/arch-katas-2023/blob/main/Diagrams/IndividualComponentDiagrams/CustomerService.drawio.png)

# Capability and Solution Description

The UserManagementMicroservice is tasked with handling various user-related functionalities such as logins, registrations, social logins, trip sharing, profile updates, user preferences, consent, etc.
This microservice will interface with an Identity Provider (IDP) for authentication services and social logins. All customer data will be stored in a cloud-based relational database.

The user preferences will include email details that the user has granted access to. These details will be utilized by the DataPreparationMicroservice to poll or subscribe to emails, retrieving travel-related information.

Upon user login or registration, an event will be promptly dispatched to the Event Streaming Cloud Service. The Registration Event will be consumed by the DataPreparationMicroservice to setup initial data for the recently registered user.


# Components
- UserAuthenticationService
- IDP
- UserProfileService
- UserConsentManagementService
- SQL DB Cloud Service


# Architectural Choice
- Microservice
- Event Stream Cloud Service
- SQL DB Cloud Service

