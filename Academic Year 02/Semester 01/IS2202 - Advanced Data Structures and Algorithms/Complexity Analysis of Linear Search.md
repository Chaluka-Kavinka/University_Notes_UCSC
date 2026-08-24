Linear search (or sequential search) is the most straightforward search algorithm: it traverses an array from the very first element to the last, checking each index until the target element is found or the end of the array is reached.

Let's analyze its performance under the sequential computational model, identifying how its runtime behaves in different scenarios.

---

# 1. Best Case vs. Worst Case Scenarios

The runtime of sequential search is highly dependent on where the target item is located within the array:

- **🏆 Best Case Scenario**: The target element is found at **index 0**.
	The loop only needs to execute 1 **iteration** before returning a match.
- **⚠️ Worst Case Scenario**: The target element is found at the very last index (**index** n−1) or is **not present in the array** at all.
	The loop must execute for the full n **iterations**.

# 2. The Exact Worst-Case Cost Equation

Using our instruction-counting model, the slides define the total worst-case instruction count for sequential search as a polynomial:

$$ T_{\text{worst}}(n) = 3n + 3 \quad \text{instructions} $$

_(Note: The slides point out that "the last assignment does not always execute," but ask, "does one assignment really matter?" as the highest-order term will ultimately dominate)._

# 3. Deriving the Typical (Average) Case Complexity

To find a more realistic measure of everyday performance, we calculate the average or **typical case** using probability. We make two fundamental assumptions:

1. There is a **50/50 chance** that the target item is actually in the array.
2. If the target _is_ in the array, it is **equally likely to be at any index** (from 0 to $n−1$).

The Mathematical Derivation:

- **Scenario A (Not in array - 50% probability)**: We must check every single index, resulting in n **comparisons**.
- **Scenario B (Is in array - 50% probability)**: Since it is equally distributed, on average we will find it exactly halfway through, requiring $n/2$ **comparisons**.

By combining these two scenarios, we calculate the weighted average:

$$
\text{Typical Comparisons} = \left(\frac{1}{2} \times n\right) + \left(\frac{1}{2} \times \frac{n}{2}\right)
$$

$$
\text{Typical Comparisons} = \frac{n}{2} + \frac{n}{4} = \frac{3}{4}n \quad \text{comparisons}
$$

Thus, the typical average runtime of linear search is
$$\frac{3}{4}n \text{ comparisons}$$

# 4. Why is it called "Linear" Search?

If we plot the runtime function f(n) against the input size n, the resulting graph is a **straight line**. As the input size n increases, the execution time scales proportionally in a linear fashion.

---

# 🧠 Self-Reflection Check

_Why is it so important that the worst-case polynomial is $3n+3$ but we often simplify it to just "linear"?_

_Think back to our discussion of dominating terms. As $n$ grows extremely large (e.g., $n=1,000,000$), the difference between  $3n$ and $3n+3$ is negligible. The `constant +3` is eclipsed, and the linear growth rate $(n)$ is what truly dictates the algorithm's performance curve!_