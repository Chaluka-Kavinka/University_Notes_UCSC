# 1 What is a Requirement?

Requirements reflect the **needs of customers** for a system that serves a specific purpose, such as controlling a device, placing an order, or finding information. They can range from a high-level abstract statement of a service or constraint to a detailed, mathematical functional specification.

# 2 What is Requirements Engineering (RE)?

Requirements Engineering is the systematic process of **finding out, analyzing, documenting, and checking** the services a system should provide and the constraints under which it must operate and be developed.

# 3 Types of Requirements

The sources categorize requirements in two primary ways: by their level of detail (User vs. System) and by their nature (Functional vs. Non-Functional).

## A. User Requirements vs. System Requirements

- **User Requirements:** High-level statements in natural language (plus diagrams) of what services the system is expected to provide and its operational constraints. They are written for customers and managers.
    - _Example:_ "The Mentcare system shall generate monthly management reports showing the cost of drugs prescribed by each clinic".
- **System Requirements:** More detailed descriptions of the system’s functions, services, and operational constraints. They define exactly what is to be implemented and often serve as part of the contract between the client and the developer.

## B. Functional vs. Non-Functional Requirements

- **Functional Requirements:** Describe the **functionality or system services**—what the system should actually do.
    - _Example:_ "Registered users shall be able to login with a valid username and password".
- **Non-Functional Requirements (NFRs):** These define **how the system performs** rather than what it does. They often relate to the system as a whole rather than individual features (e.g., security, reliability, or response time).

# 4 Stakeholders

A stakeholder is any **individual or organization** actively involved in a project, or whose interests may be affected by the system's execution or completion. Identifying stakeholders is crucial for gathering complete requirements.

- **Examples in a medical system (MHC-PMS):** Patients, doctors, nurses, medical receptionists, IT staff, and medical ethics managers.

# 5 The Requirements Engineering Process

The RE process is not a single step but a cycle involving several key activities:

1. **Elicitation and Analysis:** Working with stakeholders to discover their requirements.
2. **Specification:** Documenting the requirements in a way that is understandable to both users and developers.
3. **Validation:** Checking the requirements to ensure they truly define the system that the customer wants.
4. **Management/Change:** Managing changes to these requirements as the project evolves.

## Characteristics of "Good" Requirements:

- **Clear and Comprehensible:** Easy to understand without ambiguity.
- **Complete:** They cover all needs.
- **Necessary and Traceable:** Each requirement should have a clear purpose and be trackable throughout the project.
- **Testable:** It must be possible to verify that the requirement has been met.