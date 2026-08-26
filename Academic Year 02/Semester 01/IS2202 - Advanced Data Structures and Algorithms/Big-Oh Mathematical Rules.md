When simplifying algorithm complexity equations into asymptotic notation, we apply a set of formal mathematical shortcut rules1. These rules allow us to quickly discard irrelevant details and focus purely on the asymptotic growth rate of the algorithm12.

---

# 1. Base of Logs is Ignored

## 📐 The Rule:

$$\log_a(n) = O(\log_b(n))$$ For any logarithmic complexity, the base of the logarithm (e.g., base 2, base 10, or natural log) is mathematically irrelevant and is completely ignored in Big-Oh notation1. All logarithmic functions belong to the same complexity class, written simply as $O(\log n)$1.

## 🧠 Mathematical Proof / Rationale:

To understand why, we recall the logarithmic **change-of-base formula**: $$\log_a(n) = \frac{\log_b(n)}{\log_b(a)}$$ Because the base values $a$ and $b$ are constants, the term $\frac{1}{\log_b(a)}$ is simply a **constant coefficient** (a multiplier)3. Under the golden rules of Big-Oh, we drop all constant coefficients34: $$\log_a(n) = \underbrace{\left(\frac{1}{\log_b(a)}\right)}_{\text{Drop Constant Coefficient}} \cdot \log_b(n) \implies O(\log_b(n))$$

# 2. Powers Inside Logs are Ignored

## 📐 The Rule:

$$\log(n^k) = O(\log n)$$ Any constant power $k$ inside a logarithm is ignored and simplifies directly to $O(\log n)$1.

## 🧠 Mathematical Proof / Rationale:

By applying the logarithmic **power rule**, we can pull the exponent out of the logarithm as a multiplier: $$\log(n^k) = k \cdot \log(n)$$ Since $k$ is a constant exponent, it becomes a constant coefficient multiplier3. Once again, because constant coefficients are dropped in Big-Oh analysis34, the expression simplifies: $$\log(n^k) = \underbrace{k}_{\text{Drop Constant Coefficient}} \cdot \log(n) \implies O(\log n)$$

- _Example:_ $O(\log(n^2))$ simplifies directly to $O(\log n)$1.


# 3. Bases and Powers in Exponents CANNOT Be Ignored

## 📐 The Rule:

Unlike logarithms, **exponents are highly sensitive**. You cannot ignore or swap the bases or powers of exponential growth curves1: $$a^n \text{ is not } O(b^n) \quad \text{when } a > b$$ $$2^{n^2} \text{ is not } O(2^n)$$

## 🧠 Mathematical Proof / Rationale:

- **Bases cannot be ignored:** Let's compare $3^n$ and $2^n$1. We can express $3^n$ as: $$3^n = \left(\frac{3}{2}\right)^n \cdot 2^n = (1.5)^n \cdot 2^n$$ As $n$ grows larger towards infinity, the factor $(1.5)^n$ grows infinitely large without bound45. Therefore, there is no single constant $c$ that can satisfy the Big-Oh requirement: $$3^n \le c \cdot 2^n \quad \text{for all } n \ge n_0$$ Thus, $3^n$ **is not** $O(2^n)$1.
- **Powers cannot be ignored:** Consider $2^{n^2}$ vs. $2^n$. The term $2^{n^2}$ can be rewritten as $(2^n)^n$. As $n \to \infty$, $(2^n)^n$ dominates $2^n$ by an infinite factor45. Therefore, $2^{n^2}$ **is not** $O(2^n)$.


# 4. Polynomial Degrees (The Highest-Order Rule)

## 📐 The Rule:

If $T(n)$ is a polynomial of degree $k$, then it simplifies directly to the highest-power term1: $$T(n) = a_k n^k + a_{k-1} n^{k-1} + \dots + a_1 n + a_0 \implies O(n^k)$$

## 🧠 Mathematical Proof / Rationale:

As we observed with the "swamping" effect of the percentage weight table, as $n$ approaches infinity, the highest-order term grows so aggressively that it dwarfs the contributions of all lower-order terms combined6. By dropping all lower-order terms and discarding the leading coefficient $a_k$, we arrive directly at $O(n^k)$1more_horiz.

- _Example:_ $T(n) = 13n^3 + 42n^2 + 2n\log n + 4n \implies \mathbf{O(n^3)}$ .

---

# 🧠 Self-Reflection Check

_Why is_ $\log(n^2) = O(\log n)$_, but_ $2^{n^2}$ _is not_ $O(2^n)$_?_

_Think about where the power lives! In_ $\log(n^2)$_, the power of 2 is inside a logarithm, which mathematically converts it into a_ **coefficient** _(a flat multiplier of 2) that can be easily factored out and discarded_1_. However, in_ $2^{n^2}$_, the exponent is on the variable itself. This changes the fundamental growth rate of the function from exponential to super-exponential, which creates an entirely different and faster-growing curve shape!_