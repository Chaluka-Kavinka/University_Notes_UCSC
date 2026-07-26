**Introduction to Probability** is the study of experiments where the outcome is not known in advance or cannot be predicted with absolute certainty. It provides a way to quantify "how likely" it is that a specific event will occur.

---
# 1. The Probability Language

To speak the language of probability, you need to understand three core terms:

- **Random Experiment:** Any process that can be repeated where the results are uncertain, such as tossing a coin or rolling a die. Each repetition is called a **trial**.

- **Outcome:** The actual result of a single trial.

- **Sample Space (**S**):** The complete set of **all** possible outcomes.
	_Fancy Example:_ If you toss a coin three times, your sample space is the list of every possible sequence: {(H,H,H),(H,H,T),(H,T,H)…(T,T,T)}.

- **Event:** A specific outcome or a subset of the sample space.
	_Fancy Example:_ If you ask a student how many jeans they own, an **event** could be that they own an odd number {1,3,5,…} or no jeans at all {0}.

---
# 2. The Probability Scale

Probability is always a number between **0 and 1**.

- **0:** The event is impossible and cannot occur.

- **0.5:** The event is just as likely to happen as it is to fail.

- **1:** The event is a certainty; it will definitely occur.

- Values close to 0 mean "not likely," while values close to 1 mean "quite likely".

---
# 3. Three Ways to Guess the Future (Approaches)

The sources describe three ways we assign probability to events:

1. **Personal Opinion:** Based on subjective "vibes" or feelings. (e.g., "I think there is an 80% chance of rain today").

2. **Relative Frequency:** Based on doing an experiment many times (n) and counting how often event A happens (N(A)). The formula is $P(A)=nN(A)​$

3. **Classical/Formal Approach:** Based on mathematical axioms, where the total probability of the sample space must be exactly 1.

---
# 4. Key Relationship Rules

- **Independent Events:** The happening of one event has **zero influence** on the other.
	_Fancy Example:_ Getting a Head on your first coin flip doesn't change the odds of getting a Tail on your second flip.

- **Mutually Exclusive (Disjoint) Events:** Two events that **cannot happen at the same time**.
	_Fancy Example:_ You can get a Head or a Tail in one flip, but never both at once.

- **Complement of an Event** (**E′**): All outcomes in the sample space that are **not** part of event E.
	_Fancy Example:_ If 31.6% of households own a dog, the probability of the **complement** (not owning a dog) is 1−0.316=0.684.

---
# Short Note for Easy Remembering

| Term                   | Concept        | Formula/Logic                                  |
| ---------------------- | -------------- | ---------------------------------------------- |
| **Sample Space**       | The "Menu"     | Every possible choice.                         |
| **Independent**        | No Connection  | $P(A,B) = P(A) \times P(B)$                    |
| **Mutually Exclusive** | Can't Co-exist | $P(A∩B)=0$                                     |
| **Addition Rule**      | "A or B"       | $P(A∪B)=P(A)+P(B)−P(A∩B)$                      |
| **Complement Rule**    | "Not A"        | $P(A′)=1−P(A)$                                 |
| **Classical Axiom**    | The Total      | The probability of everything (S) is always 1. |

# Analogy for Understanding:

Think of probability like a **Pizza**. The **Sample Space** is the whole pizza. Each slice is an **Outcome**. If you are looking for the **Event** of "Pepperoni slices," you count those specific slices. The **Complement** is every slice that _doesn't_ have pepperoni. If you eat a Pepperoni slice and a Veggie slice, those are **Mutually Exclusive**—one bite cannot be both purely pepperoni and purely veggie at the exact same time!

---
# Lecture Notes

![[IS 1212 Handout 4 - Probability final.pdf]]