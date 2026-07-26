# 1 What is a Software Process?

A software process is a set of **ordered tasks** involving activities, constraints, and resources that produce a software system. It provides consistency and structure to development. Because it describes the life of a product from conception through delivery and maintenance, it is often referred to as a **Software Development Life Cycle (SDLC)**.

Regardless of the model chosen, all processes involve four fundamental activities:

1. **Specification:** Defining what the system should do.
2. **Design and Implementation:** Organizing and building the system.
3. **Validation:** Checking that the system meets customer needs.
4. **Evolution:** Modifying the system as requirements change.

# 2 Categories of Process Models

Process models generally fall into two broad categories:

- **Plan-driven processes:** All activities are planned in advance, and progress is measured against this fixed plan.
- **Agile processes:** Planning is incremental, making it easier to adapt to changing requirements.

# 3 Traditional Plan-Driven Models

## A. The Waterfall Model

The first published process model, the Waterfall model, is a **linear sequential model** where each phase must be completed before the next begins.

- **Phases:** Requirements -> Design -> Implementation -> Verification (Testing) -> Maintenance.
- **When to Use:** Best for small to mid-sized projects where requirements are very clear, stable, and understood upfront.
- **Advantages:** Simple to understand and easy to manage due to its rigid structure.
- **Disadvantages:** High risk and uncertainty; no working software is produced until very late in the cycle. Once an application is in the testing stage, it is very difficult to go back and change earlier phases.

## B. Incremental Development

This model is based on developing an initial implementation, getting user feedback, and evolving the software through many mini-projects.

- **Key Approach:** The highest priority requirements are tackled first.
- **Benefits:** Software is generated quickly; it is flexible and less expensive to change scope.
- **Problems:** The process is often "invisible" to managers (hard to measure progress with documents); system structure tends to degrade over time unless money is spent on **refactoring**.

## C. Reuse-Oriented Software Engineering

Most modern software is constructed by integrating existing components rather than writing everything from scratch.

- **Stages:** Includes specialized steps like **Software Discovery** (searching for existing components) and **Requirements Refinement** (modifying needs based on what is available).
- **Benefits:** Significantly reduces total development costs and risk.
- **Trade-offs:** May lead to compromises in requirements to fit the available software.

## D. The Spiral Model

The Spiral model combines elements of Iterative and Waterfall models with a **heavy emphasis on risk assessment**.

- **Structure:** It delivers projects in loops; each loop addresses the greatest remaining risk to the project.
- **Pros:** Excellent for complex, high-risk, large-scale projects.
- **Cons:** Very time-consuming and requires highly skilled risk managers.

## E. Rapid Application Development (RAD)

RAD is an iterative model focused on an **extremely short development cycle** (typically 60–90 days). It relies heavily on visual tools and reusable components to generate systems quickly.

# 4 Choosing the Right Model

Selecting a model depends on the project context:

- **Waterfall:** Smaller projects, stable requirements.
- **Incremental:** Projects with loosely-coupled parts.
- **Iterative:** Large-scale projects with multiple modules (like web services).
- **Spiral:** Complex, large-scale projects with significant risks.
- **Agile:** Best for projects with uncertain or rapidly changing requirements.