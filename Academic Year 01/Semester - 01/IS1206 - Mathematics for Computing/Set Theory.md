>Next Topic : [[Mathematical Logic]]

This subject is foundational for computing, particularly in areas like database theory, formal languages, and data structures.

---

# 1. Fundamental Concepts

- **Definition:** A set is a collection of **clearly defined objects**, things, or states.
- **Elements:** The objects contained within a set are called its elements.
- **Basic Properties:**
    - The **order** of elements does not matter.
    - Elements are **not repeated** within a set.
    - **Cardinality ( $∣A∣$ ):** This refers to the total number of elements in a set.

# 2. Representing Sets

There are two primary ways to describe a set in your sources:

- **Roster Form:** Listing all elements inside braces, separated by commas (e.g., $A = \set{a,b,c,d,e}$).
- **Set-Builder Form:** Using a statement or algebraic expression to define the elements e.g., $$\{x \in \mathbb{Z} \mid 0 < x < 20, x \text{ is odd}\}$$
# 3. Types of Sets

Understanding the different categories of sets is essential for logical classification:

- **Empty Set ($\emptyset$ or $\set{}$):** A set containing no elements.
- **Singleton Set:** A set containing exactly one element.
- **Finite vs. Infinite Sets:** Finite sets have a countable number of elements, while infinite sets (like the set of all real numbers) do not.
- **Equal vs. Equivalent:** **Equal sets** have exactly the same elements. **Equivalent sets** only need to have the same number of elements (same cardinality).
- **Subsets ( $\subseteq$ ) and Proper Subsets ( $\subset$ ):** If every element of A is in B, then A is a subset of B. If B also contains at least one element not in A, then A is a **proper subset**.
- **Universal Set ( $\bigcup$ ):** The set containing all objects under consideration for a particular problem.

# 4. Set Operations

These operations allow us to combine or compare data groups:

- **Union ( $A \cup B$ ):** Contains all elements from both set A and set B.
- **Intersection ( $A \cap B$ ):** Contains only the elements that are **common** to both sets.
- **Complement ( $A'$ or $A^\complement$ ):** Includes all elements in the Universal set ( $\bigcup$ ) that are **not** in set A.
- **Set Difference ( $A−B$ ):** Contains elements that are in A but **not** in B.
- **Symmetric Difference ( $A \Delta B$ or $A \oplus B$):** Contains elements that are in A or B, but **not in both**.
- **Cartesian Product ( $A \times B$ ):** The set of all ordered pairs $(a,b)$ where $a \in A$ and $b \in B$.

# 5. Venn Diagrams

Venn diagrams provide a **diagrammatic representation** of sets. They are used to visualize relationships, such as identifying developers involved in specific overlapping projects or calculating how many individuals are involved in "exactly two" or "at least one" category.

# 6. Application in Computing

Set theory principles are directly applied in programming:

- **Python Sets:** Used for storing unique elements and performing fast membership testing.
- **Database Theory:** Understanding how different tables (sets of data) relate through joins (intersections) and unions.