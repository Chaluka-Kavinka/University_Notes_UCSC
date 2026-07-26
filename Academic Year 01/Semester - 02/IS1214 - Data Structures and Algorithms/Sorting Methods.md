Let's dive into the detailed breakdown of **Sorting Methods**, which is divided into five main parts. Sorting is defined as the process of arranging items in a specific order (ascending or descending) using a comparison operator.

# Part A: Basic Sorting Techniques

These are simple algorithms often easier to implement but generally have a time complexity of $$O(n^2)$$
- **Selection Sort:**
  This method finds the smallest element in the array and exchanges it with the first position (`A`). It then finds the next smallest and swaps it with the second position, repeating until the array is sorted. Its running time is always $O(n^2)$ regardless of the initial order.

![[Selection Sort - Algorithm.png]]

- **Insertion Sort:**
  It partitions an array into sorted and unsorted parts. It takes elements from the unsorted part one by one and "inserts" them into their proper location within the sorted part. It is most efficient $(O(n))$ when the array is already nearly sorted and least efficient $(O(n^2))$ in the worst case.

![[Insertion Sort - Algorithm.png]]

- **Bubble Sort (Exchange Sort):**
  One of the simplest algorithms, it repeatedly passes through the list, comparing adjacent elements and swapping them if they are in the wrong order. After each pass, the next largest element "bubbles" up to its correct position. Its complexity is $O(n^2)$ for best, average, and worst cases.

![[Bubble Sort - Algorithm.png]]

# Part B: Advanced Comparison-Based Sorting (Merge & Shell)

These methods are designed to be faster for large datasets.

- **Merge Sort:**
  A **Divide-and-Conquer** algorithm. it recursively splits the unsorted list into halves until each sub-list has only one element (which is inherently sorted). It then merges these sublists back together in sorted order.

- **Shell Sort:**
  This is an improved version of Insertion Sort. Instead of moving elements one position at a time, it compares and swaps elements that are far apart using a **"gap" or increment**. This reduces the total number of shifts required to sort the list.

# Part C: Advanced Comparison-Based Sorting (Quick Sort)

- **Quick Sort:**
  Also a **Divide-and-Conquer** strategy, it is widely considered the best sorting algorithm for sequential computers. It works by selecting a **pivot** element and partitioning the array so that all elements smaller than the pivot are on its left and larger elements are on its right. The sub-arrays are then sorted independently in a recursive way.

# Part D: Heap Sort and Priority Queues

- **Heaps:**
  A heap is a special binary tree where every node's value is greater than or equal to the values of its children.

- **Heap Sort:**
  This algorithm uses the heap structure to sort elements. It involves building a heap (using **upheap** and **downheap** operations to maintain the heap property) and then repeatedly removing the largest item to build the sorted list. Heaps are also the primary way to implement **Priority Queues**.

# Part E: Non-Comparison-Based Sorting

These algorithms do not compare elements against each other and can sometimes achieve linear time complexity.

- **Counting Sort:**
  This counts the frequency of each distinct element and uses that information to place elements directly into their sorted positions. It is very efficient when the range of input values is small.

- **Radix Sort:**
  A linear sorting algorithm for integers that sorts data digit-by-digit, starting from the **Least Significant Digit (LSD)** to the most significant.

- **Bucket Sort:**
  This distributes elements into various "buckets" based on their value ranges. Each bucket is then sorted individually (often using Insertion Sort) before being concatenated to form the final sorted list. Its worst-case complexity is $O(n^2)$ if all elements fall into a single bucket.

---
# Key Comparison Factors to Remember:

- **Speed:** Simple algorithms are $O(n^2)$; advanced ones like Merge Sort and Quick Sort are typically $$O(n\log{n})$$
- **Storage:** "In-place" algorithms are best because they only need $O(N)$ memory.
- **Stability:** This refers to whether the algorithm keeps the relative order of elements with equal keys.

---
# Lecture Notes
![[DSA - Lecture 08.pdf]]