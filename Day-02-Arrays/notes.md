# Day 02 — Arrays

📅 **Date:** September 5, 2026  
📂 **Topic:** Array Traversal, In-Place Modification, Kadane's Algorithm, Prefix & Suffix Thinking  
🎯 **Target:** 4 problems  

---

## 📖 Concepts Covered

### 1. Array Traversal & Linear Scanning

Traversal is the fundamental operation of visiting each element in an array once. The key to mastering array traversal is knowing when to scan forward, backward, or from both ends.

- **Forward Scan ($0 \to n-1$):** Standard accumulation, minimum/maximum search, or linear search.
- **Backward Scan ($n-1 \to 0$):** Useful when the decision at index $i$ depends on future elements (e.g., Leaders in an Array, Next Greater Element).
- **Two-Pointer Traversal:** Pointers moving toward each other from opposite ends (e.g., reversal, pair sum) or fast/slow pointers moving in the same direction.

```java
// Boundary check precaution
if (arr == null || arr.length == 0) {
    return;
}

// Forward traversal
for (int i = 0; i < arr.length; i++) {
    // Process arr[i]
}

// Backward traversal
for (int i = arr.length - 1; i >= 0; i--) {
    // Process arr[i]
}
```

---

### 2. In-Place Array Modification

An algorithm is considered **in-place** if it transforms input using $O(1)$ auxiliary space (RAM memory), modifying the array directly without allocating a new array of size $n$.

#### The Read/Write Pointer Pattern
A common technique is using two pointers:
- **`read` pointer (`i`):** Scans every element of the array.
- **`write` pointer (`k`):** Tracks the position where the next valid element should be placed.

#### Example: Move All Zeroes to End
Move all zeros to the end of the array while maintaining the relative order of non-zero elements in $O(n)$ time and $O(1)$ auxiliary space.

```java
public static void moveZeroes(int[] nums) {
    int writeIndex = 0;
    
    // Shift all non-zero elements to the front
    for (int i = 0; i < nums.length; i++) {
        if (nums[i] != 0) {
            nums[writeIndex++] = nums[i];
        }
    }
    
    // Fill remaining positions with zeroes
    while (writeIndex < nums.length) {
        nums[writeIndex++] = 0;
    }
}
```

---

### 3. Kadane's Algorithm (Maximum Subarray Sum)

#### Problem Statement
Given an integer array `arr[]`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

#### Why Brute Force Fails
- A naive check examines all $\frac{n(n+1)}{2}$ contiguous subarrays: $O(n^2)$ or $O(n^3)$ time, causing TLE (Time Limit Exceeded) for $n \ge 10^5$.

#### Kadane's Intuition (Greedy / Dynamic Programming)
At every index $i$, we ask a single question:
> *"Is it better to extend the existing subarray sum, or start fresh from the current element?"*

If `currentSum` becomes negative, extending it to the next element will only hurt the next sum. Therefore, we discard the previous sum and start fresh from `arr[i]`.

#### State Transition Equations
$$
\text{currentSum} = \max(\text{arr}[i], \text{currentSum} + \text{arr}[i])
$$
$$
\text{maxSum} = \max(\text{maxSum}, \text{currentSum})
$$

#### Dry Run: `arr = [-2, 1, -3, 4, -1, 2, 1, -5, 4]`

| Index `i` | `arr[i]` | `currentSum = max(arr[i], currentSum + arr[i])` | `maxSum = max(maxSum, currentSum)` |
|:---------:|:--------:|:-----------------------------------------------:|:----------------------------------:|
| 0         | -2       | -2                                              | -2                                 |
| 1         | 1        | $\max(1, -2 + 1) = 1$                           | $\max(-2, 1) = 1$                  |
| 2         | -3       | $\max(-3, 1 - 3) = -2$                          | $\max(1, -2) = 1$                  |
| 3         | 4        | $\max(4, -2 + 4) = 4$                           | $\max(1, 4) = 4$                   |
| 4         | -1       | $\max(-1, 4 - 1) = 3$                           | $\max(4, 3) = 4$                   |
| 5         | 2        | $\max(2, 3 + 2) = 5$                            | $\max(4, 5) = 5$                   |
| 6         | 1        | $\max(1, 5 + 1) = 6$                            | $\max(5, 6) = 6$                   |
| 7         | -5       | $\max(-5, 6 - 5) = 1$                           | $\max(6, 1) = 6$                   |
| 8         | 4        | $\max(4, 1 + 4) = 5$                            | $\max(6, 5) = 6$                   |

**Maximum Subarray Sum = 6** (subarray `[4, -1, 2, 1]`).

#### Java Implementation (Handles all negative numbers safely)
```java
public class KadanesAlgorithm {
    public static int maxSubarraySum(int[] arr) {
        // Critical: initialize with first element, NOT 0 (handles all-negative arrays)
        int currentSum = arr[0];
        int maxSum = arr[0];

        for (int i = 1; i < arr.length; i++) {
            currentSum = Math.max(arr[i], currentSum + arr[i]);
            maxSum = Math.max(maxSum, currentSum);
        }

        return maxSum;
    }
}
```
- **Time Complexity:** $O(n)$ — Single pass through the array
- **Space Complexity:** $O(1)$ — Only two scalar variables used

