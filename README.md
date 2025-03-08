# Swiggy API

## Overview

The Swiggy API is a backend service that facilitates food ordering, restaurant management, cart handling, user authentication, delivery tracking, and reviews. This project is built using **Spring Boot** and follows a well-structured architecture with controllers, services, DTOs, entities, repositories, and security configurations.

## Features

- **User Authentication** (Sign Up, Sign In, JWT Security)
- **Restaurant Management** (Sign Up, Add Menu Items, Update Details)
- **Food Ordering System** (Cart, Orders, Payments)
- **Delivery Partner Integration** (Assign Orders, Track Deliveries)
- **Review System** (Add & View Reviews)
- **Exception Handling**
- **Pagination & Filtering**

## Project Structure

```bash
.mvn/wrapper/
│── maven-wrapper.properties
│── bin/
│── src/
│   ├── main/
│   │   ├── java/com/shivu/swiggy_api/
│   │   │   ├── config/ (Security configurations)
│   │   │   ├── controllers/ (Request handling controllers)
│   │   │   ├── dto/ (Data Transfer Objects)
│   │   │   ├── entity/ (Database entities)
│   │   │   ├── exception/ (Custom exception handling)
│   │   │   ├── jpa/specification/ (JPA criteria queries)
│   │   │   ├── repository/ (Data repositories)
│   │   │   ├── request/ (Request payload models)
│   │   │   ├── response/ (Response payload models)
│   │   │   ├── services/ (Business logic implementation)
│   │   │   ├── utils/ (Utility classes)
│   │   │   ├── SwiggyApiApplication.java (Main application file)
│   │   ├── resources/
│   │   │   ├── application.properties (Application configuration)
│   │   │   ├── Banner.txt (Custom application banner)
│   ├── test/java/com/shivu/swiggy_api/
│   │   ├── SwiggyApiApplicationTests.java (Unit tests)
│── .gitignore
│── mvnw
│── mvnw.cmd
│── pom.xml (Maven dependencies and configuration)
│── README.md
```

## Technologies Used

- **Java 17**
- **Spring Boot 3.x**
- **Spring Security & JWT**
- **Spring Data JPA (Hibernate)**
- **MySQL**
- **Maven**

## Installation & Setup

### Prerequisites

Ensure you have the following installed:

- [Java 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)
- [Maven](https://maven.apache.org/)
- MySQL Database

### Steps to Run

1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/swiggy-api.git
   cd swiggy-api
   ```
2. Update `application.properties` with your MySQL configuration:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/swiggy_db
   spring.datasource.username=root
   spring.datasource.password=python
   spring.jpa.hibernate.ddl-auto=update
   spring.security.jwt.secret=mysecretkey
   ```
3. Build and run the application:
   ```sh
   mvn clean install
   mvn spring-boot:run
   ```

## API Endpoints

### Authentication

| Method | Endpoint     | Description       |
| ------ | ------------ | ----------------- |
| POST   | /auth/signup | User registration |
| POST   | /auth/signin | User login (JWT)  |

### Restaurant Management

| Method | Endpoint           | Description               |
| ------ | ------------------ | ------------------------- |
| POST   | /restaurant/signup | Register a restaurant     |
| GET    | /restaurant/all    | Get all restaurants       |
| PUT    | /restaurant/update | Update restaurant details |

### Order & Cart

| Method | Endpoint       | Description       |
| ------ | -------------- | ----------------- |
| POST   | /cart/add      | Add item to cart  |
| GET    | /cart/view     | View cart details |
| POST   | /order/place   | Place an order    |
| GET    | /order/history | View past orders  |

### Delivery Management

| Method | Endpoint           | Description                      |
| ------ | ------------------ | -------------------------------- |
| POST   | /deliveries/assign | Assign order to delivery partner |
| GET    | /deliveries/status | Check delivery status            |

### Review System

| Method | Endpoint     | Description                  |
| ------ | ------------ | ---------------------------- |
| POST   | /review/add  | Add a review                 |
| GET    | /review/view | Get reviews for a restaurant |

## Security & Authentication

- Uses **JWT-based authentication** for securing endpoints.
- User roles: **Admin, Restaurant, Customer, Delivery Partner**.
- Restricted API access based on roles.

## Exception Handling

Custom exceptions for:

- User authentication issues (`CustomAuthenticationException.java`)
- Cart-related errors (`CartException.java`)
- Order processing failures (`OrderException.java`)
- Restaurant-specific issues (`RestaurantException.java`)
- Payment failures (`PaymentException.java`)

## Contribution Guidelines

1. Fork the repository.
2. Create a feature branch (`feature-new`).
3. Commit changes with proper messages.
4. Push and create a Pull Request.

## License

This project is licensed under the **MIT License**.

---

### Author: ABHAY 

For any queries, feel free to contact me!



