This topic covers the rules for manipulating powers, roots, and their inverse operations, which are essential for understanding algorithmic complexity and data scaling in computing.

---
# 1. Understanding Indices (Exponents)

An expression written as $a^n$ means the variable a **(the base)** is raised to the **power of** $n$ **(the index or exponent)**. It represents how many times to multiply the base by itself.

## Laws of Indices

To simplify mathematical expressions in computing, students must master these seven laws:

1. **Multiplication Rule:** $$a^n \times a^m =a^{n+m}$$
2. **Power of a Power:** $$(a^n)^m = a^{nm}$$
3. **Power of a Product:** $$(ab)^n = a^n \times b^n$$
4. **Power of a Quotient:** $$(\frac{a}{b}​)^n = \frac{a^n}{b^n}​ \text{(where b = 0)}$$
5. **Division Rule:** $$\frac{a^n}{a^m} ​= a^{n−m} (\text{if } n \leq m) \text{ or } \frac{1}{a^{m−n}}​ (\text{if } n < m)$$
6. **Zero Index:** $$a^0 = 1 (\text{for } a \neq 0)$$
7. **Negative Index:** $$a^{−n} = \frac{1}{a^n}$$​

---
# 2. Roots and Surds

The $n^{th}$ **root** of $a$ is the number $b$ such that $b^n = a$.

- **Odd Roots:** Can be taken of negative numbers.
- **Even Roots:** Of negative numbers are **undefined** in real numbers.
- **Surds:** These are roots of rational numbers that cannot be exactly determined (e.g., $\sqrt{3}, \sqrt5$).

## Operations on Surds

- **Simplification:** Express a surd in terms of the smallest possible radical by extracting perfect powers (e.g., $\sqrt{50} = \sqrt{25 \times 2} = 5\sqrt{2}$​).
- **Addition/Subtraction:** Only **"like surds"** (those with the same index and radicand) can be added or subtracted.
- **Rationalizing the Denominator:** This involves multiplying the numerator and denominator by a surd to remove the radical from the bottom
	  e.g., $$\frac{1}{\sqrt{3}} = \frac{1}{\sqrt{3}} \times \frac{\sqrt{3}}{\sqrt{3}} = \frac{\sqrt{3}}{3}$$

---
# 3. Logarithms

Logarithms are the **inverse of exponentiation**.

- **Key Relationship:** If $N = a^x$, then $\log_a ​N = x$.
- **Common Logarithms:** Logarithms with **base 10**.
- **Natural Logarithms:** Logarithms with **base** $e (\approx 2.718)$, denoted as $ln \text{ or } \log_e$​.

## Laws of Logarithms

1. **Log of 1:** $$\log_a ​1 = 0$$
2. **Product Rule:** $$\log_a​ xy = \log_a ​x + \log_a ​y$$
3. **Quotient Rule:** $$\log_a \bigg(\frac{x}{y}​ \bigg) = \log_a ​x − \log_ a ​y$$
4. **Power Rule:** $$\log_a ​x^r = r \log_a ​x$$
5. **Change of Base Formula:** $$\log_b ​x = \frac{\log_a ​x}{\log_a ​b}​$$

---
# 4. Solving Exponential Equations

The strategy for solving equations like $5^{x^2} − 25^{6−2x} = 0$ is to:

1. **Rewrite** the equation so each side is a single exponential expression.
2. Express both sides using the **same base** (e.g., change $25$ to $5^2$).
3. **Set the exponents equal** to each other once the bases match.
4. Solve the resulting algebraic equation (often a quadratic).