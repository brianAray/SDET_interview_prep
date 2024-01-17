# JUnit
- **Intro to JUnit**
    - JUnit is a unit testing framework for the java programming language
    - It is widely used for writing and executing automated tests for Java
    - Some key features of JUnit
        - **Assertions**
            - Ways to verify the expected output of a test case
        - **Test fixtures**
            - JUnit provided annotations to define the setup and teardown methods that will be executed before and after each test method
        - **Test suits**
            - A way to group multiple test cases together and execute them as a suite
        - **Test runners**
            - Several test runners that can be used to exectue test cases and generate reports
- **Annotations & Assertions**
    - Annotations:
        - `@Test`: used to signal that the annotated method is a test method.
        - `@BeforeEach`: used to signal that the annotated method should be executed before each test method in the current test class.
        - `@AfterEach`: used to signal that the annotated method should be executed after each test method in the current test class.
        - `@BeforeAll`: used to signal that the annotated method should be executed before any test methods in the current test class.
        - `@AfterAll`: used to signal that the annotated method should be executed after all test methods in the current test class have been run.
    - Assertions:
        - `assertEquals(expected, actual)`: checks that the expected value is equal to the actual value.
        - `assertTrue(condition)`: checks that the given condition is true.
        - `assertFalse(condition)`: checks that the given condition is false.
        - `assertNull(object)`: checks that the given object is null.
        - `assertNotNull(object)`: checks that the given object is not null.
        - `assertSame(expected, actual)`: checks that the expected object and the actual object are the same.
        - `assertNotSame(expected, actual)`: checks that the expected object and the actual object are not the same.
    - ```java
      import org.junit.jupiter.api.Assertions;
      import org.junit.jupiter.api.Test;
      
      public class MathUtilsTest {
          
          @Test
          public void testAdd() {
              MathUtils mathUtils = new MathUtils();
              int result = mathUtils.add(2, 3);
              Assertions.assertEquals(5, result, "The result should be 5");
          }
          
          @Test
          public void testDivide() {
              MathUtils mathUtils = new MathUtils();
              Assertions.assertThrows(ArithmeticException.class, () -> mathUtils.divide(1, 0), "Divide by zero should throw ArithmeticException");
          }
          
          @Test
          public void testMultiply() {
              MathUtils mathUtils = new MathUtils();
              int result = mathUtils.multiply(2, 3);
              Assertions.assertEquals(6, result, "The result should be 6");
          }
      }
- **Intro to TDD**
    - Test-driven Development (TDD) is a software development process that emphasizes the creation of automated tests before actually writing code
    - You create small units of functionality and test them continuously in an iterative process throughout development
    - The TDD process typically involves these steps:
        1. **Write a failing test**
            - Start by writing a test that specifies the desired behavior of the code
            - The test should fail initially as no code has been written yet to implement the functionality
        2. **Write the code**
            - Write the minimum amount of code necessary to pass the test
            - This ensures that the code is testable and that the test is effective
        3. **Run the tests**
            - Run all of the tests to ensure that the new code does not break any existing functionality
        4. **Refactor the code**
            - Once the new code passes all of the tests, it can be refactored to improve its quality and readability
        5. **Repeat**
            - Repeat the process for each new feature or functionality that needs to be added to the codebase
    - Benefits of TDD:
        - **Improved code quality**
            - It encourages developers to write clean, modular, and testable code
        - **Faster development**
            - It helps catch bugs earlier in the development process, which leads to faster feedback and faster development cycles
        - **Improved documentation**
            - Tests serve as documentation for the codebase, making it easier for new developers to understand how the code works
        - **Increased confidence**
            - By writing tests that cover all aspects of the codebase, developers can be more confident in the quality of their code
    - An example of TDD:
        1. **Write a failing test**
            - ```java
              @test
              public void testSum() {
                Calculator calculator = new Calculator();
                int sum = calculator.sum(2, 3);
                assertEquals(5, sum);
              }
        2. **Write the code**
            - ```java
              public class Calculator {
                public int sum(int a, int b){
                    return a + b;
                }
              }
        3. **Run the tests**
            - ```
              Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
        4. **Refactor the code** (none needed in this example)
        5. **Repeat** for any additional functionality that needs to be added