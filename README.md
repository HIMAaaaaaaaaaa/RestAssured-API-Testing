
# RestAssured API Testing

## Overview
This project involves automation testing of specific APIs for a website called "Learning Curve," which focuses on training and educating employees. The goal is to ensure that the APIs work correctly according to the specified requirements. The tests are written using the RestAssured library, which allows for seamless interaction with the APIs.

## Goal
The main objective of the project is to validate the functionality of the APIs by performing various types of tests. This includes checking the responses for different HTTP methods (GET, POST) and ensuring that the APIs behave as expected based on their specifications.

## Features
- Automation testing of APIs using RestAssured
- Supports various HTTP methods:
  - **GET**: Retrieve data from the API
  - **POST**: Send data to the API
- Written in Java and organized using Maven
- Tests can be run using TestNG or JUnit (if applicable)

## Tools Used
- **RestAssured** for API testing
- **Java** as the programming language
- **TestNG or JUnit** for organizing and executing tests
- **Maven** for project management
- **IntelliJ** as the development IDE
- **JDK 22** for the Java Development Kit

## Getting Started
To run the project locally:
1. Clone the repository.
2. Ensure you have JDK 22 installed and configured.
3. Navigate to the project directory.
4. Use Maven to run the tests with the following command:
   ```bash
   mvn test
   ```

## API Testing Examples
Here are some examples of the tests implemented in the project:

### Example 1: Testing GET Method
```java
import io.restassured.RestAssured;
import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;

public class GetAPITest {
    @Test
    public void testGetAPI() {
        RestAssured.given()
            .when()
                .get("/api/endpoint")
            .then()
                .statusCode(200)
                .body("key", equalTo("value"));
    }
}
```

### Example 2: Testing POST Method
```java
import io.restassured.RestAssured;
import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;

public class PostAPITest {
    @Test
    public void testPostAPI() {
        RestAssured.given()
            .contentType("application/json")
            .body("{\"key\":\"value\"}")
            .when()
                .post("/api/endpoint")
            .then()
                .statusCode(201);
    }
}
```

## Future Enhancements
- Expand test coverage to include more APIs
- Implement additional testing scenarios and edge cases
