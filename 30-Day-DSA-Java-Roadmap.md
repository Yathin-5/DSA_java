# 30-Day DSA Challenge — Java

**Start date:** September 4, 2026
**Language:** Java
**Main practice platform:** LeetCode
**Proof of work:** GitHub
**Extra credentials:** HackerRank certifications (optional, do these on rest days)
**Target:** 100–120 quality problems (Easy 60–70 / Medium 30–45 / Hard 5–10)

> Goal for these 30 days: build a **complete DSA foundation** and enough pattern recognition to keep going independently. Not "master everything" — that comes after.

---

## 1. GitHub Setup (do this before Day 1 problem-solving)

Create a repo called `30-Days-DSA-Java` with this structure:

```
30-Days-DSA-Java/
│
├── README.md
├── progress.md
│
├── Day-01-Foundations/
├── Day-02-Arrays/
├── Day-03-Hashing/
├── ...
├── Day-30-Mock-Interview/
```

Inside each `Day-XX-Topic/` folder, keep one `.java` file per problem, e.g. `TwoSum.java`, and a `notes.md`.

**Each `notes.md` entry, per problem:**
```
Problem: Two Sum
Pattern: Hashing
Approach: HashMap for O(1) lookup
Time Complexity: O(n)
Space Complexity: O(n)
What I learned: ...
```

**End of every day**, commit:
```
git add .
git commit -m "Day 01 - Foundations: Big-O + arrays"
git push
```

**`progress.md` template** (append one block daily — this is your public reflection log):
```
## Day 01 — 2026-09-04
Topic: Foundations
Problems solved: 2/4
What clicked: ...
What's still fuzzy: ...
Tomorrow: ...
```

---

## 2. The 30 Days

### Week 1 — Foundations, Arrays, Hashing, Two Pointers

| Day | Topic (from DSA Master Tree) | Focus / Patterns | Problems |
|---|---|---|---|
| 1 | Foundations: DS vs Algorithm, Big-O/Ω/Θ, Space Complexity, Java arrays basics | Understand growth rates, not memorize | 4–5 |
| 2 | Arrays: traversal, in-place modification, Kadane's Algorithm | Prefix/suffix thinking | 4 |
| 3 | Hashing: Hash Tables, Collision Handling (chaining vs open addressing), Load Factor | "Have I seen this? How many times?" | 4–5 |
| 4 | Arrays + Hashing combined | Frequency counts, lookups, duplicates | 4 |
| 5 | Two Pointers | Sorted-array pairs, palindromes, partitioning | 4 |
| 6 | Two Pointers advanced + intro Palindrome problems (Strings) | Why pointers move, not code memorization | 4 |
| 7 | **Revision** + light Math Basics (GCD/LCM, Primes, Sieve of Eratosthenes) | 5 mixed problems, no solutions peeking | 5 |

**Week 1 target:** 25–30 problems

---

### Week 2 — Sliding Window, Binary Search, Stack/Queue, Strings

| Day | Topic | Focus / Patterns | Problems |
|---|---|---|---|
| 8 | Sliding Window basics | Fixed window, expand/shrink | 3–4 |
| 9 | Sliding Window advanced + String Pattern Matching intro (Naive → KMP overview) | "Longest/shortest substring/subarray with condition" | 4 |
| 10 | Binary Search basics | low/mid/high, avoiding infinite loops | 4 |
| 11 | Binary Search patterns | Rotated sorted arrays, peak element | 3 |
| 12 | Binary Search on Answer | "Can I do it with X?" search-space trick | 3 |
| 13 | Stack: implementation, balanced parens, Monotonic Stack, Min Stack | LIFO, next-greater-element | 4 |
| 14 | Queue + Deque + Priority Queue intro + **Revision** | FIFO, monotonic queue, BFS setup | 4–5 |

**Week 2 target:** 25–30 problems

---

### Week 3 — Linked Lists, Trees, Graphs, Recursion

