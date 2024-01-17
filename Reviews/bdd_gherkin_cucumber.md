# BDD - Gherkin / Cucumber
## Orientation
---
- **BDD**
  - Behavioral Driven Development
  - Emphasizes collaboration between developers, testers, and business stakeholders to ensure software meets business requirements
  - Focuses on defining and describing software behavior in terms of user scenarios and interactions
  - BDD focuses on describing the behavior of a system from a user's perspective in a way that is easy to understand and can be translated into automated tests
  - Here are some key features of BDD:
    - **User-focused** 
      - BDD places the user at the center of the software development process. This means that requirements and tests are expressed in terms of user stories and scenarios, rather than technical specifications.
    - **Collaborative** 
      - BDD encourages collaboration among developers, quality assurance engineers, and non-technical stakeholders. By involving everyone in the process, BDD can help ensure that everyone is on the same page and that the system is being developed to meet everyone's needs.
    - **Automated** 
      - BDD involves writing automated tests that can be run against the system to verify that it meets the requirements. By automating tests, BDD can help catch bugs early in the development process.
    - **Gherkin syntax** 
      - BDD tests are often written using Gherkin syntax, which is a plain-text language that is easy to understand for both technical and non-technical stakeholders.
- **Gherkin**
  - Business readable language used to define scenarios in BDD, it is **not** a programming language
  - Uses a simple syntax that is easily understandable by non-technical stakeholders, as well as developers and testers
  - Consists of a few basic keywords to describe the behavior of the system under test, to provide a clear understanding of the expected behaviors of the system
## Cucumber
---
- **Cucumber**
  - Cucumber is an open-source testing framework that supports BDD
  - It is based on the Gherkin language and provides a way for stakeholders to easily understand and participate in the testing process
  - Cucumber allows the team to write automated tests in a natural language syntax that can be easily understood by all stakeholders
  - Here are some key features of Cucumber:
    - Supports various programming languages such as Java, Ruby, Python, JavaScript, etc.
    - Integrates with multiple testing frameworks such as JUnit and TestNG
    - Provides a way for non-technical stakeholders such as business analysts, product owners, and domain experts to participate in the testing process by writing feature files in Gherkin syntax.
    - Offers the ability to generate user-friendly reports for test results.
    - Provides support for both Web and API automation testing.
- **Feature File**
  - The feature file is a text file that contains a list of scenarios written in the Gherkin syntax
  - It defines the ebhavior of the software from a user's perspective
  - There should be a clear and concise description of how the feature should be tested
- **Given**
  - Keyword used in Gherkin syntax to describe the initial state of the system
  - Indicates what preconditions must be met before the test scenario can be executed
    - ```gherkin
      Given the user is on the login page
      Given the user is logged in
- **When**
  - Keyword used in Gherkin syntax to describe the action or event that triggers the system behavior
  - Describes what the user is doing to interact with the system
    - ```gherkin
      When the user enters valid credentials
      When the user clicks the submit button
- **Then**
  - Keyword used in Gherkin syntax to describe the expected outcome of the system behavior
  - Indicates the expected result or state of the system after the action or event described in the When step
    - ```gherkin
      Then the user is redirected to the home page
      Then an error message is displayed
- **Scenario**
  - Keyword used in Gherkin syntax to define a specific test scenario
  - Describes a particular set of conditions and actions to be tested
    - ```gherkin
      Scenario: Login with valid credentials
      Scenario: View profile information

- **Example Feature File**
  - ```gherkin
    Feature: Login
        As a user
        I want to login to my account
        So that I can access my account information
    
        Scenario: Login with valid credentials
            Given the user is on the login page
            When the user enters valid credentials
            And the user clicks the submit button
            Then the user is redirected to the home page
    
        Scenario: Login with invalid credentials
            Given the user is on the login page
            When the user enters invalid credentials
            And the user clicks the submit button
            Then an error message is displayed
  - This feature file is then used to create a step definition file in Java using Cucumber
  - ```java
    public class LoginStepDefinitions {
        
        @Given("the user is on the login page")
        public void navigateToLoginPage() {
            // Code to navigate to the login page
        }
    
        @When("the user enters valid credentials")
        public void enterValidCredentials() {
            // Code to enter valid credentials
        }
    
        @When("the user clicks the submit button")
        public void clickSubmitButton() {
            // Code to click the submit button
        }
    
        @Then("the user is redirected to the home page")
        public void verifyHomePage() {
            // Code to verify the user is on the home page
        }
    
        @Then("an error message is displayed")
        public void verifyErrorMessage() {
            // Code to verify an error message is displayed
        }
    }
## Integration
---
- **Glue Code**
  - Glue code is the code that links the feature files and the step definitions
  - It acts as a bridge between feature files and the Java code that runs the tests
  - It is written in Java and is used to match the steps in the feature files to their corresponding Java methods
  - It uses annotations to match the steps
    - `@Given`, `@When`, and `@Then` annotations are used to match the steps
- **Step Implementations**
  - Step implementations are the Java methods that are executed when a step in a feature file is matched
  - They contain the actual test code that runs the tests
    - ```java
      @Given("the user is on the login page")
      public void userIsOnLoginPage() {
          driver.get("https://example.com/login");
      }
- **JUnit Runner**
  - The JUnit Runner is a class that runs the feature files and executes the step definitions
  - It is used to define the test suite and to configure the test execution
  - It uses annotations to specify which feature files and step definition classes to run
    - ```java
      import org.junit.runner.RunWith;
      import io.cucumber.junit.Cucumber;
      import io.cucumber.junit.CucumberOptions;
      
      @RunWith(Cucumber.class)
      @CucumberOptions(
          features = "src/test/resources/features",
          glue = {"com.example.stepdefinitions"}
      )
      public class CucumberRunner {
      }
    - Make sure to import [`cucumber-junit`](https://mvnrepository.com/artifact/io.cucumber/cucumber-junit) and [`junit-vintage-engine`](https://mvnrepository.com/artifact/org.junit.vintage/junit-vintage-engine) dependencies as well
    - `@RunWith(Cucumber.class)`
      - Specifies the Cucumber class as an extension to JUnit5
    - `@CucumberOptions`
      - Allows us to specify the options for Cucumber
    - `features`
      - The location of the feature files
    - `glue`
      - The packages where the step definitions are located
    - There are other options as well such as `tags`, `plugin`, `monochrome`, etc.
- **Scenario Outline**
  - A Scenario Outline is a way to run the same scenario with different input values
  - It is used when you want to test the same functionality with different input values
  - It is defined using the Scenario Outline keyword in the feature file
  - The input values are defined using placeholders in the feature file, which are replaced by the actual values during execution
    - ```gherkin
      Scenario Outline: Login with different users
        Given the user is on the login page
        When they enter "<username>" and "<password>"
        Then they should be logged in
        
        Examples:
        | username | password |
        | user1    | pass1    |
        | user2    | pass2    |
        | user3    | pass3    |