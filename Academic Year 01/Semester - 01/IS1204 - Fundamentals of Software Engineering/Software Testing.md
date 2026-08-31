# 1 Understanding Software Testing

**Software testing** is the process of executing a program or application with the intent of finding **software bugs**—errors or flaws that cause incorrect or unexpected results. It is important to note that testing can reveal the presence of errors, but it can never prove their absolute absence; you cannot claim a system is 100% bug-free.

## Why Testing is Critical:

- **Reliability:** Ensures the application handles hundreds of users as effectively as it handles one.
- **Compatibility:** Confirms the software works across different devices, browsers, and operating systems.
- **Safety:** In safety-critical systems, such as flight traffic control, testing prevents glitches that could lead to injury or death.
- **Business Success:** High-quality products increase customer satisfaction, protect reputation, and lower long-term maintenance costs.

# 2 Verification and Validation (V&V)

Testing is part of a broader process known as **Validation and Verification**, which aims to ensure a system is "fit for purpose".

- **Verification ("Are we building the product right?"):** Ensuring the software conforms to its technical specifications.
- **Validation ("Are we building the right product?"):** Ensuring the software does what the user actually requires.

# 3 Testing Techniques

- **Static Techniques (Software Inspections):** Analysis of the system (requirements, design, or code) without executing it. Inspections are effective for finding errors and checking compliance with standards and maintainability before implementation.
- **Dynamic Techniques (Defect Testing):** Exercising the system with test data and observing its operational behavior to find defects.

# 4 Stages of the Testing Process

Software is tested at three distinct stages to ensure comprehensive coverage:

**1. Development Testing:** Activities carried out by the development team during the build phase.

- **Unit Testing:** Testing individual functions, methods, or object classes in isolation. This is often **automated** using frameworks like JUnit so tests can run without manual intervention.
- **Component Testing:** Focusing on several interacting objects. Testing ensures the **component interface** behaves according to its specification.
- **System Testing:** Integrating components to test the complete system as a whole. The focus is on component interactions and the **emergent behavior** of the system.

**2. Release Testing:** A separate team (not involved in development) tests a complete version before it is released.

- **Goal:** To convince stakeholders that the system is "good enough" for external use.
- **Requirements-Based Testing:** Examining each requirement and developing a specific test for it.
- **Performance Testing:** Increasing the load steadily to test the system’s limits and failure behavior (Stress Testing).

**3. User Testing:** Users or customers test the system in their own actual working environment.

- **Alpha Testing:** Users work with the development team at the developer's site.
- **Beta Testing:** A release is provided to users to experiment with and report problems.
- **Acceptance Testing:** The final step where customers decide if the system is ready to be deployed.


# 5 Test-Driven Development (TDD)

TDD is an iterative approach where you **write a test before writing the actual code**.

- **Process:** Identify a small increment of functionality -> Write a test (it will initially fail) -> Implement the code -> Re-run tests until they pass.
- **Key Benefits:**
    - **Code Coverage:** Every segment of code has at least one associated test.
    - **Simplified Debugging:** When a test fails, it is obvious where the problem lies.
    - **Regression Testing:** A suite of tests is built incrementally to ensure new changes do not "break" previously working code.

# 6 Methodologies: Black Box vs. White Box

- **Black Box Testing:** Focuses on functionality based on specifications and requirements without peering into the internal code. The tester knows _what_ the software should do but not _how_ it does it.
- **White Box Testing:** Also known as structural testing, it tests the internal structures, workings, and logic of the application.