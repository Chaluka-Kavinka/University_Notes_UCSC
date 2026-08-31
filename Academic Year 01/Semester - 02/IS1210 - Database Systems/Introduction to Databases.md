>[!tip]
>This topic helps to establish a foundational understanding of the **database approach** as a solution to the limitations of traditional file-based data management.
>
>The main goal of designing a database for an enterprise is to create an **accurate representation of the data**, the **relationships** between that data, and the **constraints** relevant to the organization

# Introduction and the Evolution of Data Management

Traditional **file-based systems** consisted of application programs that performed services for end-users, where each program managed its own data. This approach led to significant limitations, including **data redundancy** (duplication of data), **data dependence** (file structures being defined within the program code), and **isolation of data**, which made it difficult for different programs to share information. The **database approach** arose as a paradigm shift to solve these issues by storing data descriptions separately and independently from application programs.

# Defining the Database and DBMS

A **database** is a shared collection of logically related data designed to meet the information needs of an organization. A **Database Management System (DBMS)** is the software that allows users to define, create, maintain, and provide controlled access to this data. The **DBMS environment** is composed of hardware, software (DBMS, OS, and applications), data, procedures, and people.

# Roles and Responsibilities

There are several key roles within the database environment:

- **Data Administration:** A high-level function responsible for overall data resource management and corporate standards.

- **Database Administration (DBA):** A technical role focused on physical database design, security, performance, and backup/recovery.

- **Database Designers and Application Developers:** Those who design the structure and build the programs that interact with the data.

- **End-Users:** The "clients" who require information from the database to perform their duties.

# Data Structures and Languages

Data is organized in a **hierarchy** starting from bits and bytes to fields, records, files, and finally the database. The **system catalog** (or data dictionary) stores **metadata**, which is data that describes the properties of other data, such as its type, length, and constraints. Interaction with the database occurs through two main languages:

- **Data Definition Language (DDL):** Used to specify data types, structures, and constraints.

- **Data Manipulation Language (DML):** Used for selecting, inserting, updating, and deleting data

# Evolution of the Database Approach

Databases offer **improved consistency, minimal redundancy, and better data sharing**. However, they also involve **increased complexity, higher costs** for software and hardware, and a **higher impact of failure**. Databases can range from **personal databases** for a single user to **enterprise databases** (such as data warehouses) that support entire organizations.

---

# Short Note - Introduction to Databases

- **Core Concept:**
	A database is a **shared corporate resource** that separates data descriptions from application programs, achieving **program-data independence**.

- **Key Software:**
	The **DBMS** provides controlled access via security, integrity, concurrency, and recovery systems.

- **The Data Hierarchy:**
	Data moves from the smallest unit (**bit**) to the largest (**database**), with **metadata** stored in the system catalog to define what the data means.

- **Primary Advantages:**
	- **Reduced Redundancy:** Facts are ideally recorded only once.
	- **Data Consistency:** Controlling redundancy prevents disagreements between values.
	- **Increased Productivity:** DBMS provides standard functions, reducing the time needed to develop new applications.

- **Primary Disadvantages:**
	High **complexity** and **cost**, as well as the need for additional hardware and specialized personnel.

- **Database Types:**
	Personal (<1 user), Work-group (<25 users), Departmental (functional units), and Enterprise (organization-wide).

A **file-based system** is like a group of students each keeping their own personal notebook for a project; if one student updates a fact, the others' notes become outdated and inconsistent. A **database system**, however, is like a single shared digital document where everyone views and updates the same information in real-time, ensuring everyone has the most accurate data.

---
# Lecture Notes

![[IS1210 - Introduction to Databases.pdf]]