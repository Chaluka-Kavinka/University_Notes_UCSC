>[!tip]
>This topic helps to understand the **database design process**, specifically how to analyze requirements and transform them into a **conceptual schema** using **Entity-Relationship (ER)** and **Enhanced Entity-Relationship (EER)** modeling.
>
>It further aims to the rules for **mapping** these high-level diagrams into **relational schemas** (tables) that are compatible with a Database Management System

# The Database Design Process

The process of creating a database is divided into four phases: **Requirements Collection and Analysis**, **Conceptual Design**, **Logical Design**, and **Physical Design**. During the conceptual phase, designers create a "mini-world" representation that documents business rules and data requirements independently of technology.

# The Entity-Relationship (ER) Model

The ER model is built upon three main concepts:

- **Entities:**
	These are "things" in the real world, such as an Employee or Department. **Strong entities** exist independently, while **weak entities** depend on an "identifying owner" entity for their existence.

- **Attributes:**
	These properties describe entities. They can be **simple** (indivisible), **composite** (broken into parts like a name), **multi-valued** (multiple values like skills), or **derived** (calculated from other data like age).

- **Relationships:**
	These are meaningful associations between entities. They are defined by their **degree** (unary, binary, ternary, or Quaternary) and **Cardinality ratios** (1:1, 1:N, or M:N). **Participation constraints** determine if every entity instance _must_ participate in a relationship (Total) or if it is optional (Partial).
## Symbols used in ER Model
![[ER diagram symbols.png]]
# Enhanced Entity-Relationship (EER) Modeling

EER modeling introduces advanced concepts for complex applications:

- **Super-classes and Sub-classes:**
	Sub-classes represent subgroups of a super-class in an "IS-A" relationship (e.g., a Technician _is an_ Employee).

- **Inheritance:**
	Sub-classes inherit all attributes and relationship participators from their super-class.

- **Specialization and Generalization:**
	Specialization is the top-down process of defining sub-classes, while generalization is the bottom-up process of identifying common features to create a super-class.

- **Constraints:**
	These include **Disjointness** (whether an instance can belong to multiple sub-classes) and **Completeness** (whether every super-class instance must belong to a subclass).

![[Academic Year 01/Semester - 02/IS1210 - Database Systems/Images/img_01.svg]]
# Logical Database Design (Mapping)

The final stage of modeling is mapping the ER/EER diagrams into relations. This involves transforming entities into tables and resolving relationships:

- **1:N relationships** are handled by placing a **foreign key** in the "many" side table.

- **M:N relationships** and **complex relationships** require creating a new **associative relation** (junction table).

- **Multi-valued attributes** are moved into their own separate relations to maintain **[^1]Atomicity**.

---
# Short Note - Data Modeling

- **Design Blueprint:** The **Conceptual Design** is a high-level description of the database structure, often represented by an **E-R diagram**, which ensures all user requirements are met without conflicts.

- **Entity Dynamics:** Databases distinguish between **Strong entities** (which have their own identifier) and **Weak entities** (which require a foreign key from an owner to form a primary key).

- **The Power of EER:** **Inheritance** allows subclasses to automatically possess the attributes of their superclass, simplifying the modeling of complex organizational hierarchies.

- **Mapping Integrity:** Converting a design into tables requires strict rules, such as identifying **parent and child entities** to properly place foreign keys.

- **Associative Entities:** When a relationship has its own attributes or is **Many-to-Many (M:N)**, it is transformed into its own table to link the participating entities.

The **ER Modeling process** is like **building a family tree for data**: **Entities** are the family members (Nouns), **Attributes** are their traits (Adjectives), and **Relationships** are how they are connected (Verbs). **EER modeling** adds the concept of **Inheritance**, where "children" (sub-classes) automatically receive the "genes" (attributes) of their "parents" (super-classes).

---
# Lecture Notes

![[IS1210 - Data Modeling using the Entity-Relationship Model.pdf]]

[^1]: Atomicity refers to the number of atoms in a molecule or, in computing, the "all-or-nothing" property of database transactions, ensuring operations complete fully or not at all, preventing partial updates like a bank transfer. Essentially, it means indivisibility, whether in chemical structures or complex data operations, ensuring a stable, consistent state.