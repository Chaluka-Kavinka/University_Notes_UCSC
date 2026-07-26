we explore the branch of mathematics concerned with counting, arranging, and selecting objects. This field forms the foundation of discrete mathematics and is essential for computer science, particularly in algorithm analysis, data encryption, and optimization.

---

# 1. Basic Counting Principles

There are four fundamental rules used to solve a variety of combinatorial problems:

- **The Product Rule:** If a sequence of tasks can be performed in $n$ ways followed by $m$ ways, then there are $n \times m$ ways to perform both tasks in sequence. This is used for independent, sequential tasks, such as determining the number of possible computer configurations or bit strings.
- **The Sum Rule:** If a task can be done in n ways and another in m ways, and they **cannot be performed simultaneously**, there are $n+m$ ways to do either task.
- **The Subtraction Rule (Inclusion-Exclusion):** When tasks or sets have common elements, the number of ways to select an element from their union is the sum of the individual ways **minus the overlap** $(∣A_1 \cup ​A_2∣ = ∣A_1​∣+∣A_2​∣ − ∣A_1​ \cap A_2​∣)$
- **The Division Rule:** This is applied when multiple distinct arrangements actually represent the same outcome, such as seating people around a **circular table** where only relative positions matter.

# 2. The Pigeonhole Principle

This principle is used to guarantee a certain outcome when items exceed containers.

- **Basic Principle:** If $k + 1$ or more objects are placed into $k$ boxes, at least one box must contain two or more objects. For example, in a group of 13 people, at least two must share a birth month.
- **Generalized Pigeonhole Principle:** If $N$ objects are placed into k boxes, at least one box contains at least $\lceil N/k \rceil$ objects. This is useful for proving, for instance, that in a group of 85 people, at least four share the same last-name initial.

# 3. Permutations and Combinations

The choice between these two depends entirely on whether **order matters**.

- **Permutations $(P(n,r))$:** An **ordered arrangement** of r distinct elements from a set of n elements.
    - _Formula:_ $$P(n,r) = \frac {n!} {(n−r)!}​$$
    - _Examples:_ Awarding gold, silver, and bronze medals or arranging students in a line for a photo.
- **Combinations $(C(n,r))$:** An **unordered selection** (subset) of r elements from a set of n elements.
    - _Formula:_ $$C(n,r) = \frac {n!} {r!(n−r)!}​$$
    - _Examples:_ Selecting a committee of five from ten members or dealing a poker hand.
    - _Key Property:_ $C(n,r) = C(n,n−r)$, meaning choosing which elements to include is the same as choosing which to exclude.

# 4. Advanced Counting Scenarios

- **Permutations with Repetition:** If elements can be reused (like characters in a password), the number of $r$-permutations of n elements is $nr$.
- **Indistinguishable Objects:** When reordering items where some are identical (like the letters in "SUCCESS"), the total permutations are divided by the factorials of the counts of repeated items.
- **Combinations with Repetition:** Used for selecting items from k types where you can pick multiple of the same type (e.g., choosing 6 cookies from 4 different kinds). The formula is $C(n+k−1,n)$.

# 5. Distributing Objects into Boxes

The method for distributing objects depends on whether the **objects** and **boxes** are distinguishable (labeled) or indistinguishable.

- **Distinguishable Objects & Boxes:** Distributing 5 cards to 4 different players is solved using the product rule of combinations.
- **Indistinguishable Objects & Distinguishable Boxes:** Placing 10 identical balls into 8 labeled bins is equivalent to combinations with repetition.
- **Indistinguishable Objects & Boxes:** There is no simple closed formula for this; it often requires listing the partitions of the integer n.