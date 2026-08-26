Now that we have covered the mathematical definitions and calculations of Big-O, we can classify algorithms into **standard complexity classes** based on their growth curves. This allows us to predict how an algorithm will scale as inputs increase, for both **Time Complexity** (execution time) and **Space Complexity** (memory allocation).

---

# 1. The Asymptotic Growth Hierarchy

When comparing algorithms, we rank their growth rates from most efficient (slowest growing) to least efficient (fastest growing)1:

$$O(1) < O(\log n) < O(n) < O(n \log n) < O(n^2) < O(n^3) < O(2^n)$$

- **Green Zone (Highly Scalable)**: $O(1)$, $O(\log n)$, and $O(n)$. These algorithms handle massive datasets with ease.
- **Yellow Zone (Moderate Scalability)**: $O(n \log n)$. Typical of efficient sorting algorithms.
- **Red Zone (Poor Scalability)**: $O(n^2)$, $O(n^3)$, and $O(2^n)$. As $n$ grows, execution time or memory requirements quickly become astronomical2.

# 2. Time Complexity Classes with Concrete Code Examples

## 🟢 A. Constant Time — $O(1)$

The algorithm's execution time is **independent of the input size**3. Whether the input is 1 item or 1,000 items, the function always takes the same number of steps3.

- **Example Code**:

```c
function printFirstItem(arrayOfItems) {
    console.log(arrayOfItems); // Always takes 1 step
}
```

- **Key Characteristics**: No loops depend on the input size $n$.

## 🟢 B. Logarithmic Time — $O(\log n)$

With each step, the algorithm **reduces the problem size by a constant fraction** (typically half). This is highly efficient because even for billions of elements, the algorithm finishes in a handful of steps.

- **Classic Examples**:
    - **Binary Search**: Divides the search space successively into halves4.
    - **Binary Tree Search**: Navigates down a balanced search tree where the height is proportional to $\log n$45.

## 🟢 C. Linear Time — $O(n)$

The execution time grows **in direct proportion to the size of the input**6. If the input size doubles, the execution steps double6.

- **Example Code (Iteration and Traversal)**:

```c
function sayHelloNTimes(n) {
    for (var i = 0; i < n; i++) {
        console.log('hello'); // Runs n times
    }
}

function printAllItemsInArray(theArray) {
    theArray.forEach(function(item) {
        console.log(item); // Prints n times
    });
}
```

- **Scenario-Dependent Analysis**: Consider a linear search function:

```c
function contains(haystack, needle) {
    for (var i = 0; i < haystack.length; i++) {
        if (haystack[i] === needle) return true;
    }
    return false;
}
```

- **Worst-Case**: $O(n)$ (when the needle is at the very end of the array or not present at all)6.
- **Best-Case**: $O(1)$ (when the needle is found in the very first iteration)6.

## 🟡 D. Log-Linear Time — $O(n \log n)$

This class typically occurs when a linear-time operation is repeated logarithmic-time times. It is the **optimal theoretical limit for comparison-based sorting algorithms** (such as Mergesort or Heapsort).

## 🔴 E. Quadratic Time — $O(n^2)$

The execution time grows in proportion to the **square of the input size**. If the input size doubles, the run time quadruples.

- **Classic Example**: Nested loops where both loops iterate up to $n$57.

```c
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        // Nested operations execute n * n times
    }
}
```

# 3. Space Complexity Classes with Concrete Code Examples

**Space Complexity** refers to the amount of memory or storage space that an algorithm or function consumes based on the size of its input78.

## 🟢 Constant Space — $O(1)$ Space

An algorithm has constant space complexity if it **does not allocate any new variables** or structures whose size scales with the input size7.

- **Example Code**:

```c
function sayHelloNTimes(n) {
    for (var i = 0; i < n; i++) {
        console.log('hello'); 
    }
}
```

- _Why O(1)?_ The space remains constant because the function only uses a single variable `i` for loop control, regardless of how large `n` becomes7.

## 🔴 Linear Space — $O(n)$ Space

An algorithm has linear space complexity when the memory allocation **scales directly with the size of the input data**7.

- **Example Code**:

```c
function duplicateArray(arrayOfItems) {
    let helloArray = [];
    for (var i = 0; i < arrayOfItems.length; i++) {
        helloArray.push(arrayOfItems[i]); // helloArray grows with input size
    }
    return helloArray;
}
```

- _Why O(n)?_ The size of `helloArray` scales proportionally with the size of the input array `arrayOfItems`7.

---

# 📊 Reference Guide: Array Sorting Algorithms Complexity Matrix

The table below (compiled from the lecture's self-study materials) outlines the time and space complexity behaviors of common sorting algorithms:

|Algorithm|Best Time|Average Time|Worst Time|Worst Space Complexity|
|---|---|---|---|---|
|**Quicksort**|$O(n \log n)$|$O(n \log n)$|$O(n^2)$|$O(\log n)$|
|**Mergesort**|$O(n \log n)$|$O(n \log n)$|$O(n \log n)$|$O(n)$|
|**Timsort**|$O(n)$|$O(n \log n)$|$O(n \log n)$|$O(n)$|
|**Heapsort**|$O(n \log n)$|$O(n \log n)$|$O(n \log n)$|$O(1)$|
|**Bubble Sort**|$O(n)$|$O(n^2)$|$O(n^2)$|$O(1)$|
|**Insertion Sort**|$O(n)$|$O(n^2)$|$O(n^2)$|$O(1)$|
|**Selection Sort**|$O(n^2)$|$O(n^2)$|$O(n^2)$|$O(1)$|
|**Shell Sort**|$O(n)$|$O((n \log n)^2)$|$O((n \log n)^2)$|$O(1)$|
|**Bucket Sort**|$O(n+k)$|$O(n+k)$|$O(n^2)$|$O(n)$|
|**Radix Sort**|$O(nk)$|$O(nk)$|$O(nk)$|$O(n+k)$|

---

# 🧠 Self-Reflection Check

_Look at Heapsort versus Mergesort in the matrix. Both share an identical_ $O(n \log n)$ _time complexity across best, average, and worst cases. However, Mergesort requires_ $O(n)$ _extra space because it needs helper arrays to merge sorted segments, whereas Heapsort sorts completely in-place with_ $O(1)$ _extra space! This is a perfect example of the_ **Time vs. Space Complexity Trade-off** _we studied in Topic 01._