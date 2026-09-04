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
| Notation | Meaning | Use |
|---|---|---|
| **O(f(n))** | Upper bound (worst case) | Most commonly used |
| **Ω(f(n))** | Lower bound (best case) | Theoretical analysis |
| **Θ(f(n))** | Tight bound (average case) | When best = worst |

**Common growth rates (fastest → slowest):**

| Complexity | Name | Example |
|---|---|---|
| O(1) | Constant | Array access by index |
| O(log n) | Logarithmic | Binary search |
| O(n) | Linear | Single loop through array |
| O(n log n) | Linearithmic | Merge sort, quick sort (avg) |
| O(n²) | Quadratic | Nested loops |
| O(2ⁿ) | Exponential | Recursive subsets |
| O(n!) | Factorial | Permutations |

### 3. Space Complexity
- **Auxiliary space** — Extra space used by the algorithm (excluding input)
- **Total space** — Auxiliary + input space
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

| # | Problem | LeetCode # | Difficulty | Pattern | Time | Space | Status |
|---|---|---|---|---|---|---|---|
| 1 | | | | | | | ⬜ |
| 2 | | | | | | | ⬜ |
| 3 | | | | | | | ⬜ |
| 4 | | | | | | | ⬜ |
| 5 | | | | | | | ⬜ |

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

These are recommended LeetCode problems for Foundations:

1. **Running Sum of 1d Array** — [LeetCode #1480](https://leetcode.com/problems/running-sum-of-1d-array/) (Easy)
2. **Richest Customer Wealth** — [LeetCode #1672](https://leetcode.com/problems/richest-customer-wealth/) (Easy)
3. **Shuffle the Array** — [LeetCode #1470](https://leetcode.com/problems/shuffle-the-array/) (Easy)
4. **Kids With the Greatest Number of Candies** — [LeetCode #1431](https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/) (Easy)
5. **Number of Good Pairs** — [LeetCode #1512](https://leetcode.com/problems/number-of-good-pairs/) (Easy)

> These are warm-up problems to get comfortable with Java arrays, loops, and basic logic. No tricks — just clean fundamentals.
