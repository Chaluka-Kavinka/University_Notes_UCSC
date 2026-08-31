>[!tip]
>This topic helps to define the fundamental concepts and structural rules of the **relational model**. It aims to provide students with the ability to:
>
> - Define core terminology such as **relations, attributes, domains, and tuples**.
> - Understand the quantitative properties of a relation, including its **degree** and **cardinality**.
> - Identify and differentiate between various **key types** used to uniquely identify data.
> - Explain and apply **fundamental integrity rules**, such as entity and referential integrity, to ensure data accuracy.

# Relational Terminology and Structure

In relational model, data is organized into **Relations** (informally know as tables). A **Tuple** represents a row in the table, while an **Attribute** represents a column. The **[^1]Domain** is the set of values allowed for one or more attributes.

Two important measures of a relation are its **Degree** (the number of attributes it contains) and its **Cardinality** (the number of tuples/rows it contains).

# The Concept of Key

Keys are attributes used to uniquely identify tuples in a relation. There are several specific types.

- **Super Key:** An attribute or set of attributes that uniquely identifies tuples.
- **Candidate Key:** A **minimal** super key; an entity may and multiple candidate keys.
- **Primary Key:** The specific candidate key selected to uniquely identify tuples; it **cannot contain null values** or repetitive values.
- **Alternate Key:** Candidate keys that were not selected as the primary key.
- **Composite Key:** A primary key that consists of **two or more attributes**.
- **Foreign Key:** An attribute in one relation that matches the candidate key of another relation, used to link tables together.
- **Surrogate Key:** An **artificially created** unique value (often a simple integer) used when no natural primary key exists.

# Integrity Constraints

Constraints are integrity rules that a database is not permitted to violate.

- **Entity Integrity:** States that no attribute of a primary key can be **null**.

- **Referential Integrity:** Ensures that a foreign key value must match a candidate key value in the related table or be null.

- **Domain Constraints:** Define the specific set of values an attribute is permitted to hold.

# Domain Constrains

In SQL, domains are implemented and enforced through **Data Definition Language (DDL)** using two primary mechanisms: the `CHECK` clause and the `CREATE DOMAIN` statement.

## 1. The CHECK Clause

The `CHECK` clause allows you to define a constraint directly on a column to limit the values it can receive.

**Example: Restricting Gender Values**

```
	CREATE TABLE Staff (
	    staffNo CHAR(5) PRIMARY KEY,
	    fName VARCHAR(20) NOT NULL,
	    -- The domain is restricted to 'M' or 'F' using an inline CHECK constraint
	    sex CHAR NOT NULL CHECK (sex IN ('M', 'F'))
	);
```

In this code, the **domain** for the `sex` attribute is strictly defined as only two possible characters, and the DBMS will reject any other input.

## 2. The CREATE DOMAIN Statement

The ISO standard also allows you to create a **reusable domain** as a standalone database object. This is useful if multiple tables need to follow the same set of rules.

**Example: Defining a custom "SexType" Domain**

```
	-- First, define the domain independently
	CREATE DOMAIN SexType AS CHAR
	    DEFAULT 'M'
	    CHECK (VALUE IN ('M', 'F'));
	
	-- Then, use that domain when creating tables
	CREATE TABLE Staff (
	    staffNo CHAR(5) PRIMARY KEY,
	    sex SexType -- Instead of CHAR, we use our custom domain
	);
	
	CREATE TABLE Client (
	    clientNo CHAR(5) PRIMARY KEY,
	    sex SexType -- The same domain logic is reused here
	);
```

By defining `SexType` once, you ensure that every attribute using this domain across the entire database follows the exact same set of legal values.

**Why Domains Matter**
Beyond simple data entry, domains are critical for **relational integrity**. For example, when performing set operations like a `UNION`, it is the user's responsibility to ensure that corresponding columns come from the **same domain**. It would not be sensible to combine a column for "Staff Age" with a column for "Number of Rooms," even if they both use the `INTEGER` data type, because they represent different logical domains.

---

# Short Note - Relational Data Model

- **Structure:** Data is stored in **relations** (tables), where each row is a **tuple** and each column is an **attribute**.

- **Measurement:** A table's size is described by its **degree** (columns) and **cardinality** (rows).

- **Identification:** **Primary Keys** are the unique identifiers for a table, while **Foreign Keys** act as the "hooks" that connect different tables.

- **Key Varieties:** Keys can be **Composite** (made of multiple columns), **Surrogate** (invented by the system), or **Candidate** (potential primary keys).

- **Data Rules:** **Entity Integrity** prevents "empty" primary keys, ensuring every record can be found, while **Referential Integrity** maintains the consistency of links between tables.

The **relational data model** is like a **standardized spreadsheet workbook**: the **Relation** is an individual sheet, the **Attributes** are the column headers, and each **Tuple** is a completed row. **Primary Keys** act like unique ID numbers for every row to ensure no two entries are confused, and **Foreign Keys** are like a "see also" note that points you to a specific row on a different sheet.

---
# Lecture Notes

![[IS1210 - Relational Data Model.pdf]]

[^1]: A **domain** is the original set of **atomic values**—meaning values that are indivisible—used to model data for one or more attributes. It serves as a set of **acceptable values** that a specific column is permitted to contain, ensuring that the information stored remains logical and consistent. For example, the domain for a "Marital Status" attribute might be restricted to the set {Married, Single, Divorced}, while a "Salary" domain might be defined as all floating-point numbers greater than 0 and less than 200,000.