# Task1_Java_Proj

Task 1 for the Java course at Vistula University.
Author: Danylo Kholodtsov, 76822

## About

This is a simple Spring Boot web application. It has one controller that shows a greeting page. The page says hello to the name you pass in the URL, and also shows some text and a picture.

The project uses Java 25, Spring Boot 4.1.2, Spring MVC, Thymeleaf and Lombok. It is built with Maven, and the Maven wrapper is included, so you don't need to install Maven yourself.

The request is handled by HelloController.java in src/main/java/pl/edu/vistula/task1_java_proj/controller. The page itself is greeting.html in src/main/resources/templates, and the picture is k2.jpg in src/main/resources/static/images.

## How to run

You need JDK 25 installed.

Clone the repository and go into the project folder, then start the app with the Maven wrapper.

On Windows:

```
mvnw.cmd spring-boot:run
```

On Linux or macOS:

```
./mvnw spring-boot:run
```

You can also open the project in IntelliJ IDEA and run the Task1JavaProjApplication class.

The app starts on port 8080.

## How to use

Open http://localhost:8080/greeting in your browser. You will see "Hello, World!".

To change the name, add the name parameter to the URL, for example http://localhost:8080/greeting?name=Vistula. The page will then show "Hello, Vistula!".

The controller takes the name from the URL (or uses World if there is no name), puts it into the model and returns the greeting view. Thymeleaf then puts the name into the page.

## Tests

To run the tests:

```
./mvnw test
```
