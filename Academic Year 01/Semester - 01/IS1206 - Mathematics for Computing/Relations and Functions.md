# 1. Ordered Pairs and Cartesian Products

- **Ordered Pairs:** Denoted by $(a,b)$, where the order of elements is essential; $(a,b)=(c,d)$ only if $a=c$ and $b=d$.
- **Cartesian Product $(A \times B)$:** The set of all possible ordered pairs where the first element is from set A and the second is from set B.
    - The cardinality (size) of $A \times B$ is the product of the sizes of both sets: $∣A \times B∣ = ∣A∣ \times ∣B∣$.
    - If either set is empty, the Cartesian product is also empty $(A \times \emptyset = \emptyset)$.

# 2. Understanding Relations

- **Definition:** A relation $R$ from set $A$ to set $B$ is simply a **subset of the Cartesian product** $A \times B$. It shows how elements from one set are connected to elements of another.
- **Binary Relations:** These specifically represent relationships between elements of two sets using ordered pairs.

# 3. Functions (Mappings/Transformations)

- **Definition:** A function is a special type of relation where **every element** in the input $set (A)$ is mapped to **exactly one** element in the output $set (B)$.
- **Key Distinction:** While every function is a relation, not every relation is a function. For a relation to be a function, no single input can have multiple different outputs.

# 4. Terms Related to Functions

- **Domain:** The set of all possible inputs for which outputs are obtained (Set A).
- **Co-domain:** The set of all potential outputs (Set B).
- **Range:** The set of all actual outputs that have a corresponding input (pre-image). The range is always a subset of the co-domain.

# 5. Representations of Relations and Functions

The sources identify five ways to represent these connections:

1. **Roster Form:** Listing the elements as ordered pairs, e.g., $R=\{(−1,1),(0,0),(1,1)\}$.
2. **Set-Builder Form:** Using an algebraic rule, e.g., $$R=\{ (a,b) \mid a \in A, b \in B \text{ and } b=a^2 \}$$
3. **Arrow Diagrams:** Drawing lines to connect elements in one box to elements in another.
4. **Tabular Form:** Organizing inputs and outputs in a table.
5. **Lattice/Graphical Form:** Plotting the ordered pairs as points on a Cartesian plane.

# 6. Composite Functions

- **Definition:** Function composition occurs when the **output of one function becomes the input of another**.
- **Notation:** Denoted as $(f∘g)(x)$, which is read as "f composed with g" and calculated as $f(g(x))$.
- **Properties:**
    - **Associative:** $$(f∘g)∘h=f∘(g∘h)$$
    - **Identity:** $$f∘I=I∘f=f, where I(x)=x$$
    - **Inverse:** If f has an inverse $(f−1)$, then $f∘f−1=I$.