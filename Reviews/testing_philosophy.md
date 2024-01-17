# Testing Philosophy
## Testing Mindset
---
- **Developer Mindset**
    - Testing should be approached like writing code, with a focus on quality and defect prevention. 
    - Developers should take ownership of the quality of the software they produce and strive to prevent defects from occurring.
- **Test Mindset**
    - Having a mindset focused on testing and quality is essential for producing reliable software. 
    - Considering testing and quality throughout the entire software development life cycle, not just during testing phases.
## Why Test
---
- **Objectives of Testing**
    - The objective of software testing is to ensure that the software meets the desired quality and functionality. This includes:
        - Verifying that the software satisfies the specified requirements
        - Verify the software is reliable
        - Verify that it performs as expected
- **Quality Management**
    - Quality management involves the processes for ensuring that the software meets the required quality standards. It includes:
        - The Development of Quality Control Procedures
        - Test Planning
        - Test Execution.
- **Verification vs Validation**
    - Verification is concerned with ensuring that the software is built correctly and meets the specified requirements.
        - ```md
          > The requirement is that a login page should have two fields for username and password
          > Verification involves checking if the login page has two fields
    - Validation is concerned with ensuring that the right software is built and meets the needs of the user.
        - ```md
          > The user needs to be able to login to the system quickly and easily
          > Validation involves checking if the login page is intuitive, and the process is fast and efficient 
## Testing Principles
---
- **Test Reveals Defects not their absence**
    - Testing is a process of finding defects, not proving perfection. 
    - No matter **how** comprehensive the testing is, it is **impossible** to ensure that the software is entirely error-free.
- **Exhaustive Testing is impossible**
    - It is **impossible** to test the software exhaustively, covering every possible input and scenario. 
    - Testing should be done strategically, focusing on the most critical and high-risk areas of the software.
- **Test Early**
    - Testing should be done as early as possible in the software development life cycle. 
    - This helps to prevent defects from propagating and becoming more expensive to fix.
- **Defect Cluster**
    - Defects often cluster around a specific area of code or functionality. 
    - Identifying these clusters can help to prioritize testing efforts and allocate resources more effectively.
    - Example:
        - ```md
          > A software is designed to handle user registration and login. 
          > During testing, testers find that there are several defects related to the password reset functionality:

          - The password reset link is not being sent to the user's email address
          - The password reset link is not valid when the user clicks on it
          - The user's password is not being reset correctly
- **Pesticide Paradox**
    - The Pesticide Paradox refers to the fact that repeating the same tests only finds the same defects. 
    - To ensure that testing is effective, testing strategies should evolve and change over time.
- **Test Context**
    - The environment in which software is tested includes hardware and software configurations, as well as other external factors that can affect the software's performance and behavior.
- **Absence of error fallacy**
    - Passing a test does not mean that there are no defects in the software. 
    - It is possible that the testing did not cover all possible scenarios or that some defects were missed.