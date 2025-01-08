# Calculator Unit Test Project

This project demonstrates how to write unit tests for a simple `Calculator` class using Java and JUnit 5. The `Calculator` class includes basic arithmetic operations, and the tests ensure the correctness of these operations, including edge cases.

## Features

### Calculator Class
The `Calculator` class provides the following methods:

- `add(int a, int b)`: Adds two integers.
- `subtract(int a, int b)`: Subtracts the second integer from the first.
- `multiply(int a, int b)`: Multiplies two integers.
- `divide(int a, int b)`: Divides the first integer by the second. Throws an `IllegalArgumentException` if the divisor is zero.

### Unit Tests
The project includes unit tests for all the methods of the `Calculator` class using **JUnit 5**.

## Project Structure

```
CalculatorProject/
├── src/
│   ├── main/
│   │   └── java/
│   │       └── Calculator.java
│   └── test/
│       └── java/
│           └── CalculatorTest.java
└── pom.xml
```

### `Calculator.java`
The main class containing arithmetic methods.

### `CalculatorTest.java`
The test class for validating the `Calculator` methods.

### `pom.xml`
Maven configuration file to manage dependencies and build the project.

## Getting Started

### Prerequisites

- Java Development Kit (JDK) 8 or higher
- Maven build tool

### Setup

1. Clone the repository or create the project structure manually.
2. Add the JUnit 5 dependency to the `pom.xml` file:

```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>5.9.3</version>
    <scope>test</scope>
</dependency>
```

3. Create the `Calculator` class in the `src/main/java/` directory:

```java
public class Calculator {

    public int add(int a, int b) {
        return a + b;
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    public int multiply(int a, int b) {
        return a * b;
    }

    public int divide(int a, int b) {
        if (b == 0) {
            throw new IllegalArgumentException("Divider cannot be zero");
        }
        return a / b;
    }
}
```

4. Create the `CalculatorTest` class in the `src/test/java/` directory:

```java
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class CalculatorTest {

    @Test
    public void testAdd() {
        Calculator calculator = new Calculator();
        assertEquals(5, calculator.add(2, 3), "2 + 3 should equal 5");
    }

    @Test
    public void testSubtract() {
        Calculator calculator = new Calculator();
        assertEquals(1, calculator.subtract(3, 2), "3 - 2 should equal 1");
    }

    @Test
    public void testMultiply() {
        Calculator calculator = new Calculator();
        assertEquals(6, calculator.multiply(2, 3), "2 * 3 should equal 6");
    }

    @Test
    public void testDivide() {
        Calculator calculator = new Calculator();
        assertEquals(2, calculator.divide(6, 3), "6 / 3 should equal 2");
    }

    @Test
    public void testDivideByZero() {
        Calculator calculator = new Calculator();
        assertThrows(IllegalArgumentException.class, () -> calculator.divide(6, 0), "Dividing by zero should throw IllegalArgumentException");
    }
}
```

5. Run the tests using your IDE or Maven:

```bash
mvn test
```

## Expected Output

All tests should pass if the `Calculator` methods are implemented correctly:

```
[INFO] Tests run: 5, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.015 s
[INFO] BUILD SUCCESS
```

## Learning Outcomes

- How to write and structure unit tests in Java using JUnit 5.
- How to handle edge cases, such as division by zero.
- How to integrate and run tests in a Maven project.

## License
This project is licensed under the MIT License. Feel free to use and modify it as needed!

## Project Structure
![Screenshot (12)](https://github.com/user-attachments/assets/5a9f72a1-811b-4780-8b18-e6746fdb72b0)


