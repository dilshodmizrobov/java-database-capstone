Section 1: Architecture Summary

This Spring Boot application follows a hybrid architecture combining both MVC and RESTful design principles.
It uses Thymeleaf templates for server-side rendered dashboards (AdminDashboard and DoctorDashboard) and REST APIs for other modules like patients, appointments, and prescriptions.

The backend interacts with two databases:

MySQL for structured relational data (doctors, patients, appointments, and admin).

MongoDB for flexible document data (prescriptions).

All controllers delegate logic to a Service Layer, which applies business rules and communicates with the Repository Layer.
Repositories manage data persistence through Spring Data JPA (for MySQL) and Spring Data MongoDB (for MongoDB).
This layered design ensures clean separation of concerns, scalability, and maintainability following Spring Boot best practices.

Architecture Diagram

Section 2: Numbered Flow of Data and Control

The user accesses the system through one of the dashboards (AdminDashboard or DoctorDashboard) or REST-based modules (Appointments, PatientDashboard, PatientRecord).

The action triggers a request routed to the appropriate controller — either a Thymeleaf Controller for web pages or a REST Controller for API endpoints.

The controller validates input and calls the Service Layer to process the business logic.

The Service Layer coordinates with the corresponding Repository to perform data persistence or retrieval.

The MySQL Repository accesses the MySQL Database, handling relational data such as patients, doctors, appointments, and admins.

The MongoDB Repository accesses the MongoDB Database, managing unstructured or document-oriented data like prescriptions.

Retrieved data is converted into JPA entities (for MySQL) or MongoDB documents, which are then passed back through the service and controller layers to the frontend:

Thymeleaf Controllers render HTML templates with model data for web dashboards.

REST Controllers return JSON responses to API clients.
