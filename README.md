<p align="center">
  <a target="_blank"><img src="https://angular.io/assets/images/logos/angular/angular_solidBlack.png" width="120" alt="Angular Logo" /></a>
<a target="_blank"><img src="https://spring.io/images/projects/spring-edf462fec682b9d48cf628eaf9e19521.svg" width="100" alt="Spring Logo" /></a>
</p>


[![GitHub license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/fedexu/love-article/blob/master/LICENSE)
[![sonar qube](https://sonarcloud.io/api/project_badges/measure?project=fedexu_love-article&metric=alert_status)](https://sonarcloud.io/dashboard?id=fedexu_love-article)

# Love Article

This is a tutorial project, the purpose is to show one of the many possible implementation of the <a target="_blank" rel="noopener noreferrer" href="http://martinfowler.com/microservices/">Microservice Architecture Pattern</a> by using Spring Boot, Spring Cloud and Docker.

<p align="center">
  <a target="_blank"><img src="https://user-images.githubusercontent.com/22296699/74551163-fd12c600-4f52-11ea-8343-a66c0a87759c.gif" alt="angular-pwa-gif" /></a>
</p>


## Functional services

Love Article is created with three core microservices. All of them are developed following the pattern Domain-Driven Design (DDD) and they are independently deployable applications.

<p align="center">
  <img width="868" alt="functional_schema" src="https://user-images.githubusercontent.com/22296699/74650581-54e34400-5182-11ea-9a57-49156563b088.png">
</p>

#### Favorites service
Contains the favorite articles and metadata about them.

//TODO API TABLE

#### Articles service
It's the data service that contains all the articles of the site

//TODO API TABLE

#### Statistics service
Performs calculations about the favorites articles of all the users and the "Hot topic" on the site. It work on the "tag" on the articels and the number of the favorites topic along with the creation date of the article itself. 
The data generated it's used to order articles list on the main window.

//TODO API TABLE

## Infrastructure architecture
In this project there is some distributed system patterns implemented. <a target="_blank" rel="noopener noreferrer" href="http://projects.spring.io/spring-cloud/">Spring cloud</a> enhance Spring Boot applications to implement those patterns and it's used in this project along with some Netflix OSS projects.

<p align="center">
  <img width="963" alt="infrastructure_architecture" src="https://user-images.githubusercontent.com/22296699/74650527-3bda9300-5182-11ea-9896-b8eea0d8b2e3.png">
</p>

//TODO description or list of the tool included in the project


## Local environment run

This project use 9 Spring Boot application, 4 Database instances and RabbitMq.
Ensure that you have at least `4 Gb` RAM available by running it with Docker-compose. A second options is to run the core services (Gateway, Registry, Config, Auth Service and Functional services ) manually.

#### Before you start

- Install Docker along with Docker Compose.
- Build the project: `mvn clean package -DskipTests`

#### Run the app

To run the app simply type `docker-compose up --build`
All the images will be builded locally and runned. If you want to detach the process add -d in the command.

#### Important endpoints
- http://localhost:4000 - Gateway
- http://localhost:7777 - Eureka Discovery Dashboard
- http://localhost:15000 - RabbitMq (username/password: guest/guest)

#### Notes
If you see some error in the startup process, no worries. The Docker compose V3 have removed the `depends_on` option and the application are resilient to the fail startup.

Discovery Service take a while to register all the applications (default heartbeat is 30s). This service will be the first to start up but you need some time to see all the services register to it.

## Help me to get the app famous!

Love Article is open source and want to give to you the basics knowledge about cloud native application with Spring and java technologies. A star to this project will be appreciate!


