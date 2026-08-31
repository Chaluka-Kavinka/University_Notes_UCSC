>[!tip]
>The primary objective of **Logical Database Design** is to transform a high-level conceptual model (ER or EER diagram) into a **relational schema**. This involves refining the model to remove features incompatible with the relational model and applying a well-defined set of rules to derive a structured set of tables.

---
# Mapping Entities

The first step in logical design is transforming entity types into relations (tables).

- **Strong Entities:** Each regular entity becomes a relation. All **simple attributes** are included, while **composite attributes** are broken down into their constituent simple parts.

- **Multi-valued Attributes:** These are removed from the original entity and placed into a **new relation** along with the primary key of the parent entity to act as a foreign key.

- **Weak Entities:** These are mapped into relations where the primary key is partially or fully derived from the **identifying owner entity**.

# Mapping Relationships

The method for mapping relationships depends on their degree (binary, unary, or complex) and cardinality:

- **One-to-Many (1:N):** The primary key of the "one" side (parent) is copied into the "many" side (child) as a **foreign key**.

- **One-to-One (1:1):** The strategy depends on participation. Entities with **total participation** on both sides can be combined into one relation. If participation is partial on one side, the entity with partial participation usually acts as the parent.

- **Many-to-Many (M:N):** These require creating a **new associative relation** (junction table) containing the primary keys of both participating entities as foreign keys.

- **Unary (Recursive):** For 1:N unary relationships, the primary key is added as a foreign key within the **same relation**. For M:N unary relationships, a new relation is created using the primary key twice.

- **Complex Relationships:** A new relation is created to represent the relationship, containing foreign keys from all participating entities.

# Advanced Modeling (Sub-types and Categories)

- **Super-type/Sub-type:** Since the relational model does not directly support inheritance, designers use strategies based on **disjointness and completeness constraints**. This may result in a single relation for the entire hierarchy or separate relations for each subclass.

- **Categories (Union Types):** When a subclass represents a union of super-classes with different keys, a **surrogate key** is often defined to uniquely identify records in the category relation.

---
# Short Note - Logical Database Design

- **Blueprint Translation:** Mapping is the systematic process of turning an ER diagram into **relational tables** using seven core steps.

- **Attribute Flattening:** Relations must contain only **atomic values**; therefore, composite attributes are split, and multi-valued attributes are moved to separate tables.

- **Key Propagation:** The "Golden Rule" for 1:N relationships is that the **Parent's Primary Key** always follows the data to the **Child table** as a Foreign Key.

- **Relationship Resolution:** M:N and complex relationships cannot exist in a single table; they must be "resolved" into their own **associative relations**.

- **Managing Hierarchies:** Super-class/Subclass mapping requires choosing between **combining data** (minimizing joins) or **splitting data** (minimizing nulls) based on business constraints.

- **Surrogate Keys:** These are artificial identifiers used specifically when mapping **Categories** or complex associative entities to ensure every record remains unique.

The **Logical Database Design process** is like **drafting a manufacturing manual from a concept sketch**: The **ER Diagram** is the sketch of what the product should look like, but the **Relational Schema** is the set of specific instructions (tables and keys) that tell the factory (the DBMS) exactly how to build and connect every individual component (data) to ensure the final product functions correctly.

---
# Lecture Notes

![[IS1210 - Logical Database Design.pdf]]