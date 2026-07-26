>[!tip]
>**Independent events** occur when the happening of one event does not influence the probability of the other happening in any way. In other words, if two events are independent, the information that one has occurred leaves the probability of the other unchanged.

# 1. The Formal "Independence Test"

To mathematically prove that two events (A and B) are independent, you can use these properties from the sources:

- **The Multiplication Rule:** $P(A∩B)=P(A)×P(B)$.

- **The Conditional Rule:** $P(A∣B)=P(A)$ and $P(B∣A)=P(B)$.

    ◦ _Meaning:_ Knowing B happened did nothing to the original probability of A.

# 2. Fancy Examples from the Sources

- **The "Reset" Button (Replacement):** Imagine a bag with 5 red and 7 black counters.
	- If you draw a red counter, **put it back**, and then draw again, the second draw is **independent** of the first because the bag is exactly the same as when you started.
	- If you **did not** put it back, the events would be **dependent** because the total number of counters would have changed.

- **The Double Die Throw:** If you throw a die twice, getting a "4" on the first throw does not affect your chances of getting an odd number on the second throw. Each throw is a "fresh start".

# 3. Independence of Multiple Events

Independence can involve more than just two events. For three events (A,B, and C) to be **mutually independent**, they must satisfy several conditions simultaneously:

1. Every pair must be independent (e.g., P(A∩B)=P(A)P(B)).

2. The group must be independent: P(A∩B∩C)=P(A)P(B)P(C).

If these events are mutually independent, then combinations of them are also independent. For example, event A would be independent of the combined event "B or C".

# 4. Key Properties to Remember

- **The Complement Rule:** If A and B are independent, then A and the "not B" (B′) are also independent.

- **Independence vs. Mutually Exclusive:** These are often confused. Mutually exclusive events **cannot** happen at the same time (P(A∩B)=0), whereas independent events **can** happen together—they just don't affect each other's odds.

---
# Short Note for Easy Remembering

| Concept                 | Key Logic                          | Formula                        |
| ----------------------- | ---------------------------------- | ------------------------------ |
| **Independence**        | "No influence"                     | $P(A∩B)=P(A)×P(B)$             |
| **The "With" Rule**     | **With** replacement = Independent | $P(A∩B)=P(A)P(B)$              |
| **The Conditional**     | The "Given" is ignored             | $P(A∣B) = P(A)$                |
| **Mutual Independence** | Works for 3+ events                | All pairs + the trio must work |

**Analogy for Understanding:**
	Think of **independent events** like **two people watching the same movie in different cities.** Whether Person A buys popcorn $(EventA)$ has absolutely no effect on the probability that Person B will buy a soda $(EventB)$. Their choices are totally separate. However, if they were **sharing one bucket of popcorn** (Dependent), Person A taking a huge handful would definitely change the probability of how much popcorn is left for Person B!

---
# Lecture Notes
![[IS 1212 Handout 6 - Independent Events.pdf]]