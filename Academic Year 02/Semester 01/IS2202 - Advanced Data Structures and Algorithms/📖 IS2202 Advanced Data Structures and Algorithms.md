- Course Code : IS 2202
- Course Name : Advanced Data Structures and Algorithms
- Lecture : Dr. Kasun Karunanayaka | Dr. Yohani Ranasinghe

#Lesson-Plan 


> [!Tip] Objective of this Lesson
> The primary objectives of this lesson are to enable you to:
>  - Understand and evaluate the fundamental **complexity trade-offs** (Time Complexity vs. Space Complexity) inherent in algorithm design.
> - Formulate mathematical, hardware-independent representations of code execution times using a standardized **sequential computational model**.
> - Examine how resource consumption scales as input sizes (n) grow arbitrarily large, moving from exact instruction counts to **asymptotic notations**.
> - Formally define, calculate, and apply the rules of **Big-O, Big-Omega, and Big-Theta notations** to classify algorithms into standard complexity classes.

---
# Summary of Entire Lesson

The lesson begins by explaining that designing algorithms is about managing trade-offs, particularly balancing **Time Complexity** (how long it takes to run) and **Space Complexity** (how much memory/storage it consumes). These trade-offs are illustrated using grocery shopping analogies: driving a large car to buy everything at once is time-efficient but space-costly, whereas walking back and forth with a small tote bag is space-efficient but highly time-consuming.

To compare algorithms objectively without hardware bias, the lesson introduces the **Sequential Computational Model**. This computer-independent model assumes sequentially executed instructions, infinite memory, and a cost of one unit of time for every simple instruction (assignments, comparisons, increments). By applying this model, exact instruction-counting equations can be derived for code. For example:

- Managing a loop block like `for (int j = 0; j < n; j++)` costs 2n+2 instructions.
- **Sequential (Linear) Search** yields an exact worst-case cost of 3n+3 instructions, but operates at an average/typical case cost of 3/4n comparisons when assuming a 50/50 target distribution.

As the input size (n) scales towards infinity, exact constants become less significant because the highest-order term dominates ("swamps") the growth rate of the polynomial. The lesson utilizes **Asymptotic Behavior** (where a function continually approaches but never meets a defined limit or curve) and **Unbounded Behavior** (where a function increases without limits as inputs grow) to visualize scaling trends. Examples include asymptotic curves like 1/x, bounded oscillations like sin(x), and unbounded growth profiles like ex and x3.

Finally, **Big O Notation** is defined as the formal language to describe this asymptotic rate of growth. The lesson introduces **three major notations** to bound algorithm complexity:

1. **Big-Oh (O)**: The asymptotic upper bound.
2. **Big-Omega (Ω)**: The asymptotic lower bound.
3. **Big-Theta (Θ)**: The asymptotic tight bound.

It details calculation rules (such as ignoring log bases and coefficients) and diagrams standard curves to classify algorithms into runtime categories like constant O(1), logarithmic O(logn), linear O(n), and quadratic O(n2).

---
# Topics Covered in this Lesson

The lecture material is systematically organized into the following topics:

1. [[Time vs. Space Complexity Trade-offs]]
    - Definitions of Time and Space complexity.
    - Real-world grocery shopping analogies (Time-efficient vs. Space-efficient).

2. [[The Sequential Computational Model]]
    - Core assumptions of computer-independent models.
    - Unit costs for basic programmatic operations.

3. [[Code Instruction Counting]]
    - Calculating cost equations for sequential assignments.
    - Evaluating loops and nested loops step-by-step (e.g., deriving $3n^2+4n+3$ costs).

4. [[Complexity Analysis of Linear Search]]
    - Deriving the worst-case total cost of $3n+3$.
    - Identifying Best Case vs. Worst Case scenarios.
    - Deriving the typical average-case cost of $3/4n$ comparisons.

5. [[Polynomial Rate of Growth]]
    - Identifying highest-order dominating terms.
    - Comparing linear vs. quadratic function growth $(100n \text{ vs } n^2+n)$.

6. [[Asymptotic and Unbounded Behavior]]
    - Mathematical definitions of asymptotes and limits.
    - Analyzing behavioral bounds of functions $(1/x, \sin(x), e^x, \text{ and } x^3)$.

7. [[Asymptotic Notations]] ( O , Ω , Θ )
    - Formal definition of **Big-Oh** $(T(n) ≤ c⋅f(n) \text{ when } n≥n_0​)$.
    - Differentiating Upper Bounds (O), Lower Bounds (Ω), and Tight Bounds (Θ).

8. [[Big-Oh Mathematical Rules]]
    - Logarithm simplification rules (ignoring bases and internal powers).
    - Exponent rules (exponents and bases cannot be ignored).

9. [[Standard Complexity Classes and Curves]]
    - Visualizing different **Big O** growth curves.
    - Code examples demonstrating $O(1)$ constant time, $O(n)$ linear time, $O(\log{n})$ logarithmic time, and $O(n^2)$ space/time quadratic complexities.