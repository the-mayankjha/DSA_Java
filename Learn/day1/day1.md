# 🚀 Day 1 — DSA From Zero

Today we're **not trying to solve 20 questions**. We're building the mental foundation that everything else will depend on.

Your Day 1 has two tracks:

**Main DSA:** Arrays + Complexity
**Problem-Solving:** Recursion → DP intuition

By the end of today, you should be able to:

* Explain what DSA actually is
* Understand Big-O
* Analyze simple Java code
* Work comfortably with arrays
* Recognize basic array problem patterns
* Understand recursion conceptually
* Understand *why* DP exists
* Solve your first set of problems independently

---

# 🕘 9:00–11:00 — DSA Foundations + Big-O

## 1. What is DSA?

**Data Structure** = How we organize/store data.

Examples:

```text
Array
Linked List
Stack
Queue
HashMap
HashSet
Tree
Heap
Graph
```

**Algorithm** = A sequence of steps used to solve a problem.

Example:

> Find the largest number in an array.

Data structure:

```java
int[] arr
```

Algorithm:

```text
1. Start with first element as maximum
2. Visit every element
3. If current > maximum
       update maximum
4. Return maximum
```

So:

> **DS = how data is stored**
> **Algorithm = how we process it**

---

# 2. Why Companies Care About Complexity

Suppose:

```java
int[] arr = {4, 7, 2, 9, 1};
```

Finding `9` is easy.

But imagine:

```text
n = 10
```

versus:

```text
n = 10,000,000
```

An algorithm that works beautifully for 10 elements may become unusable for 10 million.

That's why interviews ask:

> **What's your time complexity?**

---

# 3. Big-O

Big-O describes how an algorithm's resource usage grows as input size `n` increases.

The most important ones for you:

<p align="center">
<img src="./time.png"></img>
</p>


```text
O(1)       Constant
O(log n)   Logarithmic
O(n)       Linear
O(n log n)
O(n²)      Quadratic
O(2ⁿ)      Exponential
O(n!)      Factorial
```

For placement preparation, these should become second nature.

---

# 4. O(1) — Constant

```java
int x = arr[0];
```

No matter whether the array has:

```text
10 elements
1,000 elements
10 million elements
```

you're doing one direct access.

Therefore:

**O(1)**

---

# 5. O(n) — Linear

```java
for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);
}
```

If:

```text
n = 10
```

→ ~10 operations.

If:

```text
n = 1,000
```

→ ~1,000 operations.

Therefore:

**O(n)**

---

# 6. O(n²) — Quadratic

```java
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        System.out.println(arr[i] + arr[j]);
    }
}
```

For every `i`, we go through every `j`.

Approximately:

```text
n × n
= n²
```

Therefore:

**O(n²)**

---

# 7. Nested Loops Don't Always Mean O(n²)

Important!

Look at:

```java
for (int i = 0; i < n; i++) {
    for (int j = 0; j < 10; j++) {
        System.out.println(j);
    }
}
```

Inner loop always runs 10 times.

Therefore:

```text
10n
```

Drop constants:

**O(n)**

---

# 🧪 Your First Complexity Test

Don't look for the answer online.

### Q1

What's the time complexity?

```java
for (int i = 0; i < n; i++) {
    System.out.println(i);
}
```

### Q2

```java
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        System.out.println(i + j);
    }
}
```

### Q3

```java
System.out.println(arr[5]);
```

### Q4

```java
for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);
}

for (int i = 0; i < n; i++) {
    System.out.println(arr[i]);
}
```

### Q5 — Think carefully

```java
for (int i = 0; i < n; i++) {
    for (int j = 0; j < 100; j++) {
        System.out.println(i + j);
    }
}
```

Send me your answers **before continuing**.

I'll check them and then we'll move into arrays.

---

# 🧩 9:00–11:00 Continued — Arrays

Once you've got Big-O, arrays are our first major data structure.

Think of an array as:

```text
Index:   0   1   2   3   4
         ↓   ↓   ↓   ↓   ↓
Array:  [10, 20, 30, 40, 50]
```

Each element has an index.

```java
int[] arr = {10, 20, 30, 40, 50};
```

Access:

```java
arr[0]  // 10
arr[3]  // 40
```

Array indexing is:

**O(1)**

---

# 8. Array Traversal

The most fundamental array pattern:

```java
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

Complexity:

**Time: O(n)**
**Extra Space: O(1)**

---

# 9. Find Maximum

Start with:

```java
int max = arr[0];
```

Then inspect every element.

```java
for (int i = 1; i < arr.length; i++) {
    if (arr[i] > max) {
        max = arr[i];
    }
}
```

The important concept isn't the code.

It's:

> **Maintain a variable representing the best answer seen so far.**

This pattern appears everywhere.

---

# 10. Find Minimum

Same idea:

```java
int min = arr[0];

for (int i = 1; i < arr.length; i++) {
    if (arr[i] < min) {
        min = arr[i];
    }
}
```

---

# 11. Array Pattern #1 — Traversal

Whenever a problem says:

> "Go through every element and calculate something..."

Your first thought should be:

```text
Traversal
   ↓
