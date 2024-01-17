# Test Case Design
## Terminology
---
- **High Level Testcase**
    - Test case that covers broad functionality of the system
    - Example: 
        - ```md
          # Login Functionality 
          - This test case would cover the entire login process, from entering valid/invalid credentials to successful login/logout

          # Registration Functionality
          - This would cover the entire registration process, from entering user information, validating it, then successfully registering
- **Low Level Testcase**
    - Test case that covers specific functionality of the system
    - Example: 
        - ```md
          # Button click event
          - This test case would ensure that clicking on a button would perform the expected action or event

          # Input Validation
          - This test case would ensure that invalid inputs are detected and handled properly by the system
          - This could include testing for input field length limits, data type validation, and character restrictions
- **Test Basis**
    - The test basis is the set of requirements and specifications used as the basis for creating test cases.
    - These would include:
        - **Requirements specification**
            - Outlines the functionality and features that the software system is intended to have
        - **Design specification**
            - Outlines the technical design of and architecture of the software system
        - **User stories**
            - Used in agile to for describing the user requirements and validate their interactions in test cases
        - **Use cases**
            - Used to describe interactions between users and the software
        - **Functional requirements**
            - Describe the behavior and functionality of the software
        - **Non-functional requirements**
            - Describe the non-functional requirements like performance, usability, etc
        - **Existing software system**
            - If system already exists, use test cases to ensure the system continues to function as intended
- **Test Objective**
    - The test objective is the goal of a specific test case. It specifies what is being tested, how it is being tested, and what the expected outcome is.
- **Test Suite**
    - A test suite is a collection of test cases used to test a software system.
- **Test Data**
    - Data used in testing, including input data and expected output data
- **Test Object**
    - The test object is the software or system being tested.
- **Error/Defect/Failure**
    - An error is a mistake in the code, a defect is a problem in functionality, and a failure is when the software does not behave as expected.
    - **Error**
        - Developer accidentally types the wrong variable name in their code, system fails to compile
    - **Defect**
        - In an e-commerce website, the "Add to cart" button is not functioning correctly, and doesn't add the selected item to cart preventing user from purchasing
    - **Failure**
        - A user tries to book a hotel room, the software crashes during the booking process and the user cannot book a room
- **Use Case Stories**
    - Use case stories are a way of describing the functionality of a system from the user's perspective. 
    - They help to ensure that the software meets the needs of the user and that the user's requirements are translated into software specifications.
        - ```md
          "As a customer, I want to be able to add items to my shopping cart, so that I can purhcase them all at once"

          1. Test case: Add item to cart
            - Pre-condition: User is logged in and on product page
            - Steps: Click "Add to Cart" button
            - Expected result: Item is added to cart and cart count is updated
          
          2. Test case: Remove item from cart
            - Pre-condition: User has items in cart
            - Steps: Click "Remove" button next to item
            - Expected result: Item is removed from cart and cart count is updated
          
- **Requirements Traceability Matrix**
    - A Requirements Traceability Matrix (RTM) is a tool used to track requirements through the software development process.
    - It ensures that all requirements are met and that changes to requirements are properly tracked and managed.

## Technique
---
- **Equivalence Partitioning**
    - Equivalence partitioning is a testing technique that divides input values into equivalent groups to reduce the number of test cases required.
        - ```md
          > There is a login page of an application that requires a username and password
          
          The input values for the username and password can be divided into three equivalent groups:
          
          # Valid
            - Input values that are expected to be accepted by the system
            - Example: 
                - username: "john.doe"
                - password: "Password123"
          
          # Invalid
            - Input values that are expected to be rejected by the system
            - Example: 
                - username: "jo"
                - password: "pass"
                - These could be rejected based on not enough characters or missing types of characters like numbers

          # Boundary
            - Input values that are on the edge of the input range
            - Example: A boundary value for username could be a string that is exactly 20 characters long if the system accepts only between 5 - 20 characters 
- **Boundary Value Analysis**
    - Boundary Value Analysis is a testing technique that focuses on values at the boundary between valid and invalid input. 
    - It helps to identify defects that may arise from the software's handling of boundary values.
