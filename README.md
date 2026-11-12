# Task 1 – Spring Boot Greeting App

A simple web application built with **Spring Boot**, **Spring MVC** and **Thymeleaf**.
It serves a greeting page that welcomes the user by name and shows an image.

Author: Danylo Kholodtsov (76822), Vistula University

## Features

- `GET /greeting` returns an HTML page rendered by Thymeleaf
- An optional `name` query parameter personalizes the greeting (the default is `World`)
- A static image (`/images/k2.jpg`) is served from `src/main/resources/static`

## Tech stack

| Component      | Version / Details                    |
|----------------|--------------------------------------|
| Java           | 25                                   |
| Spring Boot    | 4.1.2                                |
| Web            | Spring MVC (`spring-boot-starter-webmvc`) |
| Templates      | Thymeleaf                            |
| Build tool     | Maven (Maven Wrapper included)       |
| Other          | Lombok                               |

## Project structure

```
src/
├── main/
│   ├── java/pl/edu/vistula/task1_java_proj/
│   │   ├── Task1JavaProjApplication.java   # Application entry point
│   │   └── controller/
│   │       └── HelloController.java        # Handles the /greeting endpoint
│   └── resources/
│       ├── application.properties          # Application configuration
│       ├── static/images/k2.jpg            # Static image shown on the page
│       └── templates/greeting.html         # Thymeleaf view
└── test/
    └── java/pl/edu/vistula/task1_java_proj/
        └── Task1JavaProjApplicationTests.java
```

## Requirements

- JDK 25 or newer
- No separate Maven installation is needed, because the project includes the Maven Wrapper (`mvnw` / `mvnw.cmd`)

## How to run

1. Clone the repository:

   ```bash
   git clone https://github.com/WaweLone/-Task1_Java_Proj.git
   cd -- -Task1_Java_Proj
   ```

2. Start the application:

   **Linux / macOS**
   ```bash
   ./mvnw spring-boot:run
   ```

   **Windows**
   ```cmd
   mvnw.cmd spring-boot:run
   ```

   You can also open the project in IntelliJ IDEA and run `Task1JavaProjApplication`.

3. The application starts on port **8080** by default.

## How to use

Open a browser and go to:

| URL | Result |
|-----|--------|
| http://localhost:8080/greeting | Shows `Hello, World!` |
| http://localhost:8080/greeting?name=Vistula | Shows `Hello, Vistula!` |
| http://localhost:8080/greeting?name=Danylo | Shows `Hello, Danylo!` |

The page shows the greeting, a short paragraph of text and an image.

## How it works

1. A request to `/greeting` is handled by `HelloController.greeting(...)`.
2. The controller reads the `name` request parameter (or uses `World` if it is missing) and adds it to the `Model`.
3. The controller returns the view name `greeting`, so Spring renders `templates/greeting.html`.
4. Thymeleaf puts the value into the page with `th:text="'Hello, ' + ${name} + '!'"`.

## Building and testing

Run the tests:

```bash
./mvnw test
```

Build an executable JAR:

```bash
./mvnw clean package
java -jar target/Task1_Java_Proj-0.0.1-SNAPSHOT.jar
```
