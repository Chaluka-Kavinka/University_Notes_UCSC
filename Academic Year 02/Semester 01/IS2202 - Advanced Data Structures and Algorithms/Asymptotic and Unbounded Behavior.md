When analyzing algorithms, we study how their runtimes behave as the input size $(n)$ grows arbitrarily large, approaching infinity. To describe these trends mathematically, computer scientists rely on the concepts of **limits, bounds, asymptotes, and unbounded behavior**.

---

# 1. Asymptotic Behavior (Approaching a Limit)

- **Asymptote**: An asymptote is a straight line that continually approaches a given curve but does not meet it at any finite distance.
- **Asymptotic Behavior**: This describes a function or expression that has a defined limit or asymptote. As you change the function's input, the output gets closer and closer to this limit but will **never actually reach or touch it**.

## 🍕 The Division Example $(f(x)= \frac {1}{x})$

- Consider the division function f(x)=1/x.
- If you plug in a massive number (approaching infinity) for x, you get 1 over a really huge number.
- While 1/∞ does not mean the value is exactly 0, the function has a **horizontal asymptote at 0**. This means the values of f(x) get extremely close to 0 but never actually touch 0.
- **Real-world Analogy**: Think of continually cutting a piece of pizza in half. No matter how many times you slice it, you will never quite reach a point of having exactly nothing.

# 2. Unbounded Behavior (Growth Without Limits)

- **Unbounded Behavior**: This occurs when a function or expression operates **without any limits**. As you increase the function's input, the output also increases continuously.
- Mathematically, a function is unbounded when its limit tends to positive infinity (+∞) or negative infinity (−∞). Interestingly, a function that **fluctuates (oscillates) infinitely** without settling into a bound is also classified as unbounded.

## 🍕 The Multiplication Example $(1⋅x)$

- A simple example of unbounded growth is multiplication, such as $1⋅x$.
- **Real-world Analogy**: If you have 5 ovens, you can cook 5 pizzas at once. If you had an infinite number of ovens, you could cook an infinite number of pizzas. As inputs scale, outputs grow completely without limit.

# 3. Classification of Bounds: Bounded vs. Unbounded Functions

Functions can be classified based on whether they have upper bounds, lower bounds, both, or neither:

## 📊 A. Fully Bounded Functions (e.g., $y = \sin(x)$)

- A function is bounded if it is constrained on both sides.
- **Example**: The trigonometric function $y = \sin(x)$ is bounded.
- **Limits**: Its upper bound is 1 (it never yields a value greater than 1) and its lower bound is −1 (it never yields a value smaller than −1).

## 📈 B. Partially Bounded Functions (e.g., $y = e^x$)

- Some functions are unbounded in one direction but bounded in another.
- **Example**: The exponential function 
$$y = e^x$$
- **Limits**: It is **unbounded from above** because it has no upper limit and increases to +∞. However, it is **bounded from below** because its output never drops below 0.

## 📉 C. Fully Unbounded Functions (e.g., $f(x) = x^3$)

- Some functions have no restrictions whatsoever.
- **Example**: The cubic function
- $$f(x) = x^3$$
- **Limits**: This function has **neither an upper nor a lower bound**. As x→+∞, f(x)→+∞. As x→−∞, f(x)→−∞.

# 4. Why This Matters for Algorithm Analysis

In computer science, we cannot easily predict the exact runtime of an algorithm down to the millisecond because of hardware variations. Instead, the mathematical concepts of limits and asymptotes allow us to **describe the behavior of runtime functions as they approach unreachable infinity**.

This asymptotic focus is why we use **Big O Notation**. We only care about the highest-order term (like $n^3$ dominating over $n^2$ or $n$) because, for sufficiently large problem sizes, the fastest-growing term completely **swamps and eclipses** all lower-order terms and constants.

---

# 🧠 Self-Reflection Check

_Think about memory leaks in software. If an algorithm continually allocates memory inside a loop without releasing it, the memory usage function $M(n)$ behaves like an unbounded function (similar to $e^x$). If we run it on a machine with physical limits, it will eventually crash the system! Conversely, an algorithm that keeps its memory usage tightly bounded (like $O(1)$ space complexity) is safe to run indefinitely._