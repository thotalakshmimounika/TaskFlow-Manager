
# TASK - FLOW MANAGEMENT

## Overview
This project implements a Task Management System using a RESTful API architecture built with Spring Boot. The API supports user registration and login, task management (CRUD operations), and advanced features like filtering and searching.

## Instructions to Run the Application Locally

### Prerequisites
- **Java 11 or above** installed on your machine.
- **Maven** for managing dependencies and building the project.
- **MySQL Database** installed and running locally.
- **Docker** (optional) if you want to run the application using Docker.

### Setup Steps

#### Clone the Repository
Clone the repository to your local machine:
```bash
git clone https://github.com/thotalakshmimounika/TaskFlow-Manager
cd TaskFlow-Manager
```

#### Configure MySQL Database
Ensure that MySQL is running on your local machine.

1. Create a new database named `task_management_db`:
   ```sql
   CREATE DATABASE task_management_db;
   ```

2. Update the `src/main/resources/application.properties` file with your MySQL credentials:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/task_management_db
   spring.datasource.username=your_mysql_username
   spring.datasource.password=your_mysql_password
   
   # Other common Spring Boot settings
   spring.jpa.hibernate.ddl-auto=update
   spring.jpa.show-sql=true
   spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL5Dialect
   ```

#### Build the Project
Use Maven to install dependencies and build the project:
```bash
mvn clean install
```

#### Run the Application
After a successful build, you can run the Spring Boot application:
```bash
mvn spring-boot:run
```

Alternatively, you can run the packaged JAR:
```bash
java -jar target/task-management.jar
```

#### Access the Application
Once the application is running, you can access the API via:
```
http://localhost:8080/
```

### Docker Instructions (Optional)
To run the application using Docker:

#### Build the Docker Image
```bash
docker build -t task-management-system .
```

#### Run the Application
Use Docker Compose to start both the application and the database:
```bash
docker-compose up
```
This will spin up both the Spring Boot application and a MySQL database container.

## Documentation
Explore the API endpoints and integration details in the [Postman Collection](https://documenter.getpostman.com/view/19274512/2sAXqzVdUK).

## Features
- User Registration and Login
- CRUD operations for tasks
- Task assignment to users
- Filtering options for tasks based on status, priority, and due date
- Search functionality for tasks by title or description
- Dockerized application for easy deployment
- CI/CD pipeline using GitHub Actions

## Assumptions
- Each task is assigned to a single user, and a user can have multiple tasks.
- Authentication is handled via JWT tokens.
- The task statuses are managed as an enum.

