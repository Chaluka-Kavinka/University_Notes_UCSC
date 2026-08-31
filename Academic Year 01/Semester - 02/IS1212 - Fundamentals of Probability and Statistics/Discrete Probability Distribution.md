>[!tip]
>**Discrete Probability Distributions** describe how probabilities are spread across the possible values of a discrete random variable. A valid probability mass function $(pmf)$, denoted as $f(x)$, must ensure that every individual probability is between 0 and 1, and the sum of all probabilities equals exactly 1.

---
# 1. Discrete Uniform Distribution (The "Equal Chance" Model)

In this simplest model, every possible outcome has an equal chance of occurring.

- **The Logic:**
  If there are $n$ outcomes, each has a probability of $1/n$.
- **Fancy Example:**
  Choosing one of the **6 Infinity Stones** at random from a bag. Each stone has a $1/6$ chance of being picked.
- **Stats:** 
	- Mean $$E(X)=\frac{(n+1)}{2}$$ or if it in middle range $$E(X)=\frac{(a+b)}{2}$$
	- Variance $$Var(X)=\frac{(n^2−1)}{12}$$ or $$Var(X)=\frac{[(b-a+1)^2−1]}{12}$$
# 2. Bernoulli & Binomial (The "Success vs. Failure" Models)

- **Bernoulli Distribution:**
  A single trial with only two outcomes: "Success" (the outcome of interest) or "Failure".

>_Example:_ Flipping a coin once to see if it's "Heads".

- **Binomial Distribution:**
  This happens when you repeat independent Bernoulli trials $n$ times with a constant probability of success $p$.

>**Fancy Example:**
>A basketball player has a 70% chance (p=0.7) of making a free throw. The Binomial distribution predicts the probability of them making exactly 8 out of 10 shots (n=10).

>**Stats:** Mean $E(X)=np$; Variance $Var(X)=npq$ $($where $q=1−p)$.

The **probability mass function (PMF)** of the **binomial distribution** gives the probability of obtaining exactly k successes in n independent Bernoulli trials, each with success probability p. 
### Formula:
$$P(X = k) = \binom{n}{k} p^k (1 - p)^{n - k}$$
$$
P(X = k) = \binom{n}{k} p^k (1 - p)^{n - k}, \quad k = 0, 1, 2, \dots, n
$$   
for k=0,1,2,…,n, where:

- $\binom{n}{k​}=\frac{k!}{(n−k)!n!}​$ is the **binomial coefficient** (number of ways to choose k successes from n trials),
- p is the probability of success,
- 1−p is the probability of failure.
# 3. Poisson Distribution (The "Rare Events" Model)

Used for events that occur randomly over a fixed interval of time or space.

- **The Logic:** It depends on the mean number of occurrences $(λ)$.
- **Fancy Example:** Counting the number of **falling stars** seen in one hour or the number of bacteria in 1ml of liquid.
- **Stats:** Mean $E(X)=λ$; Variance $Var(X)=λ$.
## Key Characteristics

- **Discrete**: Only non-negative integers (0, 1, 2, ...) are possible outcomes. 
- **Single Parameter**: Defined entirely by λ (lambda), the average rate of occurrence.
- **Independence**: Events occur independently of each other. 
- **Constant Rate**: The average number of events per interval ( λ ) remains constant.
- **Rare Events**: Often used for events that are infrequent but have many opportunities to occur.

As **λ** increases, the distribution becomes more symmetric and approaches a normal distribution.
## Probability Mass Function (PMF)

The probability of observing exactly k events in a fixed interval is given by the Poisson probability mass function:
$$P(X=k)=\frac{e^{−λ}λ^k}{k!}$$​
Where:
- k = number of occurrences (0, 1, 2, ...)
- λ = average number of occurrences in the interval ( λ>0 )
- e ≈ 2.71828 (Euler’s number) 

This formula is derived as a limiting case of the binomial distribution when the number of trials n→∞ and the probability of success p→0, such that np=λ remains constant.

# 4. Geometric & Negative Binomial (The "Waiting" Models)

- **Geometric Distribution:** Measures the number of trials needed until the **very first success** occurs.
>**Fancy Example:** Flipping a coin repeatedly until you get your first "Heads".

- **Negative Binomial Distribution:** A generalization of geometric; it measures the number of trials until the $k^{th}$ success happens.
>**Fancy Example:** An oil company drills wells (20% success rate) and wants to know the probability that their **3rd strike** happens on the **7th well** drilled.

# 5. Hyper-geometric Distribution (The "No-Replacement" Model)

Used when you are selecting items from a finite population **without replacement**, meaning the trials are _not_ independent.

>**Fancy Example:** Drawing 5 cards from a small deck of 20 cards (6 red, 14 black) and calculating the chance of getting exactly 4 red cards.

---
# Short Note for Easy Remembering

| Distribution       | Key "Vibe"        | Formula Trigger          | Mean           |
| ------------------ | ----------------- | ------------------------ | -------------- |
| **Uniform**        | Pure Fairness     | 1/n (Each is equal)      | $(n+1)/2$      |
| **Bernoulli**      | One Shot          | Success (p) or Failure   | $p$            |
| **Binomial**       | Multi-Trial       | n trials, fixed p        | $np$           |
| **Poisson**        | Time/Space        | Rare events (λ)          | $λ$            |
| **Geometric**      | Wait for $1^{st}$ | Trials until 1st success | $\frac{1}{p}$  |
| **Neg. Binomial**  | Wait for $k^{th}$ | Trials until k successes | $\frac{k}{p}$  |
| **Hypergeometric** | No Replacement    | Finite "Pool" (N, k, n)  | $\frac{nk}{N}$ |

**Analogy for Understanding:** Imagine you are **fishing**.

• If every fish in the pond is equally likely to bite, that's **Uniform**.

• If you want to know the chance of catching 5 fish in 10 casts, that's **Binomial**.

• If you want to know how many casts it takes to catch your _first_ fish, that's **Geometric**.

• If you are counting how many fish swim by your boat every hour, that's **Poisson**.

• If you catch fish and **keep them in a bucket** (don't throw them back), the changing odds of your next catch follow the **Hyper-geometric** distribution!

---
# Lecture Notes
![[IS 1212 Handout 8 - Discrete Probability Distribution I.pdf]]
![[IS 1212 Handout 9 - Discrete Probability Distribution II.pdf]]