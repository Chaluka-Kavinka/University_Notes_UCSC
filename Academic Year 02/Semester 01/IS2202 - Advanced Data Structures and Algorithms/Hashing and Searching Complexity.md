# 1. Searching Algorithms

Searching is the process of finding a target element t within a collection C. Different algorithms offer varying performance based on whether the data is sorted.

- **Sequential/Linear Search:** Successively checks each element in a list until a match is found.
    - **Complexity:** Best: $O(1)$; Average/Worst: $O(n)$.
- **Binary Search:** Successively divides a **sorted** array in half to locate the target.
    - **Complexity:** Average: $O(\log n)$; Worst: $O(n)$ if the tree is unbalanced.
- **Jump Search:** Works on **sorted** arrays by jumping ahead by fixed blocks of size $\sqrt{n}$​ and then performing a linear search backward once the target range is found.
    - **Complexity:** $O(\sqrt{n}​)$, placing it between linear and binary search.
- **Interpolation Search:** An improvement on binary search for **uniformly distributed** sorted data. It calculates a "probe" position based on the value of the target.
    - **Complexity:** $O(\log (\log n))$ for uniform data.

# 2. Direct-Address Tables

A technique where each key $k$ corresponds directly to a slot $k$ in an array.

- **Pros:** Search time is reduced to $O(1)$.
- **Cons:** If the universe of keys U is large, the table size becomes impractical, and if actual keys are few, most space is wasted.

# 3. Hash Tables and Hash Functions

A hash table uses a **Hash Function (**h**)** to map a key k to a specific slot h(k) in a table of size m. Ideally, the search time is O(1) on average.

**A. Components of a Hash Function**

The process typically involves two steps: h(key)=h2​(h1​(x)).

1. **Hash Code Map (**h1​**):** Converts keys (like strings) into integers.
    - **Integer Cast:** Interprets bits as an integer.
    - **Summing Components:** Sums the integer values of characters in a string.
    - **Polynomial Accumulation:** Uses a polynomial (e.g., x0​+x1​a+x2​a2...) to spread values more effectively.
2. **Compression Map (**h2​**):** Maps integers into the range [0,m−1].
    - **Division Method:** h(k)=kmodm. Choosing a **prime number** for m helps spread values.
    - **Multiplication Method:** Multiplies key k by a constant A and extracts the fractional part to determine the index.
    - **Mid-Square:** Squares the key and extracts the middle digits.
    - **Folding:** Divides the key into parts and sums them.

**4. Universal Hashing**

To prevent a "malicious adversary" from choosing keys that all hash to the same slot (causing O(n) performance), **Universal Hashing** selects a hash function at random from a carefully designed class of functions at the start of execution.

- **MAD Method (Multiply Add and Divide):** A common universal hash function: h(k)=[(ak+b)modp]modm, where p is a large prime.

**5. Collision Resolution**

Collisions occur when two different keys hash to the same slot. The **Load Factor (**α=n/m**)** represents the table's fullness.

**A. Chaining**

All elements hashing to the same slot are placed in a **linked list**.

- **Average Search Time:** Θ(1+α).
- **Overflow Area:** A variation where a pre-allocated section of the table is reserved specifically for collisions, potentially making access faster.

**B. Open Addressing**

All elements are stored directly in the table. If a collision occurs, the algorithm "probes" for the next available slot.

- **Linear Probing:** Checks the next slot (i,i+1,i+2...). It is easy to implement but suffers from **primary clustering** (long runs of occupied slots).
- **Quadratic Probing:** Uses a quadratic formula to determine the next slot, reducing clustering.
- **Double Hashing:** Uses a second hash function to determine the probe interval: h(k,i)=(h1​(k)+i⋅h2​(k))modm. This is one of the best methods for open addressing.

**6. Perfect Hashing**

Used for **static sets** of keys (data that never changes, like files on a CD-ROM). It uses a two-level hashing scheme to guarantee O(1) **search time in the worst case**.

**7. Applications of Hashing**

- Dictionaries and spell checkers.
- Databases and compilers (symbol tables).
- Cryptography.
- Game board lookups (Chess, Tic-Tac-Toe).
- Quick command lookups in a UNIX shell .