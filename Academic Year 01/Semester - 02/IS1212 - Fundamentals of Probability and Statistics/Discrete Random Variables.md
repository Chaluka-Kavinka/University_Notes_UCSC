>[!tip]
>**Discrete Random Variables**, which are tools used to summarize the numerical results of random experiments where the specific values cannot be predicted with certainty.

---
# 1. What is a Random Variable?

A random variable $(X)$ is essentially a function that maps outcomes from an experiment's sample space $(\ohm)$ to real numbers $(\mathbb{R})$.

- **Discrete Random Variable:**
  A variable is "discrete" if the values it can take are **finite** or countable.
- **Fancy Example:**
  If you toss a coin three times, the outcomes are sequences like *HHH* or *THT*. A random variable $X$ could be "the number of Heads observed," turning the outcome *HHT* into the number **2**.

# 2. Probability Distributions

The **probability distribution** of $X$ describes how "probability mass" is spread across all possible values in its sample space $(\ohm_{X}​)$. This is usually defined by a **probability function** $p_x​(x)$, which equals $P(X=x)$.

- **Key Condition:**
  The sum of all probabilities in a distribution must always equal **1**.
- **Functions of Variables:**
  You can create new random variables by applying math to old ones, such as $2X+5$ or $X^2$.

# 3. Expectation: The "Center" 

The **Expectation** or **Expected Value** $E(X)$ is the theoretical mean of the distribution. It represents the average value you would get if you repeated the experiment many times.

- **Formula:** $$E(X)=∑xP(x)$$
- **Fancy Example (The Die Game):**
  Suppose you play a game with a fair die where you win $20 for a "2", $40 for a "4", and lose $30 for a "6". The **Expected Value** helps you decide if the game is worth playing by calculating the average "win" per roll.

- **Special Properties:**
	- $E(aX+b)=aE(X)+b$ (where a and b are constants)
	- $E(X+Y)=E(X)+E(Y)$

--------------------------------------------------------------------------------

# 4. Variance & Standard Deviation: The "Spread"

While the mean tells you the center, **Variance** $Var(X)$ measures how much the values "spread out" around that center.

- **Standard Deviation (σ):**
  This is the square root of the variance. It is the most common measure of spread because it uses the **same units** as the original data.
- **The "Shortcut" Formula:** $$Var(X)=E(X^2)−[E(X)]^2$$
- **Special Properties:**
	- $Var(cX)=c^2Var(X)$
	- $Var(constant)=0$
	- If X and Y are **independent**, then $Var(X±Y)=Var(X)+Var(Y)$

---
# Short Note for Easy Remembering

| Concept                  | What it is                 | Math Logic / Shortcut              |
| ------------------------ | -------------------------- | ---------------------------------- |
| **Random Variable**      | A "Translator"             | Turns "Heads/Tails" into "0, 1, 2" |
| **Discrete**             | Countable                  | Like steps on a ladder (no gaps)   |
| **Probability Function** | The "Map"                  | $P(X=x)$; total sum must be 1      |
| **Expectation $E(X)$**   | The "Long-term Average"    | $∑(Value \times Probability)$      |
| **Variance $Var(X)$**    | The "Shake"                | How much results vary from average |
| **Std. Deviation (σ)**   | The "Unit-friendly Spread" | $\sqrt{Variance}$​                 |

**Analogy for Understanding:** Imagine you are **playing a lottery.** The **Random Variable** is the amount of money you could win. The **Probability Distribution** is the list of prizes and the odds of winning each one. The **Expectation** is the average amount of money you’d get back per ticket if you bought millions of them. The **Standard Deviation** tells you how "risky" the lottery is—a high SD means you might win nothing or win the jackpot (high variability), while a low SD means most prizes are very close to the average win.

---
# Lecture Notes
![[IS 1212 Handout 7 - Discrete Random Variable.pdf]]