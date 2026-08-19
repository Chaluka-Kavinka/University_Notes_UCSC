To analyze and compare algorithms objectively, computer scientists cannot rely on raw execution time in seconds, as this varies depending on the speed of the computer processor, hardware configurations, and system load. Instead, we use a **computer-independent model** to mathematically summarize algorithm runtimes.

---

# 1. Core Assumptions of the Sequential Computational Model

The model operates under four fundamental simplifications to standardize complexity analysis:

1. **Sequential Execution**: Instructions are executed one after the other, with no parallel processing.
2. **Infinite Memory**: We assume the computer has unlimited memory, allowing us to focus solely on instruction logic.
3. **Standard Unit Cost**: Every basic, simple instruction takes exactly **one unit of time**.
4. **Direct Instruction Counting**: We measure time complexity by directly counting all assignments, comparisons, and increments.

# 2. Standard Costs of Basic Operations

Under this model, we assign a unit cost of **1** to simple programmatic actions:

- **Assignments**: Cost of **1** (e.g., `x = 5;`).
- **Comparisons**: Cost of **1** (e.g., `x < n;`).
- **Increments / Decrements**: Cost of **1** (e.g., `x++;`).

# 3. Loop Overhead Mechanics

Analyzing a standard loop requires breaking down its initialization, boundary comparison, and increment steps. Let us analyze the overhead of the following loop:

```c++
for (int j=0; j<n; j++){
	//Instruction for loop here
}
```

- **Initialization** `(j=0)`: Executes exactly **1 time** at the start of the loop.
- **Boundary Comparison** `(j<n)`: Evaluates to `true` n times and `false` 1 time (to exit the loop). Thus, it executes n+1 **times**.
- **Increment** `(j++)`: Executes n **times** (at the end of each successful iteration).

$$ \text{ Total Loop Overhead Cost } = 1 + (n + 1) + n = 2n + 2 \text{ instructions } $$

⚠️ **Rule of Iterations**: Each statement located inside the repeated body of a loop has its cost multiplied by the total number of times the loop iterates.

# 4. Step-by-Step Counting Examples

Example A: Sequential Statements

```c
sum = 0;                // Cost: 1 (Assignment)
sum = sum + next;       // Cost: 1 (Assignment & Addition)
```

- **Total Cost**: 1+1=2.

Example B: A Single Summation Loop

```c
for (int i=1; i<=n; i++)    // Overhead: 1 + (n + 1) + n = 2n + 2
    sum = sum++;                // Body: executes n times (cost: n)
```

- **Total Cost**: $(2n+2)+n=3n+2$.$

Example C: Nested Loops (Quadratic Cost)

```c
k = 0;                                 // Cost: 1
for (int i = 0; i < n; i++)            // Overhead: 2n + 2
    for (int j = 0; j < n; j++)        // Runs n times. Overhead: n * (2n + 2) = 2n² + 2n
        k++;                           // Inner body: executes n * n times (cost: n²)
```

Let's sum these component costs:

1. **Outer assignment**: 1
2. **Outer loop overhead**: $2n+2$
3. **Inner loop overhead**: $2n^2+2n$
4. **Inner body increment**: $n^2$

$$ \text{Total Cost} = 1 + (2n + 2) + (2n^2 + 2n) + n^2 = \mathbf{3n^2 + 4n + 3} $$

---

# 🧠 Self-Reflection Check

_Look at Example C. Why does the inner loop overhead cost_ 2n2+2n_? Remember, the statement_ _for (int j = 0; j < n; j++)_ _is itself inside a loop that iterates_ n _times. Thus, its base overhead of_ 2n+2 _is multiplied by the outer loop's_ n _iterations!_