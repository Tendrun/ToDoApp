# ToDoApp

A simple **Spring Boot 3** + **Spring Security** backend project (Maven) that exposes a few demo HTTP endpoints and protects them with authentication.

> Repo: `Tendrun/ToDoApp`

## What this project is

This repository is a starter/demo backend application built with:

- **Spring Boot 3.3.5** (Maven)
- **Spring Web** (REST endpoints)
- **Spring Security** (basic authentication / form login)

It includes a minimal controller (`GreetingsController`) and a basic `SecurityFilterChain` configuration (`SecurityConfig`) that requires authentication for every request.

## Features

- ✅ Spring Boot application entry point (`DemoApplication`)
- ✅ Example endpoints returning simple text responses
- ✅ Spring Security enabled
- ✅ All endpoints require authentication (`anyRequest().authenticated()`)
- ✅ Supports **form login** and **HTTP Basic**

## Tech Stack

- Java
- Spring Boot
- Spring Web
- Spring Security
- Maven

## Project Structure

```
ToDoApp/
├── pom.xml
└── src/
    ├── main/
    │   ├── java/com/example/demo/
    │   │   ├── DemoApplication.java
    │   │   ├── config/SecurityConfig.java
    │   │   └── controllers/GreetingsController.java
    │   └── resources/
    │       └── application.properties
    └── test/
        └── java/com/example/demo/
            └── DemoApplicationTests.java
```

## API Endpoints

### `GET /hello`
Returns a greeting.

- Query param: `myName` (optional, default: `World`)
- Response example: `Hello World!`

### `GET /`
Returns a greeting.

- Query param: `test` (optional, default: empty string)
- Response example: `Hello !` / `Hello abc!`

### `GET /api/v1/greetings/say-good-bye`
Returns a goodbye message.

- Response example: `Goodbye World!`

## Security

Security is configured in:

- `src/main/java/com/example/demo/config/SecurityConfig.java`

Behavior:

- `anyRequest().authenticated()` → **every endpoint requires authentication**
- `formLogin()` enabled
- `httpBasic()` enabled

That means if you call an endpoint without credentials, you should get a `401 Unauthorized`.

## Running locally

### Prerequisites

- Java 17+ (recommended for Spring Boot 3)
- Maven (or use the included Maven Wrapper)

### Run the app

Using Maven Wrapper:

```bash
./mvnw spring-boot:run
```

Or using Maven:

```bash
mvn spring-boot:run
```

The app will start on port **8080** by default.

## Testing

```bash
./mvnw test
```

## Notes / Next Steps (optional ideas)

If you want to turn this into a real ToDo backend API, typical next steps would be:

- Add Task model/entity + repository (e.g., JPA + PostgreSQL/H2)
- Add REST endpoints: create/update/delete/list tasks
- Replace default form/basic auth with JWT authentication
- Add CORS config for a React frontend

---

**Last updated:** December 2024
