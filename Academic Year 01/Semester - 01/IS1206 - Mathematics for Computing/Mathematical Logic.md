Mathematical logic provides a formal, universal language with strict syntax to remove the ambiguity found in natural human communication. It is the backbone of programming, AI, and system specifications.

# 1. Propositions and Truth Values

- **Definition:** A proposition is a statement that is either **True (T)** or **False (F)**, but not both.
- **Types:**
    - **Primitive Proposition:** Cannot be broken down further.
    - **Compound Proposition:** Formed by combining simple propositions using logical connectives.
- **Not Propositions:** Questions, commands, or sentences with variables (e.g., $x+1=2$) are not propositions because their truth value is not fixed until variables are defined.

# 2. Logical Connectives and Truth Tables

These symbols allow us to build complex logical structures:

- **Negation ( $\neg p$ ):** "Not p." If p is True, ¬ p is False.
- **Conjunction ( $p \land q$ ):** "p and q." True only if **both** are true.
- **Disjunction ( $p \lor q$ ):** "p or q." True if **at least one** is true.
- **Exclusive OR ( $p \oplus q$ ):** True if **exactly one** is true, but not both.
- **Implication ( $p\rightarrow q$ ):** "If p, then q." It is only False if the hypothesis (p) is True but the conclusion (q) is False.
- **Biconditional ( $p\leftrightarrow q$ ):** "p if and only if q." True only when p and q have the **same truth value**.

# 3. System Specifications and Consistency

Logic is used to translate English requirements into unambiguous hardware and software specifications. A set of specifications is **consistent** if there is at least one assignment of truth values that makes every statement in the list true. If no such assignment exists, the system requirements are contradictory and inconsistent.

# 4. Tautologies and Equivalences

- **Tautology:** A compound proposition that is **always true**, regardless of the truth values of its components (e.g., $p \lor \neg{p}$).
- **Contradiction:** A proposition that is **always false** (e.g., $p \land \neg{p}$).
- **Logical Equivalence ( $\equiv$ ):** Two propositions are equivalent if they have identical truth tables. **De Morgan’s Laws** are essential here:  $$\neg{(p \land q)} \equiv \neg{p} \lor \neg{q}$$

# 5. Predicate Logic

When statements involve variables (like "$x > 3$"), we use **Predicates** ( $P(x)$ ). These become propositions once the variable is assigned a value or bound by a **Quantifier**:

- **Universal ( $\forall$ ):** The predicate is true for **every** element in the domain.
- **Existential ( $\exists$ ):** There is **at least one** element in the domain for which the predicate is true.