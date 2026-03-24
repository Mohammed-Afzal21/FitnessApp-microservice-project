# FitnessApp – Microservices Project

This is a microservices-based fitness application built using Spring Boot, Spring Cloud, React, Keycloak authentication, PostgreSQL, MongoDB, RabbitMQ, and Docker.
The system includes multiple microservices, an API gateway, service discovery, centralized configuration, messaging, databases, and a React frontend.

## Overview

The application allows users to register, log in, manage fitness activities, view AI-based workout suggestions, and access data through a secure microservices setup.

Authentication and authorization are implemented using Keycloak.

## Architecture

FitnessApp-microservice-project/
│
├── userservice/          → Manages users, integrates with Keycloak (PostgreSQL)
├── activityservice/      → Manages fitness activities (MongoDB)
├── aiservice/            → AI-based suggestions using Gemini API
│
├── configserver/         → Centralized configuration service
├── eureka/               → Service discovery
├── gateway/              → API gateway with JWT validation
│
├── fitness-app-frontend/ → React frontend with Keycloak login
│
└── docker-compose.yml


## Features

### System Features

* Microservices architecture
* API Gateway routing
* Eureka service registry
* Centralized configuration
* Event-based communication via RabbitMQ
* PostgreSQL and MongoDB databases
* Dockerized deployment
* AI suggestions using Gemini API

### Authentication

* Keycloak for login, signup, token issuance, session management
* Gateway verifies Keycloak-issued JWT tokens
* Role-based access supported

### User Features

* User registration and login through Keycloak
* Add and view fitness activities
* View AI-generated suggestions
* Dashboard and profile access

## Tech Stack

### Backend

* Java 17+
* Spring Boot
* Spring Cloud (Eureka, Config Server, Gateway)
* Spring Security + Keycloak
* Spring Data JPA
* Spring Data MongoDB
* RabbitMQ

### Frontend

* React
* Keycloak JavaScript Adapter
* Axios

### Databases

* PostgreSQL
* MongoDB

### Additional

* Docker
* Maven
* Gemini API for AI logic

## How to Run

### Prerequisites

* Java 17+
* Maven
* Node.js
* Docker and Docker Compose

## Running with Docker (Recommended)


docker-compose up --build


This starts:

* Keycloak
* PostgreSQL
* MongoDB
* RabbitMQ
* Eureka
* Config Server
* Gateway
* User Service
* Activity Service
* AI Service
* Frontend



## Running Without Docker

### 1. Start Keycloak

```
keycloak.bat start-dev
```

Import realm if required.

---

### 2. Start Config Server

```
cd configserver
mvn spring-boot:run
```

### 3. Start Eureka Server

```
cd eureka
mvn spring-boot:run
```

### 4. Start API Gateway

```
cd gateway
mvn spring-boot:run
```

---

### 5. Start Microservices

```
cd userservice
mvn spring-boot:run
```

```
cd activityservice
mvn spring-boot:run
```

```
cd aiservice
mvn spring-boot:run
```

---

### 6. Start Frontend

```
cd fitness-app-frontend
npm install
npm start
```

---

## API Access

Gateway Base URL:

```
http://localhost:8080
```

Sample Endpoints:

* User Service: `/users/register`, `/users/login`
* Activity Service: `/activities/add`, `/activities/list`
* AI Service: `/ai/suggestions`

---

## AI Integration

The AI service integrates with the Gemini API to generate workout recommendations and other fitness-related suggestions based on user activity patterns.

---

## Future Improvements

* Add notifications service
* Add analytics dashboard
* Add subscription/payment module
* Deploy to cloud (AWS/GCP)

---

## Author

Afzal
GitHub: [https://github.com/Mohammed-Afzal21](https://github.com/Mohammed-Afzal21)


