Now that we have established the rules of the **Sequential Computational Model**, we can apply them to directly count instructions in program blocks. By summing the exact execution costs of assignments, comparisons, and loop steps, we can construct precise algebraic equations representing the total runtimes of algorithms.

Let us break down the mathematical derivations for the three primary code configurations analyzed in the lectures: sequential code, single loops, and nested loops.

---

# 1. Sequential Statements (Constant Cost)

For statements that execute one after the other without branching or repetition, we simply sum their individual unit costs.

Code Block:

```c
sum = 0;                // Cost: 1
sum = sum + next;       // Cost: 1
```

Step-by-Step Mathematical Count:

- **Line 1** `(sum = 0;)`: A single assignment operation. 

$$\text{Cost} = 1$$

- **Line 2** `(sum = sum + next;)`: An addition and assignment operation. Under our model, this simple expression has a unit cost of 1. 

$$\text{Cost} = 1$$

$$\text{Total Cost} = 1 + 1 = \mathbf{2} \text{ instructions}$$

# 2. A Single Loop (Linear Cost)

When analyzing loops, we must count both the **loop overhead** (initialization, boundary comparison, and increment) and the **loop body** (multiplied by the number of iterations).

Code Block:

```c
for (int i = 1; i <= n; i++)    // Overhead: 2n + 2
    sum = sum++;                // Body: n
```

## Step-by-Step Mathematical Count:

1. **Loop Initialization** `(i = 1)`: Executes exactly once. 

$$\text{Cost} = 1$$

1. **Boundary Comparison** `(i <= n)`: Evaluates to `true` n times and `false` 1 final time to terminate the loop.

$$\text{Cost} = n+1$$

1. **Variable Increment** `(i++)`: Executes at the end of each successful iteration, totaling n times.

$$\text{Cost} = n$$

1. **Loop Body** `(sum = sum++;)`: Located inside the repeated part of the loop, so its cost is multiplied by the number of iterations $(n)$.

$$\text{Cost} = n⋅(1) = n $$

## Algebraic Summation:

$$\text{Total Cost} = (1+(n+1)+n)+n$$


# 3. Nested Loops (Quadratic Cost)

With nested loops, the inner loop's entire overhead is treated as the "body" of the outer loop, meaning its cost is multiplied by the outer loop's iteration count.

Code Block:

```c
k = 0;                                 // Cost: 1
for (int i = 0; i < n; i++)            // Overhead: 2n + 2
    for (int j = 0; j < n; j++)        // Inner Loop: n * (2n + 2)
        k++;                           // Inner Body: n²
```

Step-by-Step Mathematical Count:

- **Line 1** `(k = 0)`: A single assignment outside the loops.

$$ \text{Cost} = 1$$

- **Line 2** `(Outer Loop i < n)`: A standard loop running $n$ times (from 0 to $n−1$). Its loop overhead matches our established formula:

$$ \text{Cost} = 2n+2 $$

- **Line 3** `(Inner Loop j < n)`: A loop running n times. The standalone overhead of this loop is 2n+2. Since it is nested inside the outer loop, it is instantiated and run n times.

$$ \text{Cost} = n⋅(2n+2) = 2n^2+2n $$

- **Line 4** `(Inner Body k++)`: This single increment operation has a base cost of 1. Because it is inside both loops, it executes $n⋅n$ times.

$$ \text{Cost} = n^2⋅(1)= n^2 $$


Algebraic Summation:

$$ \text{Total Cost} = 1 + (2n+2) + (2n^2+2n) + n^2$$
$$\text{Total Cost} = 3n^2 + 4n + 3 \text{ instructions}$$

---

# 🧠 Self-Reflection Check

_Notice how quickly the total instruction count grows as complexity degrees increase! When_ $n=10$:

- _The linear loop takes_ $3(10)+2=32$ _instructions._
- _The quadratic loop takes_ $3(10)^2+4(10)+3=343$ _instructions._

_As_ $n$ _becomes very large, the_ $3n^2$ _term completely dominates the computation time, swamping the_ $4n$ _and_ 3 _terms._