---

### 4. Prefix & Suffix Thinking

#### Prefix Sum Array
A prefix sum array stores cumulative sums from index $0$ to $i$:
$$
\text{prefix}[i] = \sum_{j=0}^{i} \text{arr}[j]
$$
$$
\text{prefix}[i] = \text{prefix}[i-1] + \text{arr}[i] \quad (i \ge 1)
$$

#### Range Sum Query in $O(1)$
To calculate the sum of elements between indices $L$ and $R$ inclusive:
$$
\text{Sum}(L, R) = \begin{cases} \text{prefix}[R] & \text{if } L = 0 \\ \text{prefix}[R] - \text{prefix}[L - 1] & \text{if } L > 0 \end{cases}
$$

```java
// Precomputing prefix sum: O(n)
int[] prefix = new int[arr.length];
prefix[0] = arr[0];
for (int i = 1; i < arr.length; i++) {
    prefix[i] = prefix[i - 1] + arr[i];
}

// Query sum in range [L, R]: O(1)
int rangeSum = (L == 0) ? prefix[R] : prefix[R] - prefix[L - 1];
```

#### Suffix / Right-to-Left Thinking
Accumulating values or extrema from right to left avoids nested loops.

**Example: Leaders in an Array**
An element is a "leader" if it is greater than all elements to its right.
Scanning backwards ($n-1 \to 0$) and maintaining `maxFromRight` solves it in $O(n)$ time and $O(1)$ auxiliary space:

```java
public static List<Integer> findLeaders(int[] arr) {
    List<Integer> leaders = new ArrayList<>();
    int n = arr.length;
    int maxFromRight = arr[n - 1];
    leaders.add(maxFromRight);

    for (int i = n - 2; i >= 0; i--) {
        if (arr[i] >= maxFromRight) {
            maxFromRight = arr[i];
            leaders.add(maxFromRight);
        }
    }
    Collections.reverse(leaders);
    return leaders;
}
```

---

## ✅ Problems Solved

| # | Problem | Platform | Difficulty | Pattern | Time | Space | Status |
|---|---------|----------|------------|---------|------|-------|--------|
| 1 | Kadane's Algorithm (Max Subarray) | GFG / LeetCode | Medium | Kadane's Algorithm | O(n) | O(1) | ⬜ |
| 2 | Move All Zeroes to End | GFG / LeetCode | Easy | In-Place Two Pointers | O(n) | O(1) | ⬜ |
| 3 | Equilibrium Point / Running Sum | GFG / LeetCode | Easy | Prefix Sum | O(n) | O(1) | ⬜ |
| 4 | Leaders in an Array | GFG | Easy | Suffix Traversal | O(n) | O(1) | ⬜ |

> Fill in as you solve each problem. Change ⬜ to ✅ when done.

---

## 🧠 Reflection

- **What clicked today:**
  - *(write here after studying)*

- **What's still fuzzy:**
  - *(write here — be honest, this is for you)*

- **Plan for tomorrow (Day 3 — Hashing):**
  - Hash tables, Java `HashMap` and `HashSet`
  - Collision handling (chaining vs open addressing), load factor
  - 4–5 problems

---

## 💡 Suggested Day 2 Problems

### GeeksforGeeks (Free)

| # | Problem | Link | Difficulty | Pattern |
|---|---------|------|------------|---------|
| 1 | Kadane's Algorithm | [GFG](https://www.geeksforgeeks.org/problems/kadanes-algorithm-1587115620/1) | Medium | Kadane's / DP |
| 2 | Move All Zeroes to End | [GFG](https://www.geeksforgeeks.org/problems/move-all-zeroes-to-end-of-array0751/1) | Easy | In-Place Modification |
| 3 | Equilibrium Point | [GFG](https://www.geeksforgeeks.org/problems/equilibrium-point-1587115620/1) | Easy | Prefix Sum |
| 4 | Leaders in an Array | [GFG](https://www.geeksforgeeks.org/problems/leaders-in-an-array-1587115620/1) | Easy | Right-to-Left Traversal |

### HackerRank & LeetCode (Free)

| # | Problem | Link | Difficulty | Pattern |
|---|---------|------|------------|---------|
| 1 | Maximum Subarray | [LeetCode](https://leetcode.com/problems/maximum-subarray/) | Medium | Kadane's Algorithm |
| 2 | Move Zeroes | [LeetCode](https://leetcode.com/problems/move-zeroes/) | Easy | Two Pointers |
| 3 | Running Sum of 1d Array | [LeetCode](https://leetcode.com/problems/running-sum-of-1d-array/) | Easy | Prefix Sum |
| 4 | Left and Right Sum Differences | [LeetCode](https://leetcode.com/problems/left-and-right-sum-differences/) | Easy | Prefix & Suffix Sum |

> Focus on identifying whether a problem requires: (1) Single pass with state, (2) In-place overwriting, or (3) Cumulative precomputation.
