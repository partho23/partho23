Employees - REST API
Simple REST API to manage employees created with Spring Boot, Java 8 and Maven.

Table of Contents
Getting Started
Build and Run
Request and Response Examples
Technologies
Authors
Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

Prerequisites
Download the project zip or clone the repository with the following command:

git clone https://github.com/davmrs/employees-API
Build and Run
Build jar file with Maven:

mvn package
Run the jar file using:

java -jar target/employees-API-1.0.0.jar
Alternatively, you can go to the root directory of the application and run the app without packaging it using:

mvn spring-boot:run
The app will start running at http://localhost:8080.

Request and Response Examples
API Resources
GET /employees
GET /employees/[id]
POST /employees
PUT /employees/[id]
DELETE /employees/[id]
GET /employees
Retrieved all active employees.

Example: http://localhost:8080/api/v1/employees

Response body:

  [
      {
          "id": 1,
          "firstName": "David",
          "middleInitial": "S",
          "lastName": "Mora",
          "dateBirth": "22081991",
          "dateEmployment": "20092015",
          "active": true
      },
      {
          "id": 2,
          "firstName": "Juan",
          "middleInitial": "A",
          "lastName": "Guevara",
          "dateBirth": "03091978",
          "dateEmployment": "15032017",
          "active": true
      },
      {
          "id": 4,
          "firstName": "Fernando",
          "middleInitial": "J",
          "lastName": "Trinidad",
          "dateBirth": "28121990",
          "dateEmployment": "05042018",
          "active": true
      }
  ]
GET /employees/[id]
Retrieved the employee with the Id specified on URL only if it is active.

Example: http://localhost:8080/api/v1/employees/2

Response body:

  {
      "id": 2,
      "firstName": "Juan",
      "middleInitial": "A",
      "lastName": "Guevara",
      "dateBirth": "03091978",
      "dateEmployment": "15032017",
      "active": true
  }
POST /employees
Create a new employee.

Example: Create – POST  http://localhost:8080/api/v1/employees

Request body:

  {
      "firstName": "Rodrigo",
      "middleInitial": "P",
      "lastName": "Garces",
      "dateBirth": "01011998",
      "dateEmployment": "11092019"
  }
PUT /employees/[id]
Update existing employee with the Id specified on URL.

Example: Update – PUT  http://localhost:8080/api/v1/employees/4

Request body:

  {
      "firstName": "Fernanda",
      "middleInitial": "M",
      "lastName": "Sanchez"
  }
DELETE /employees/[id]
Switch status of employee with the Id specified on URL to inactive.

Example: http://localhost:8080/api/v1/employees/4

Header:

Authorization       Basic RGF2aWQgTW9yYTpwYXNzd29yZDEyMw==
Response body:

  {
      "id": 4,
      "firstName": "Fernanda",
      "middleInitial": "M",
      "lastName": "Sanchez",
      "dateBirth": "28121990",
      "dateEmployment": "05042018",
      "active": false
  }
Technologies
Project built with:

Spring Boot - Java Framework used for building production-ready applications
Java SDK 8 - Java SE Development Kit 8
Maven - Dependency Management
Authors
David Mora - Initial work - davmrs
