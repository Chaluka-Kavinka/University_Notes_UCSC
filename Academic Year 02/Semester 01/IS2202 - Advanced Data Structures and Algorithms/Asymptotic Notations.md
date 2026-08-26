Having studied asymptotic and unbounded behaviors, we now introduce the formal language computer scientists use to analyze, classify, and compare the efficiency of different algorithms: **Asymptotic Notations**.

---

# 1. What is Asymptotic (Big-O) Notation?

**Asymptotic Notation** (commonly referred to generally as $Big-O$ Notation) is the mathematical language we use to describe the complexity of an algorithm. It allows us to compare the efficiency of different algorithmic approaches to a problem by expressing their runtimes in terms of **how quickly they grow relative to the input size $(n)$ as the input gets larger**.

- **Focus on Growth Rate**: It is highly difficult to determine the exact execution time of an algorithm because it depends on the processor speed, compiler, and hardware. Instead of direct time measurements, we use asymptotic notation to describe the **growth profile** of the runtime.
- **Arbitrarily Large Inputs $(n→∞)$**: Our code may contain small setup steps that seem expensive when n is small, but these are completely eclipsed as $n$ scales. In asymptotic analysis, we focus purely on the fastest-growing term.

---

# 2. The Three Major Asymptotic Notations

To describe how an algorithm behaves at scale, we utilize **three primary notations** to establish boundaries on its runtime:

```
      c·f(n) [Upper Bound]               c2·g(n) [Upper Bound]
         \                                  \ 
       T(n) \                             T(n) \
         \   \                               \   \
          \___\___                            \___\___
               \                                   \
             n0 [Threshold]                      c1·g(n) [Lower Bound]

     (a) Big-Oh Notation                  (b) Big-Theta Notation
```

## 📈 A. Big-Oh (O) Notation — The Asymptotic Upper Bound

- **Definition**: Big-Oh defines an **upper limit** on an algorithm's growth rate, bounding the function strictly from above. It represents the **worst-case scenario** (though it can technically cover better cases too).
- **Mathematical Definition**: We say that $T(n)=O(f(n))$ if there exist positive constants c and n0​ such that:

$$T(n) \leq c⋅f(n) \quad \text{for all} \quad n \geq n_0$$​

_(Note: Some course slides represent this boundary strictly as $T(n)<c⋅f(n)$ for all $n≥n0$​)._
- **Visualizing the Bound**: Beyond the threshold input size n0​, the scaled function c⋅f(n) will always lie **above** the actual runtime curve T(n).
- **Example**: Insertion Sort runs in linear time in the best case and quadratic time in the worst case; we can write its overall complexity as O(n2) because quadratic growth safely bounds all possible outcomes.

📉 B. Big-Omega ((\Omega)) Notation — The Asymptotic Lower Bound

- **Definition**: Big-Omega defines a **lower limit** on an algorithm's growth rate, bounding the function strictly from below. It represents the **best-case scenario** (the absolute minimum resources the algorithm will consume).
- **Mathematical Definition**: We say that T(n)=Ω(g(n)) if there exist positive constants c and n0​ such that: T(n)≥c⋅g(n)for all n≥n0​
- **Visualizing the Bound**: Beyond the threshold input size n0​, the scaled function c⋅g(n) acts as an floor, always lying **below** the actual runtime curve T(n).

⚖️ C. Big-Theta ((\Theta)) Notation — The Asymptotic Tight Bound

- **Definition**: Big-Theta defines a **tight bound** that sandwiches the function from both above and below. It indicates that the algorithm's actual runtime grows at the exact same rate as the bounding function.
- **Mathematical Definition**: We say that T(n)=Θ(g(n)) if there exist positive constants c1​, c2​, and n0​ such that: c1​⋅g(n)≤T(n)≤c2​⋅g(n)for all n≥n0​
- **Visualizing the Bound**: Beyond n0​, the actual runtime curve T(n) is locked tightly inside the "envelope" created by c1​⋅g(n) and c2​⋅g(n).

---

3. Justifying the Simplification (The "Swamping" Effect)

Focusing only on the highest-order term and discarding constants is a massive simplification, but it is mathematically justified because **for sufficiently large problem sizes, the highest-order term completely dominates ("swamps") all lower terms**.

Consider the function representing a program's step-count, R(x)=x2+3x+5:

- At x=10: the quadratic term (x2=100) contributes **74%** of the total value (R=135).
- At x=1,000: the quadratic term (x2=1,000,000) contributes **99.7%** of the total value (R=1,003,005).
- At x=100,000: the quadratic term contributes **99.997%** of the total value (R=10,000,300,005).

As x grows large, the contribution of 3x+5 shrinks to mathematical irrelevance.

---

4. Visualizing the Growth Rate Curves

When designing systems, we classify algorithms into standard **complexity classes**. Their growth curves dictate how they scale as inputs increase:

|Complexity Class|Name|Scaling Behavior (As n doubles)|
|---|---|---|
|O(1)|Constant Time|Unaffected by input size.|
|O(logn)|Logarithmic Time|Increases by a tiny, constant amount.|
|O(n)|Linear Time|Proportional double in runtime.|
|O(nlogn)|Log-Linear|Slightly worse than linear.|
|O(n2)|Quadratic Time|Runtimes quadruple (4×).|
|O(2n)|Exponential Time|Doubling the input squares the complexity; highly unscalable.|

---

🧠 Self-Reflection Check

_Why do we say that_ O(n2) _covers linear time?_

_Remember, Big-Oh is an upper bound (a ceiling). If you promise your boss that an algorithm will take "at most_ O(n2) _steps," and it finishes in_ O(n) _steps, you have still kept your promise! To specify that an algorithm takes exactly quadratic time (not better, not worse), we must use the tight bound: (\Theta(n^2))._