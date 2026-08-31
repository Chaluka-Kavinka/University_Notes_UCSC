>[!tip]
>The primary goal of this topic is to explain the **three-level database architecture** (ANSI-SPARC) and the various components that allow a Database Management System (DBMS) to function as a bridge between users and physical data. Specifically, it aims to:
>- Differentiate between the **external, conceptual, and internal levels**.
>- Define the purpose of **mappings** and the concept of **logical and physical data independence**.
>- Distinguish between **Data Definition Language (DDL)** and **Data Manipulation Language (DML)**.
>- Identify the typical functions and software components of a DBMS.

---

# The Three-Level ANSI-SPARC Architecture

This Architecture is to protect the user’s view of data from changes in how data is physically stored, the database environment is organized into three levels:

- **External Level:**
	The part of the database relevant to an individual user; it consists of multiple "views" that can hide unauthorized data or derive new attributes.

- **Conceptual Level:**
	The logical structure of the _entire_ database as seen by the organization. it describes all entities, relationships, constraints, and security information.

- **Internal Level:**
	The physical representation of the database on the computer, focusing on storage space, data structures, and file organizations to achieve optimal performance.

# Data Independence and Schemas

The description of the database is called the **schema**. Because these levels are separated, changes to one level do not necessarily require changes to others. **Logical Data Independence** means the external schema is immune to changes in the conceptual schema (like adding a new entity). **Physical Data Independence** means the conceptual schema remains unaffected by changes in the internal schema (like changing storage devices).

# Database Languages

- **DDL (Data Definition Language):**
	Used by the DBA to define and name entities, attributes, and relationships, along with integrity and security constraints.

- **DML (Data Manipulation Language):**
	Provides operations for selecting, inserting, updating, and deleting data. It can be **procedural** (telling the system _how_ to get data) or **non-procedural** (stating _what_ data is needed).

# DBMS Functions and Components

A DBMS must provide services like **concurrency control** (ensuring simultaneous users don't conflict), **recovery services** (restoring data after failure), and **authorization services** (checking user permissions). Key software components include the **System Catalog** (a repository of metadata), the **Query Optimizer**, and the **Scheduler**.

---
# Short Note: Topic Two - Database Environment

- **Core Architecture:**
	The **ANSI-SPARC three-level architecture** decouples the user's view (**External**) from the organization's logic (**Conceptual**) and the physical storage (**Internal**).

- **Mappings:**
	The DBMS is responsible for "mapping" or translating requests between these levels.

- **Data Independence:**
	This is the most critical benefit of the three-level approach, allowing the physical or logical structure of data to evolve without breaking user applications.

- **The System Catalog:**
	Known as the "data dictionary," it stores **metadata** (data about data), such as user names, data types, and constraints, ensuring the system can maintain integrity and security.

- **DBMS Operations:**
	The system uses **DDL** to build the house (structure) and **DML** to move the furniture (data) in and out.

The **three-level architecture** is like using a **smartphone**: The **External level** is the app's interface that you interact with; the **Conceptual level** is the programming logic that decides what the app can do; and the **Internal level** is the actual electrical signals and storage chips inside the phone. Because of **data independence**, the manufacturer can change the internal chips (Internal level) without you ever needing to learn a new way to use the app (External level).

---
# Lecture Notes

![[IS1210 - Database Environment.pdf]]