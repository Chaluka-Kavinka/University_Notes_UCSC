A **Queue** is a linear data structure designed to process items in a specific sequence, following the **FIFO (First-In, First-Out)** principle. Unlike a stack, where you only use one end, a queue uses both: one end for adding data and the other for removing it.

# 1. Key Components and Operations

To manage a queue, the computer tracks two specific positions:

- **Rear (or Back):** Where new elements are **inserted** (the **Enqueue** operation).

- **Front:** Where existing elements are **removed** (the **Dequeue** operation).

## Boundary Conditions to Remember:

- **Overflow:** Occurs when you try to `Enqueue` an item into a queue that is already full (`Rear = Max - 1`).

- **Underflow:** Occurs when you try to `Dequeue` an item from an empty queue (`Front = -1`).

# 2. Fancy Examples of Queues

- **In the Real World:** People standing on an **escalator** or cars waiting at a **gas station** pump. The first person to step on or the first car to arrive is the first to leave.

- **In Computing:** An office **printer queue** where multiple documents are sent to one printer; the computer processes them in the exact order they were received.

- **In Operating Systems:** A **Ready Queue** in memory where programs wait for their turn to be processed by the CPU.

# 3. Special Types of Queues

- **Circular Queue:** In a standard linear queue, once the "Rear" reaches the end, the queue might signal it is "Full" even if there are empty spaces at the front. A circular queue solves this by treating the memory like a **circle**, where the last position connects back to the first.

- **Priority Queue:** Elements are assigned a **priority value**. Items with higher priority are processed before others, regardless of when they arrived. These are efficiently implemented using a **Heap** structure.

---

# Short Note for Memory:

• **FIFO:** **F**irst **I**n, **F**irst **O**ut.

• **Enqueue:** Add to the **Rear**.

• **Dequeue:** Remove from the **Front**.

• **Circular Queue:** Reuses "empty" slots at the beginning to save memory.

• **Priority Queue:** Importance matters more than the arrival time.

---

# Analogy for Understanding:

Think of a **Queue** like a **one-way tunnel**. Cars enter from the back and drive through to exit at the front. No car can jump the line, and the first car to enter the tunnel is guaranteed to be the first one to come out the other side. This is the heart of "First-In, First-Out"!

---
# Lecture Notes

![[DSA - Lecture 03.pdf]]

---
# Code Examples

## 📝 PSEUDOCODE FOR ALL OPERATIONS

### 1. ENQUEUE (Insertion)

```pseudo
PROCEDURE ENQUEUE(QUEUE, FRONT, REAR, MAX, ITEM)
1. [Check for overflow]
   IF REAR = MAX-1 THEN
      PRINT "Queue Overflow"
      RETURN
   END IF

2. [If queue is empty, set FRONT to 0]
   IF FRONT = -1 THEN
      SET FRONT = 0
   END IF

3. [Increment REAR]
   SET REAR = REAR + 1

4. [Insert item]
   SET QUEUE[REAR] = ITEM

5. [Success]
   PRINT "Element enqueued"
   RETURN
END PROCEDURE
```

### 2. DEQUEUE (Deletion)

```pseudo
PROCEDURE DEQUEUE(QUEUE, FRONT, REAR)
1. [Check for underflow]
   IF FRONT = -1 OR FRONT > REAR THEN
      PRINT "Queue Underflow"
      RETURN -1
   END IF

2. [Get front element]
   SET ITEM = QUEUE[FRONT]

3. [Increment FRONT]
   SET FRONT = FRONT + 1

4. [If queue becomes empty, reset]
   IF FRONT > REAR THEN
      SET FRONT = -1
      SET REAR = -1
   END IF

5. [Return dequeued element]
   RETURN ITEM
END PROCEDURE
```