| Day | Topic | Focus / Patterns | Problems |
|---|---|---|---|
| 15 | Linked Lists (singly/doubly/circular), Reverse LL, Floyd's Cycle Detection + Recursion basics | Base case, recursive case, call stack | 4–5 |
| 16 | Binary Trees: structure, Preorder/Inorder/Postorder, Level Order (BFS) | "What does this node need to know?" | 4 |
| 17 | Tree DFS patterns: height, diameter, balanced, path sum, LCA | "What should my recursive function return?" | 4 |
| 18 | Binary Search Tree: search/insert/validate, Kth smallest | Inorder = sorted order | 4 |
| 19 | Graph basics: Adjacency Matrix vs List, directed/undirected | Java `List<List<Integer>>` | 3–4 |
| 20 | BFS + DFS on graphs | Islands, flood fill, connected components, clone graph | 4 |
| 21 | Graph **Revision** + Topological Sort + Union-Find intro | Course schedule, cycle detection | 4 |

**Week 3 target:** 20–25 problems

---

### Week 4 — Backtracking, Heaps, Dynamic Programming, Mock Interview

| Day | Topic | Focus / Patterns | Problems |
|---|---|---|---|
| 22 | Backtracking basics: Subsets, Permutations | Choose → Explore → Undo | 3–4 |
| 23 | Backtracking advanced: Combination Sum, Letter Combinations, Generate Parentheses | Think in decision trees | 3 |
| 24 | Backtracking hard: N-Queens, Word Search + Trie intro | Pattern > memorized templates | 2–3 |
| 25 | Heaps: Min/Max Heap, Java `PriorityQueue`, Top-K pattern | "Largest/smallest K items efficiently" | 4 |
| 26 | Advanced Heaps (two-heap median trick) + Bit Manipulation basics (set/clear/count bits, XOR tricks) | Streaming data problems | 3–4 |
| 27 | DP basics: State, Transition, Base Case, Memoization vs Tabulation | Climbing Stairs, House Robber | 3–4 |
| 28 | 1D DP | "What is dp[i]?" — Coin Change, Decode Ways | 3–4 |
| 29 | 2D DP + Greedy Algorithms (Activity Selection, Fractional Knapsack) | Grid DP, LCS, LIS | 4–6 |
| 30 | **Mock Interview Day** — no learning, no tutorials | 2 Easy (30 min) → 2 Medium (60 min) → 5 rapid-fire pattern ID | 9 |

**Week 4 target:** 20–25 problems

For every mock-interview problem, write before coding: *pattern? brute force? optimization? time/space? edge cases?*

---

## 3. Bonus / "Month 2+" Track (from the Master Tree, deliberately deferred)

These are real gaps in most 30-day plans — don't skip them, just don't try to cram them in now:

- **Advanced Trees:** AVL Tree, Red-Black Tree, Segment Tree, Fenwick Tree
- **Advanced Strings:** Rabin-Karp, Z-Algorithm, deeper Trie use, String Hashing
- **Advanced Graphs:** Dijkstra, Bellman-Ford, Floyd-Warshall, Kruskal/Prim (MST), full Disjoint Set (Union-Find)
- **Advanced DSA:** Sparse Table, Heavy-Light Decomposition, Treap, Splay Tree, Skip List
- **Greedy deep-dive:** Huffman Coding, Job Scheduling

Suggested pacing after Day 30: **60 days → intermediate**, **90+ days → strong problem solving**, **6+ months → interview-grade DSA**.

---

## 4. Daily Routine (repeat all 30 days)

```
1 hr        → Learn the concept
1.5–2 hrs   → Solve problems (LeetCode)
30 min      → Review + notes.md + commit to GitHub
```

## 5. Progress Tracker (paste into `progress.md`, fill in as you go)

| Day | Date | Topic | Problems solved | Committed to GitHub? |
|---|---|---|---|---|
| 1 | 2026-09-04 | Foundations | | |
| 2 | 2026-09-05 | Arrays | | |
| ... | | | | |
| 30 | | Mock Interview | | |

---

### The one rule that matters most

Don't grind random problems. Always go: **Topic → Learn pattern → 3–5 problems on that pattern → Review → Commit.** That's what actually builds pattern recognition — which is the real interview skill, not the raw count.
