# Spring boot Microservices

- [Why was this project created?](#why-was-this-project-created)
- [Use case](#use-case)
- [Subprojects](#subprojects)
- [Next step](#next-step)


## Why was this project created? <a name="why-was-this-project-created"></a>

Proof of Concept: Cloud native approach to building and running applications that exploits the advantages of the cloud computing delivery model. Using the microservices architecture with the last Spring Boot version.

## Use Case <a name="use-case"></a>

Information management system for educational institutions to manage all student's data. It provides abilities such as registration of students in classes, documenting of grades and analytical marks of each student and other evaluation elements.

Using Domain driven design to break into services like: library, students, school, grades and users

## Subprojects <a name="subprojects"></a>

Below is shown a brief introduction to the subprojects included in this one:

### Discovery Service

Server used to register all microservices. Using Netflix Eureka each client can simultaneously act as a server, to replicate its status to a connected peer. In other words, a client retrieves a list of all connected peers of a service registry and makes all further requests to any other services through a load-balancing algorithm (Ribbon by default).

- [discovery-server](https://github.com/flaviojuniord3v/discovery-service)

### Configuration Server

The yaml configurations of the projects were all exported and configured through the Config Server microservice.

* [config-server](https://github.com/flaviojuniord3v/config-server)


Those configuration values have been added into the project:

* [ConfigServerData](https://github.com/flaviojuniord3v/config-repo)


### Gateway Service

Gateway implementation used by the other microservices included in this proof of concept. This module contains a filter to registry every web service invoked,
helping to debug every request. 

* [gateway-service](https://github.com/flaviojuniord3v/gateway-service)

### Domain Projects and repositories

I am using the following technologies:

* **Hibernate** as ORM to deal with the PostgreSQL database.
* **JPA** for accessing, persisting, and managing data between Java objects and database.
* **MapStruct** used to conversion between Entities <--> DTOs in an easy way.

In domain microservices, the layer division is:

* **repository** layer used to access to the database.
* **service** containing the business logic.
* **rest** REST Api Spring MVC.
* **config** with several classes used to manage several areas such: persistence, exception handlers, etc.
* **domain** to store the entities.
* **dto** custom objects to contain specific data.

### Applications

* [library-service](https://github.com/flaviojuniord3v/library-service) - Microservice related to the application of the library. 
* [student-service](https://github.com/flaviojuniord3v/student-service) - Microservice related to the application of the student. 
* [school-service](https://github.com/flaviojuniord3v/school-service) - Microservice related to the application of the school. 

## Next step <a name="next-step"></a>

The next step of the proof of concept will be implement authentication and authorization between microservices



