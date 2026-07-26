This module establishes the mathematical foundation for computing by exploring number systems, their properties, and fundamental operations.

---
# 1. Number Systems

Mathematics for computing begins with understanding different sets of numbers that form the **Real Number System**:

- **Natural Numbers ($\mathbb{N}$):** Also known as counting numbers or positive integers (e.g., 1, 2, 3...).
- **Whole Numbers ($\mathbb{W}$):** Natural numbers including zero (e.g., 0, 1, 2, 3...).
- **Integers ($\mathbb{Z}$):** The set of whole numbers combined with negative integers (e.g., ...-2, -1, 0, 1, 2...).
- **Rational Numbers ($\mathbb{Q}$):** Numbers that can be expressed as a ratio of two integers ($a/b$ where $b\not=0$). These include terminating or recurring decimals.

- **Irrational Numbers ($\mathbb{Q'}$):** Numbers that cannot be expressed as simple fractions (e.g., $\pi$ or $\sqrt{2}$).
- **Real Numbers ($\mathbb{R}$):** This includes nearly any number you can think of—all rational and irrational numbers—represented on the **Real Number Line**.

# 2. Basic Arithmetic and Order of Operations

Mastering calculations requires understanding the **|B|O|D|M|A|S| rule**, which dictates the order in which operations must be performed from left to right:

1. **B**rackets
2. **O**rder (Powers/Indices)
3. **D**ivision
4. **M**ultiplication
5. **A**ddition
6. **S**ubtraction

# 3. Properties of Signed Numbers

Directed numbers are prefixed by a positive (+) or negative (-) sign.

- **Addition:** If signs are the same, add the absolute values and keep the sign. If signs differ, subtract the smaller absolute value from the larger and keep the sign of the larger.
- **Subtraction:** To subtract a number, add its opposite $(x−y=x+(−y))$.
- **Multiplication/Division:** The result is positive if the signs are the same and negative if the signs are different.

# 4. Factors, Primes, and Multiples

- **Factor:** An integer $x$ is a factor of $y$ if x divides y without a remainder.
- **Prime Number:** A natural number greater than 1 divisible only by 1 and itself (e.g., 2, 3, 5, 7). Note that **2 is the only even prime number**.
- **Composite Number:** A natural number divisible by more than just 1 and itself.
- **Relatively Prime Numbers:** Two numbers are relatively prime if their only common factor is 1.

# 5. HCF and LCM

These concepts are vital for divisibility and algorithm efficiency:

- **Highest Common Factor (HCF/GCD):** The largest number that divides two or more numbers completely. Methods to find HCF include **listing factors**, **prime factorization** (using factor trees), and the **division method**.
- **Least Common Multiple (LCM):** The lowest possible number divisible by both numbers. It can be found via listing multiples, prime factorization, or the formula: 
- $$LCM(a,b)= \frac{(a×b)}{HCF(a,b)}$$

# 6. Fractions and Divisibility Rules

- **Operations on Fractions:** Includes reduction (simplification), addition/subtraction (requires a common denominator), multiplication (multiply numerators and denominators), and division (flip the second fraction and multiply).
- **Divisibility Rules:** Shortcuts to determine if a number is divisible by another without full division. For example:
    - **By 3:** The sum of digits is divisible by 3.
    - **By 5:** The last digit is 0 or 5.
    - **By 6:** The number is divisible by both 2 and 3.
    - **By 11:** The difference of the sum of alternating digits is divisible by 11.

# 7. Application in Computing

Divisibility rules are computationally "cheaper" than direct division. In **IoT and Big Data analysis**, using these rules to filter sensor data can significantly improve performance and scalability compared to using the modulus operator.