- **Decision Tables**
    - Decision Tables are a tool used to map out different conditions and actions of a software system.
    - They are useful for complex decision-making scenarios and help to ensure that all possible scenarios are covered in testing.
- **State Transition Diagrams**
    - State Transition Diagrams are a visual representation of the different states of a software system and how it transitions between them. 
    - They help to identify defects related to the system's behavior and transitions between different states.
- **Checklist Testing**
    - Checklist Testing is a testing technique that involves using a list of items to ensure that all necessary testing has been done. 
    - It helps to ensure that no critical areas are missed during testing.
- **Positive Testing**
    - Positive Testing is a testing technique that involves testing software with valid inputs to ensure that it behaves as expected. 
    - It helps to verify that the software functions correctly under normal operating conditions.
        - ```md
          > A website has a login page that requires a username and password

          Positive testing for this could include the following test cases:

            - Enter a valid username and password and get a successful verification
            - Enter a valid username and an incorrect password and verify the error message is displayed
            - Enter an incorrect username and password and verify the error message is displayed
- **Negative Testing**
    - Negative Testing is a testing technique that involves testing software with invalid inputs to ensure that it handles errors properly. 
    - It helps to identify defects related to error handling and exception handling.
        - ```md
          > A website has a login page that requires a username and password

          Negative testing for this could include the following test cases:

            - Enter a blank username and password and verify that the error message is displayed
            - Enter a valid username and a blank password and verify the error message is displayed
            - Enter a username longer than the allowed length and verify the error message is displayed
- **Experience Based Testing**
    - Testing based on experience, intuition, and knowledge gained through testing similar systems
    - Types:
        - Error guessing: testers predict and test for potential errors
        - Exploratory testing: testing approach that emphasizes learning, investigation, and experimentation to uncover defects
- **Risk Based Testing**
    - Testing that prioritizes tests based on risks associated with different parts of the software system
    - Process:
        - Identify potential risks associated with the software systems
        - Determine the likelihood and impact of each risk
        - Prioritize testing based on the level of risk associated with each area of the software system
- **Localisation Testing**
    - Testing approach that ensures software can be used effectively in different locales and languages
    - Process:
        - Test software with different locale and language settings to ensure that the software functions as expected
        - Test localized content (e.g. translated text) for accuracy, formatting, and readability
        - Test for any potential cultural or regional issues (e.g. date formats, currency symbols)
- **Accessibility Testing**
    - Testing approach that ensures software can be used effectively by users with disabilities
    - Process:
        - Test software with different accessibility settings (e.g. screen readers, voice recognition software) to ensure that the software functions as expected
        - Test for compliance with accessibility standards and guidelines (e.g. WCAG 2.1)
        - Test for any potential accessibility issues (e.g. color contrast, font size)
- **A-B Testing**
    - Testing approach that compares two versions of the software system to determine which performs better
    - Process:
        - Develop two versions of the software system (e.g. different user interfaces, pricing strategies, marketing campaigns)
        - Randomly assign users to each version and gather data on user behavior and performance metrics
        - Analyze data to determine which version performs better
- **Static Testing vs Dynamic Testing**
    - Static Testing examines code without executing it, while Dynamic Testing examines code as it's being executed.
    - The goal of static testing is to find defects early in the development process before the code is executed
    - It has several advantages:
        - Finding defects earlier in the development cycle
        - Lower cost than dynamic testing
        - CAn be used in all phases of the development cycle
    - Dynamic testing tries to find defects by observing the behavior of the system
    - The different types of dynamic testing include:
        - Functional testing
        - Integration testing
        - Performance testing
        - Security testing
    - Advantages of dynamic testing:
        - Identifying defects that may not be found through static testing
        - Providing real-time feedback on software behavior
        - Can measure system performance and reliability
- **Static Testing Workflow**
    - The Static Testing Workflow is the process of reviewing code before it's executed. 
    - It includes:
        - Code reviews
        - Walkthroughs
        - Inspections