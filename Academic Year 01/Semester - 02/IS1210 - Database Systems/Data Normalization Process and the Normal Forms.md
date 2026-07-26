>[!tip]
>The primary objective of **normalization** is to create an **accurate representation of data**, its relationships, and constraints. It aims to produce a set of relations with desirable properties by **minimizing data redundancy** and eliminating **update anomalies**. 
>
>The process provides a formal technique to identify a suitable set of relations where attributes with close logical relationships are grouped together. Ultimately, it ensures the database is easier to maintain, access, and takes up **minimal storage space**.

---
# Understanding Data Redundancy and Anomalies

A major goal of normalization is to group attributes to avoid **redundancy**, which occurs when the same data is stored in multiple places. Redundancy leads to **update anomalies**, which are classified into three types:

- **Insertion Anomalies:** When data cannot be added because other required data is missing, such as needing a staff member to create a branch record.

- **Deletion Anomalies:** When the deletion of one piece of data causes the unintentional loss of other unrelated data.

- **Modification Anomalies:** When data is only partially updated because it exists in multiple locations, leading to **inconsistencies**.

# Functional Dependencies and Keys

Normalization is built upon the analysis of **Functional Dependencies (FD)**, where one attribute (the determinant) uniquely identifies another. Key types include **Super Keys**, **Candidate Keys** (minimal super keys), and the **Primary Key** chosen for unique identification. To reach higher normal forms, designers must identify:

- **Full Functional Dependency:** Where an attribute depends on the entire primary key, not a subset.

- **Partial Dependency:** Where an attribute depends on only a portion of a composite primary key.

- **Transitive Dependency:** An indirect relationship where an attribute depends on another non-key attribute.

# The Normalization Process

The process involves a series of tests called **Normal Forms**:

- **Unnormalized Form (UNF):** A table that contains **repeating groups**.

- **First Normal Form (1NF):** A relation where every intersection of a row and column contains exactly **one atomic value**.

- **Second Normal Form (2NF):** A relation in 1NF where every non-primary-key attribute is **fully functionally dependent** on the primary key, effectively removing partial dependencies.

- **Third Normal Form (3NF):** A relation in 2NF that has **no transitive dependencies**.

- **Boyce-Codd Normal Form (BCNF):** A stronger version of 3NF where **every determinant must be a candidate key**.

---
# Short Note - Database Normalization

• **Technique Types:** Normalization can be used as a **bottom-up technique** to create relations from attributes or a **validation technique** to check structures derived from top-down ER modeling.

• **Decomposition Rules:** When splitting a large relation into smaller ones, the decomposition must be **lossless** (allowing the original table to be recreated) and **preserve dependencies**.

• **Key Identification:** Functional dependencies are the primary tool used to identify the most suitable **Primary Key** for a relation.

• **Surrogate Keys:** When no natural primary key exists, designers may create a **surrogate key**, which is a system-generated artificial identifier with no business meaning.

• **Trade-offs:** While normalization reduces redundancy and improves data integrity, it can **increase the number of joins** required for queries, which may reduce performance efficiency and increase system complexity.

The **Normalization Process** is like **refining raw materials**: you start with a "dirty" unnormalized table (UNF) and filter out repeating patterns (1NF), then remove "half-dependencies" on composite keys (2NF), and finally clear out indirect "sideways" dependencies (3NF) until you have a **pure, consistent data structure**. While this makes the data much safer from errors (**anomalies**), it makes the "assembly" of full reports slightly more complex because the data is now stored in many specialized, smaller tables instead of one giant one.

---
# Lecture Notes
![[IS1210 - Normalization - Part 1.pdf]]
![[IS1210 - Normalization - Part 2.pdf]]
![[IS1210 - Normalization - Part 3.pdf]]