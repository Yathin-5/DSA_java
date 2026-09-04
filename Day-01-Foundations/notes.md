# Day 01 — Foundations

📅 **Date:** September 4, 2026
📂 **Topic:** Data Structures vs Algorithms, Big-O/Ω/Θ, Space Complexity, Java Arrays Basics
🎯 **Target:** 4–5 problems

---

## 📖 Concepts Covered

### 1. Data Structures vs Algorithms

- **Data Structure** — A way to organize and store data (arrays, linked lists, trees, etc.)
- **Algorithm** — A step-by-step procedure to solve a problem using those structures
- Together they define how efficiently a program runs

### 2. Time Complexity — Big-O, Big-Omega, Big-Theta

| Notation    | Meaning                    | Use                  |
| ----------- | -------------------------- | -------------------- |
| **O(f(n))** | Upper bound (worst case)   | Most commonly used   |
| **Ω(f(n))** | Lower bound (best case)    | Theoretical analysis |
| **Θ(f(n))** | Tight bound (average case) | When best = worst    |

Eample: for the time complexity
\*\*

Linear Search is the classic algorithm where Best, Average, and Worst cases exhibit distinct runtime behaviors and operation counts.Pythondef linear_search(arr, target):
for i in range(len(arr)):
if arr[i] == target:
return i # Found element
return -1 # Element not found

1. Best-Case Scenario: $O(1)$Scenario: The target element is located at the very first index (arr[0]).Execution: The loop runs once, finds the target immediately, and exits.Operation Count: $1$ comparison.Time Complexity: $O(1)$ (Constant time).2. Average-Case Scenario: $O(n)$Scenario: The target is randomly distributed across the array with equal probability for any position.Execution: The loop checks elements one by one until it finds the match roughly halfway through the array.Operation Count Derivation:Assuming the element is in the array with uniform probability $P(i) = \frac{1}{n}$:

   $$
   T_{\text{avg}}(n) = \sum_{i=1}^{n} \frac{1}{n} \cdot i = \frac{1}{n} \cdot \frac{n(n+1)}{2} = \frac{n + 1}{2}
   $$

   Time Complexity: Dropping constants yields $O(n)$ (Linear time).3. Worst-Case Scenario: $O(n)$Scenario: The target element is at the very last position (arr[n-1]) or is not present in the array at all.Execution: The algorithm must inspect every single element before completing.Operation Count: $n$ comparisons.Time Complexity: $O(n)$ (Linear time).Summary ComparisonCaseScenarioExact ComparisonsBig-O NotationBestTarget at index 0$1$$O(1)$AverageTarget at random index$\frac{n+1}{2}$$O(n)$WorstTarget at index n-1 or missing$n$$O(n)$

**Common growth rates (fastest → slowest):**

| Complexity | Name         | Example                      |
| ---------- | ------------ | ---------------------------- |
| O(1)       | Constant     | Array access by index        |
| O(log n)   | Logarithmic  | Binary search                |
| O(n)       | Linear       | Single loop through array    |
| O(n log n) | Linearithmic | Merge sort, quick sort (avg) |
| O(n²)      | Quadratic    | Nested loops                 |
| O(2ⁿ)      | Exponential  | Recursive subsets            |
| O(n!)      | Factorial    | Permutations                 |

### 3. Space Complexity

- **Auxiliary space** — Extra space used by the algorithm (excluding input),**Auxiliary Space** is the extra or temporary memory an algorithm uses to solve a problem, **excluding** the space taken up by the input data itself.(RAM MEMORY))
- **Total space** — Auxiliary (RAM memory)+ input space
- In-place algorithms use O(1) auxiliary space

### 4. Java Arrays Basics

```java
// Declaration and initialization
int[] arr = new int[5];           // default values: 0
int[] arr = {1, 2, 3, 4, 5};     // literal initialization

// Key properties
arr.length                        // size (not a method — no parentheses!)

// Common operations
Arrays.sort(arr);                 // O(n log n) — Dual-Pivot Quicksort
Arrays.fill(arr, 0);             // fill all elements
Arrays.copyOf(arr, newLength);   // copy with new size
```

---

## ✅ Problems Solved

| # | Problem | Platform | Difficulty | Pattern | Time | Space | Status |
|---|---------|----------|------------|---------|------|-------|--------|
| 1 |         |          |            |         |      |       | ⬜     |
| 2 |         |          |            |         |      |       | ⬜     |
| 3 |         |          |            |         |      |       | ⬜     |
| 4 |         |          |            |         |      |       | ⬜     |
| 5 |         |          |            |         |      |       | ⬜     |

> Fill in as you solve each problem. Change ⬜ to ✅ when done.

---

## 🧠 Reflection

- **What clicked today:**
  - *(write here after studying)*

- **What's still fuzzy:**
  - *(write here — be honest, this is for you)*

- **Plan for tomorrow (Day 2 — Arrays):**
  - Array traversal, in-place modification, Kadane's Algorithm
  - Prefix/suffix thinking
  - 4 problems

---

## 💡 Suggested Day 1 Problems

### GeeksforGeeks (Free)

| # | Problem | Link | Difficulty |
|---|---------|------|------------|
| 1 | Start Coding (Java Basics) | [GFG](https://www.geeksforgeeks.org/problems/start-coding-java/0) | Basic |
| 2 | Sum of Array Elements | [GFG](https://www.geeksforgeeks.org/problems/sum-of-array-elements2502/1) | Basic |
| 3 | Largest Element in Array | [GFG](https://www.geeksforgeeks.org/problems/largest-element-in-array4009/0) | Basic |
| 4 | Array Search | [GFG](https://www.geeksforgeeks.org/problems/search-an-element-in-an-array-1587115621/1) | Basic |
| 5 | Reverse an Array | [GFG](https://www.geeksforgeeks.org/problems/reverse-an-array/0) | Basic |

### HackerRank (Free)

| # | Problem | Link | Difficulty |
|---|---------|------|------------|
| 1 | Java Stdin and Stdout | [HackerRank](https://www.hackerrank.com/challenges/java-stdin-and-stdout-1/problem) | Easy |
| 2 | Java If-Else | [HackerRank](https://www.hackerrank.com/challenges/java-if-else/problem) | Easy |
| 3 | Java Loops I | [HackerRank](https://www.hackerrank.com/challenges/java-loops-i/problem) | Easy |
| 4 | Java 1D Array | [HackerRank](https://www.hackerrank.com/challenges/java-1d-array-introduction/problem) | Easy |
| 5 | Simple Array Sum | [HackerRank](https://www.hackerrank.com/challenges/simple-array-sum/problem) | Easy |

> These are warm-up problems to get comfortable with Java arrays, loops, and basic logic. No tricks — just clean fundamentals. All problems are **100% free**.
