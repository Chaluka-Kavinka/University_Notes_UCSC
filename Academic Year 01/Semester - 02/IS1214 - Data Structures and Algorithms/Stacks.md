A **Stack** is a linear data structure that follows a very specific rule for managing data: elements can only be inserted or deleted from one end, known as the **TOP**.

# 1. The LIFO Principle

The defining characteristic of a stack is the **LIFO (Last-In, First-Out)** principle. This means the last element you put into the stack is the very first one you must take out.

- **Fancy Example:** Think of the **"Undo" button** in a text editor or the **"Back" button** in your web browser. Every action you take or page you visit is "pushed" onto a stack. When you want to go back, the computer "pops" the most recent item off the top to return you to your previous state.

# 2. Basic Stack Operations

To interact with a stack, we use a few fundamental operations:

- **Push:** Adds a new element to the top. Before doing this, the system checks for **Overflow**—a condition where the stack is already full and cannot accept more data.

- **Pop:** Removes the topmost element. Before popping, the system checks for **Underflow**—a condition where you try to remove an item from an empty stack.

- **Peek (or Top):** Lets you look at the value of the top element without actually removing it.

- **isEmpty / isFull:** Logical checks to see if the stack is completely empty or at maximum capacity.

# 3. Implementation Methods

There are two primary ways to build a stack in C:

- **Static Implementation (Arrays):** The stack has a **fixed size**. It is simple but can be inefficient if you don't use all the allocated space.

- **Dynamic Implementation (Linked Lists):** The stack **grows in size** as needed. This is more memory-efficient because it only uses space when data is actually added.

# 4. Why are Stacks Important?

Beyond simple data storage, stacks are essential for:

- **Mathematical Evaluations:** Converting expressions (like Infix to Post-fix) and solving them.

- **Syntax Checking:** Ensuring that parentheses `()` and braces `{}` in code are properly balanced and matched.

- **Recursion:** Stacks are used by the computer to manage function calls and solve complex puzzles like the **Towers of Hanoi**.

---

# Short Note for Memory:

- **TOP:** The only "door" into or out of the stack.

- **LIFO:** **L**ast **I**n, **F**irst **O**ut.

- **Push:** Add to Top.

- **Pop:** Remove from Top.

- **Overflow:** Too much data (Stack Full).

- **Underflow:** No data to give (Stack Empty).

---
# Analogy for Understanding:

Think of a **spring-loaded plate dispenser** in a cafeteria. When a dishwasher adds a plate, they "Push" it onto the top, and the whole pile moves down. When you need a plate, you "Pop" the one off the top. You can’t grab a plate from the middle or the bottom without removing everything above it first—that is the essence of a stack!

---
# Lecture Notes

![[DSA - Lecture 02.pdf]]

---
# Code Examples

## 📝 PSEUDO-CODE for Stack Push

```pseudo
PSEUDOCODE: PUSH OPERATION

PROCEDURE PUSH(STACK, TOP, MAX, ITEM)
1. [Check for overflow]
   IF TOP = MAX-1 THEN
	   PRINT "Stack Overflow"
      RETURN
   END IF

2. [Increment TOP]
   SET TOP = TOP + 1

3. [Insert item]
   SET STACK[TOP] = ITEM

4. [Success]
   PRINT "Element pushed successfully"
   RETURN
END PROCEDURE
```

# 💻 COMPLETE C CODE for Push Stack

```C
#include <stdio.h>
#define MAX 5  // Maximum size of stack

int stack[MAX];
int top = -1;  // Stack is empty

// Push function
void push(int item) {
    // Step 1: Check for overflow
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d\n", item);
        return;
    }
    
    // Step 2: Increment TOP
    top++;
    
    // Step 3: Insert item
    stack[top] = item;
    
    // Step 4: Success
    printf("✓ Pushed %d onto stack\n", item);
}

// Display stack
void display() {
    if (top == -1) {
        printf("Stack is empty!\n");
        return;
    }
    
    printf("Stack (TOP → BOTTOM): ");
    for (int i = top; i >= 0; i--) {
        printf("%d ", stack[i]);
        if (i == top) printf("← TOP");
        printf("\n");
    }
}

// Main function
int main() {
    printf("=== Stack Push Operation ===\n\n");
    
    // Push some elements
    push(10);
    push(20);
    push(30);
    push(40);
    push(50);  // This fills the stack (MAX=5)
    
    printf("\nCurrent stack:\n");
    display();
    
    // Try to overflow
    printf("\nTrying to push 60 (should overflow):\n");
    push(60);
    
    return 0;
}
```

## 📝 PSEUDO-CODE for Stack Pop

```pseudo
PSEUDOCODE: POP OPERATION

PROCEDURE POP(STACK, TOP)
1. [Check for underflow]
   IF TOP = -1 THEN
      PRINT "Stack Underflow"
      RETURN -1  // Error indicator
   END IF

2. [Get the top element]
   SET ITEM = STACK[TOP]

3. [Decrement TOP]
   SET TOP = TOP - 1

4. [Return the popped element]
   RETURN ITEM
END PROCEDURE
```
## 💻 COMPLETE C CODE with BOTH Push & Pop

```C
#include <stdio.h>
#define MAX 5

int stack[MAX];
int top = -1;

// Push function (from earlier)
void push(int item) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d\n", item);
        return;
    }
    top++;
    stack[top] = item;
    printf("✓ Pushed: %d\n", item);
}

// Pop function
int pop() {
    // Step 1: Check for underflow
    if (top == -1) {
        printf("Stack Underflow! Cannot pop\n");
        return -1;  // Error value
    }
    
    // Step 2: Get the top element
    int item = stack[top];
    
    // Step 3: Decrement TOP
    top--;
    
    // Step 4: Return popped element
    printf("✓ Popped: %d\n", item);
    return item;
}

// Display stack
void display() {
    if (top == -1) {
        printf("Stack: [EMPTY]\n");
        return;
    }
    
    printf("Stack (TOP → BOTTOM): \n");
    for (int i = top; i >= 0; i--) {
        printf("[%d]", stack[i]);
        if (i == top) printf(" ← TOP");
        printf("\n");
    }
    printf("\n");
}

// Main function demonstrating push/pop
int main() {
    printf("=== Stack Push & Pop Operations ===\n\n");
    
    // Push elements
    printf("Pushing elements:\n");
    push(10);
    push(20);
    push(30);
    push(40);
    push(50);
    
    printf("\nCurrent stack:\n");
    display();
    
    // Try to overflow
    printf("Trying to push 60 (overflow test):\n");
    push(60);
    
    // Pop elements
    printf("\nPopping elements:\n");
    pop();
    pop();
    
    printf("\nStack after 2 pops:\n");
    display();
    
    // Pop more
    printf("Popping remaining elements:\n");
    pop();
    pop();
    pop();
    
    printf("\nFinal stack:\n");
    display();
    
    // Try underflow
    printf("Trying to pop from empty stack:\n");
    pop();
    
    return 0;
}
```