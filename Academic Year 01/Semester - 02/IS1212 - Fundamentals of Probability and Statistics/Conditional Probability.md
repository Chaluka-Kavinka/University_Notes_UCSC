**Conditional Probability** is the science of updating our "guesses" based on new information. It describes the probability of an event (A) occurring, given that another event (B) has already happened.

---

# 1. The Notation and Formula

We write this as $P(A∣B)$, which is read as the **"probability of A, given B"**.

- **The Golden Rule:** To find the conditional probability, you take the probability of both events happening together and divide it by the probability of the event that is already certain.
- **Formula:** $$P(A∣B)=\frac{P(A∩B)}{P(B)}$$(where $P(B)>0$)
- **The Inverse:** Similarly, $$P(B∣A)=\frac{P(A∩B)}{P(A)}$$
- **Byers's Law:** $$P(A∣B) = \frac{P(B|A) \times P(A)}{P(B)}$$
- **A Special Fact:** $P(B∣B)$ is always **1**, because if we know B has happened, the chance of B having happened is 100%.

---
# 2. Fancy Examples from the Sources

- **The Card Shark:** Suppose you pick a card at random. I tell you, "It’s a heart!" Now, what is the probability it is a picture card (Jack, Queen, or King)?
	- Normally, there are 52 cards. But because you know it's a **Heart** (13 cards), your "world" has shrunk. There are 3 picture cards in the hearts.
	- **Result:** $P(Picture∣Heart) = \frac{3}{13}$.

- **The Lucky Die:** You roll a die and I tell you, "It's an odd number!" What is the chance it is a prime number?
	- The odd numbers are {1,3,5}. Out of these, only {3,5} are prime.
	- **Result:** $P(Prime∣Odd) = \frac{2}{3}$.

- **The Car Salesman:** Imagine 90% of cars have Air Conditioning (AC) and 35% have both AC and GPS. If a car has AC, what is the chance it also has GPS?
	- **Result:** $P(GPS∣AC) = \frac{0.35}{0.90} ​≈ 0.3889$ (or about 39%).

---

# 3. Advanced Tools: Total Probability and Bayes' Theorem

- **Law of Total Probability:** Sometimes an event A can happen through several different "scenarios" $(B1​,B2​,…,Bn​)$. To find the total probability of A, you add up the probability of A happening in each scenario.
	_Example:_ The probability a car starts in the morning depends on if it rained (P=0.6) or didn't rain (P=0.9). You combine these based on how likely it was to rain.

- **Bayes’ Theorem (The "Detective" Formula):** This allows us to work backward. If we see an effect (B), what is the probability it was caused by a specific event (A)?.
	_Medical Example:_ If a laboratory test for a disease comes back positive, Bayes' Theorem helps calculate the actual probability that the person has the disease, taking into account the test's accuracy and how common the disease is in the population.

---

# 4. Conditional Probability and Independence

Two events are **Independent** if the occurrence of one has **no effect** on the probability of the other.

- **The Test:** If $P(A∣B)=P(A)$, then A and B are independent.

- **Meaning:** Knowing that B happened didn't change your "guess" for A at all.

---

# Short Note for Easy Remembering

| Concept            | Symbol / Formula            | Easy Logic                          |
| ------------------ | --------------------------- | ----------------------------------- |
| **Conditional**    | $P(A$                       | $B)$                                |
| **Calculation**    | $\frac{P(Both)}{P(Given)}$​ | Divide the "both" by the "certain". |
| **Multiplication** | $P(A \cap B) = P(A$         | $B)P(B)$                            |
| **Total Prob.**    | $\sum P(A$                  | $B_i)P(B_i)$                        |
| **Independence**   | $P(A$                       | $B) = P(A)$                         |

**Analogy for Understanding:**
	Imagine you are at a **cafeteria**. The probability that someone orders **Fries** is P(Fries). However, if you see them holding a **Burger**, the probability they will order fries usually goes up! That new, higher probability is P(Fries∣Burger). If they are a health nut and the burger doesn't change their chance of getting fries, then fries and burgers are **Independent**.

---
# Lecture Notes
![[IS 1212 Handout 5 - Conditional Probability.pdf]]