O(n)
```

Examples:

* Find maximum
* Find minimum
* Calculate sum
* Count elements
* Count positives
* Find first occurrence

---

# 🕚 11:20–1:20 — Your First Problems

Now **you solve**.

Don't immediately ask for solutions.

## Problem 1 — Maximum

Given:

```text
[3, 7, 2, 9, 4]
```

Return the maximum.

Expected:

```text
9
```

Write the Java method.

---

## Problem 2 — Minimum

Given:

```text
[8, 3, 6, 1, 5]
```

Return:

```text
1
```

---

## Problem 3 — Sum

Given:

```text
[2, 4, 6, 8]
```

Return:

```text
20
```

---

## Problem 4 — Count Even Numbers

Given:

```text
[1, 4, 7, 8, 10, 13]
```

Return:

```text
3
```

---

## Problem 5 — Linear Search

Write:

```java
boolean contains(int[] arr, int target)
```

Example:

```text
arr = [4, 7, 1, 9, 3]
target = 9
```

Output:

```text
true
```

---

# 🧠 Then Problem 6 — Slightly More Interesting

Given:

```text
[5, 1, 8, 3, 9, 2]
```

Find the **second largest element**.

Expected:

```text
8
```

### Important:

Don't immediately sort the array.

Try to solve it in:

**O(n)** time.

This is your first opportunity to think beyond brute force.

---

# 🌆 5:00–6:00 — Problem-Solving Method

Now we start our separate **algorithmic problem-solving track**.

Today:

# Recursion

You don't need to master DP today.

We are building the foundation.

---

## What is Recursion?

Recursion means:

> A function calls itself to solve a smaller version of the same problem.

Example:

```java
void countdown(int n) {
    if (n == 0) {
        return;
    }

    System.out.println(n);
    countdown(n - 1);
}
```

Calling:

```java
countdown(3);
```

Conceptually:

```text
countdown(3)
    ↓
countdown(2)
    ↓
countdown(1)
    ↓
countdown(0)
    ↓
STOP
```

---

# 12. Every Recursion Problem Has Two Parts

### Base Case

When do we stop?

```java
if (n == 0) return;
```

### Recursive Case

How do we make the problem smaller?

```java
countdown(n - 1);
```

Think:

> **Base Case + Smaller Problem**

---

# 13. Your Recursion Exercise

Write:

```java
void printNumbers(int n)
```

that prints:

```text
1
2
3
...
n
```

For:

```text
n = 5
```

Output:

```text
1
2
3
4
5
```

Try solving it recursively.

---

# 14. Recursion → DP Connection

This is extremely important for your placement strategy.

Suppose we calculate Fibonacci:

```text
F(n) = F(n-1) + F(n-2)
```

A naive recursive solution repeatedly calculates the same values.

Conceptually:

```text
              F(5)
            /      \
          F(4)     F(3)
         /   \     /   \
       F(3) F(2) F(2) F(1)
       ...
```

Notice:

```text
F(3)
F(2)
```

get calculated repeatedly.

That's where **Dynamic Programming** comes in.

DP essentially asks:

> **"Have I already solved this smaller problem? Why solve it again?"**

So:

```text
Recursion
    ↓
Repeated subproblems
    ↓
Remember previous answers
    ↓
Dynamic Programming
```

This is the intuition we will build over the next 45 days.

---

# 🌙 6:00–7:00 — Day 1 Revision

Don't solve new problems here.

Review:

### Big-O

You should know:

```text
O(1)
O(log n)
O(n)
O(n log n)
O(n²)
O(2ⁿ)
```

### Arrays

You should know:

```text
Traversal
Maximum
Minimum
Sum
Search
```

### Recursion

You should understand:

```text
Base Case
     +
Recursive Case
     ↓
Smaller Problem
```

### DP intuition

Remember:

> **DP = solving smaller problems and reusing their answers when subproblems repeat.**

---

# 📝 Day 1 Completion Checklist

Before marking Day 1 complete:

### Complexity

* [ ] I understand Big-O.
* [ ] I can analyze simple loops.
* [ ] I understand why constants are ignored.
* [ ] I can distinguish O(n) and O(n²).

### Arrays

* [ ] I can traverse an array.
* [ ] I can find max/min.
* [ ] I can calculate a sum.
* [ ] I can search.
* [ ] I can solve second-largest in O(n).

### Recursion

* [ ] I understand base case.
* [ ] I understand recursive case.
* [ ] I can write a simple recursive function.
* [ ] I understand why recursion leads naturally into DP.

---

## 🎯 Day 1 Rule

**Don't rush today.**

You're building the foundation for:

```text
Arrays
  ↓
Hashing
  ↓
Two Pointers
  ↓
Sliding Window
  ↓
Trees
  ↓
Graphs
  ↓
Backtracking
  ↓
DP
```

If you understand **why** things work today rather than just copying code, the next 44 days will become much easier.

### Start by answering the 5 Big-O questions above.

I'll check your answers like a tutor, correct anything that's wrong, and then we'll move to the array problems.

