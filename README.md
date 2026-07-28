\# Workshop JavaFX + JDBC



> Desktop CRUD application built with JavaFX and JDBC for Seller and Department management.



\## About



This project was built following Nelio Alves' Java course as the foundational version of a 

desktop management system. It was later evolved into a Spring Boot REST API architecture 

in the \[seller-department-api](https://github.com/Lucileudo-Lopes/seller-department-api) project.



\## Tech Stack



\- Java 11

\- JavaFX 21

\- JDBC (MySQL)

\- MVC Architecture

\- Design Patterns: DAO, Factory, Observer, Singleton



\## Features



\- Department CRUD (Create, Read, Update, Delete)

\- Seller CRUD with Department association

\- Form validation with error messages

\- Confirmation dialog before delete

\- Responsive TableView



\## How to run



\### Prerequisites

\- Java JDK 11+

\- JavaFX SDK 21

\- MySQL Server

\- Eclipse IDE with e(fx)clipse plugin



\### Setup

1\. Clone the repository

2\. Configure JavaFX User Library in Eclipse

3\. Copy `db.properties.example` to `db.properties` and fill your credentials

4\. Run the SQL script to create the database

5\. Run `application.Main`



\## 🗄 Database



```sql

CREATE DATABASE coursejdbc;

USE coursejdbc;



CREATE TABLE department (

Id int(11) NOT NULL AUTO\_INCREMENT,

Name varchar(60) DEFAULT NULL,

PRIMARY KEY (Id)

);



CREATE TABLE seller (

Id int(11) NOT NULL AUTO\_INCREMENT,

Name varchar(60) NOT NULL,

Email varchar(100) NOT NULL,

BirthDate datetime NOT NULL,

BaseSalary double NOT NULL,

DepartmentId int(11) NOT NULL,

PRIMARY KEY (Id),

FOREIGN KEY (DepartmentId) REFERENCES department (Id)

);

```



\## Project Structure



src/

├── application/ # Main class

├── db/ # Database connection

├── gui/ # Controllers + FXML views

│ ├── listeners/ # Observer pattern interfaces

│ └── util/ # UI utilities

├── model/

│ ├── dao/ # DAO interfaces

│ │ └── impl/ # JDBC implementations

│ ├── entities/ # Domain entities

│ ├── exceptions/ # Custom exceptions

│ └── services/ # Business logic



\## Next version



This project was migrated to a professional Spring Boot REST API:
 \[seller-department-api](https://github.com/Lucileudo-Lopes/seller-department-api)







