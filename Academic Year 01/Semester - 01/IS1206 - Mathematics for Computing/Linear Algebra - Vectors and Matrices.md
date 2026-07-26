This module, which spans approximately 8 hours of lecture time, focuses on the mathematical tools used for data representation, computer graphics transformations, and solving complex systems of equations.

---

# 1. Linear Equations and Systems

A **linear equation** is an equation of the first order, meaning the highest exponent of any unknown variable is one. When plotted on a graph, these equations form a straight line.

- **Linear System:** A set of two or more linear equations involving the same variables.
- **Solutions:**
    - **Consistent:** A system that has either exactly one solution or infinitely many solutions.
    - **Inconsistent:** A system that has no solution at all.

# 2. Fundamentals of Matrices

A **matrix** is a rectangular array of numbers, symbols, or expressions arranged in rows and columns, typically denoted by capital letters (e.g., A,B).

- **Dimensions:** An m×n matrix has m rows and n columns.
- **Special Types of Matrices:**
    - **Square Matrix:** Equal number of rows and columns.
    - **Diagonal Matrix:** A square matrix where all elements outside the main diagonal are zero.
    - **Identity Matrix (**I**):** A diagonal matrix where all diagonal elements are 1.
    - **Triangular Matrices:** **Upper triangular** (elements below the diagonal are zero) or **Lower triangular** (elements above the diagonal are zero).
    - **Zero Matrix:** All elements are zero.

# 3. Matrix Algebra

- **Equality:** Two matrices are equal if they have the same dimensions and all corresponding elements are identical.
- **Addition and Subtraction:** Can only be performed on matrices of the same dimensions by adding or subtracting corresponding elements.
- **Scalar Multiplication:** Every element in the matrix is multiplied by a single number (scalar).
- **Matrix Multiplication:** Involves combining rows of the first matrix with columns of the second; each resulting element is a dot product of the corresponding row and column.

# 4. Vectors

A **vector** is a quantity that has both **magnitude (size)** and **direction**.

- **Notation:** Represented by boldface letters (e.g., **v**) or letters with arrows ($v$).
- **Components:** In 2D, a vector is written as $[v_x​,v_y​]$; in 3D, it is written as $[v_x​,v_y​,v_z​]$.
- **Operations:** Includes vector addition (using the parallelogram rule), scalar multiplication, and the **dot (inner) product**.

# 5. Advanced Matrix Operations

- **Transpose ($A^T$)$:** A new matrix created by rotating the rows of the original matrix into columns.
- **Inverse Matrix:** For a $2 \times 2$ matrix, the inverse is found by swapping a and d, negating $b$ and $c$, and dividing the entire matrix by the **determinant** $(ad−bc)$.
- **Augmented Matrix:** A compact way to represent a system of linear equations for systematic solving.

# 6. Solving Systems: Gaussian Elimination

This systematic process involves transforming an augmented matrix into a simpler form to find solutions:

1. **Elementary Row Operations:**
    - Multiplying a row by a non-zero constant.
    - Adding or subtracting a multiple of one row to another.
    - Interchanging two rows.
2. **Gaussian Elimination:** Uses these operations and **back substitution** to find variables.
3. **Reduced Row Echelon Form (RREF):** A further simplified state that allows you to read the values of variables directly from the matrix.