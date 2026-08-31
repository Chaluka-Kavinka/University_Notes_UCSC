>[!tip]
>Complexity Analysis is the mathematical technique used to characterize the time or space an algorithm requires relative to the size of its input $(n)$
. It allows us to compare different algorithms to see which one performs better as the problem gets larger, independent of the specific computer or programming language used.

---
# 1. Running Time: Actual vs. Theoretical

There are two ways to look at how **"fast"** a program is:
- **Actual Running Time:**
  Measured in seconds or milliseconds on real hardware. This is unreliable for comparison because it changes based on your CPU, RAM, and even how many other programs are open.
- **Theoretical Running Time (Time Complexity):**
  Instead of seconds, we count basic operations (like comparisons, assignments, or math steps). We express this using **Big O notation** to describe how the work increases as the input size $(n)$ grows.

# 2. The Three "Bounds" of Complexity

We use asymptotic notations to describe different scenarios:

- **Big-O Notation $(O)$ – The Ceiling:** Describes the **Worst-Case** or maximum time an algorithm can possibly take.
- **Big-Ω Notation $(Ω)$ – The Floor:** Describes the **Best-Case** or minimum time an algorithm will take.
- **Big-Θ Notation $(Θ)$ – The Tight Bound:** Describes the **Average-Case** or the exact asymptotic growth.

# 3. The Hierarchy of Speed (Best to Worst)

Algorithms are categorized into complexity classes. Think of these as "speed limits":

- $O(1)$ **(Constant):** The speed never changes, regardless of data size (e.g., accessing a single array element).
- $O(\log n)$ **(Logarithmic):** Very fast; the search space is halved each step (e.g., Binary Search).
- $O(n)$ **(Linear):** Work increases exactly with the data size (e.g., Linear Search).
- $O(n^2)$ **(Quadratic):** Work increases exponentially with data; usually involves **nested loops** (e.g., Bubble Sort).
- $O(2^n)$ **(Exponential):** Extremely slow; work doubles with every new item (e.g., Recursive Fibonacci).

# 4. Rules for Calculating Big O

When analyzing code, we use two main simplifications:

1. **Drop Constant Factors:** We don't care about the exact number of steps, just the growth. Thus, $3n+5$ is simply $O(n)$.
2. **Keep the Dominant Term:** For large n, the highest-order term "swamps" everything else. In $n^2+3n+5$, the $n^2$ term is the only one that matters, so it is $O(n^2)$.

---

**Fancy Examples:**

- **The Tea Party (Algorithm Definition):**
  An algorithm is like a **recipe for making tea**. It must be **Finite** (you stop when the tea is made), **Definite** (clear steps like "boil water"), and **Effective** (you actually have a kettle and water).
- **Finding a Friend:**
  If you search for a friend in a room of 10 people by checking each face, it’s fast. If you do the same in a stadium of 100,000 people, it takes much longer. That is **Linear Growth ($O(n)$)**.

---

**Short Note for Memory:**

- $O$ **(Big O):** Think **"Over"** (The upper limit/Worst case).
- $Ω$ **(Omega):** Think **"Only"** (The lower limit/Best case).
- $Θ$ **(Theta):** Think **"Typical"** (The average case).
- **Simple Loop:** Usually $O(n)$.
- **Nested Loop:** Usually $O(n^2)$.
- **Binary Search:** Always $O(\log n)$.

---

**Analogy for Understanding:** Think of complexity like **moving houses**.

- $O(1)$ is picking up your keys (takes the same time whether you have 1 box or 1,000).
- $O(n)$ is carrying the boxes to the truck one by one (more boxes = more time).
- $O(n^2)$ is if you had to compare every item in every box to every other item to see if they match. If you double your items, the work quadruples!
---
# Lecture Notes
![[DSA - Lecture 09.pdf]]