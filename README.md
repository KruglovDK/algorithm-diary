# Algorithm Diary

[![LeetCode](https://img.shields.io/badge/LeetCode-Practice-FFA116?style=flat&logo=leetcode&logoColor=white)](https://leetcode.com)
[![Status](https://img.shields.io/badge/status-in%20progress-yellow)](https://github.com/KruglovDK/algorithm-diary)

A personal learning journal for tracking algorithm problem-solving progress. Includes solutions, failed attempts analysis, and a retry list for spaced repetition practice.

## 📚 What is this?

This repository serves as a structured system for mastering algorithms and data structures through three key components:

- **Solutions Diary** — Optimal solutions with time/space complexity analysis
- **Mistakes Diary** — Failed attempts with root cause analysis
- **Retry List** — Problems to revisit using spaced repetition

## 📁 Structure

```
algorithm-diary/
├── retry-list/
│   └── README.md              # Problems to revisit (remove when solved)
├── problems/
│   ├── array/
│   │   └── two-sum/
│   │       ├── solution.md    # Optimal solution + explanation
│   │       └── fails.md       # Failed attempts + analysis
│   ├── linked-list/
│   │   ├── reverse-list/
│   │   └── merge-lists/
│   ├── tree/
│   ├── graph/
│   ├── dynamic-programming/
│   ├── binary-search/
│   └── ...
└── README.md
```

## 📝 Solution Template

Each `solution.md` follows this structure:

```markdown
# Problem Name

[LeetCode Link](https://leetcode.com/problems/...)

## Solution

\`\`\`python
# Code here
\`\`\`

## Complexity

**Time:** `O(n)` — explanation  
**Space:** `O(n)` — explanation

## Approach

Step-by-step explanation of the solution logic.
```

## ❌ Fails Template

Each `fails.md` documents failed attempts:

```markdown
# Failed Attempts

## Attempt 1 — TLE
\`\`\`python
# Failed code
\`\`\`
**What went wrong:** Used nested loops O(n²) instead of hashmap O(n)

## Attempt 2 — Wrong Answer
\`\`\`python
# Failed code
\`\`\`
**What went wrong:** Off-by-one error in boundary check
```

## 🔄 Retry List

Problems that couldn't be solved within 30 minutes go to `retry-list/README.md`

**Spaced Repetition Schedule:**
- First retry: 1-2 days after initial attempt
- Second retry: 1-2 weeks later
- Remove from list when solved confidently

## 🏷️ Topics

- Array
- String
- Linked List
- Stack / Queue
- Tree / Binary Tree
- Graph
- Hash Table
- Binary Search
- Two Pointers
- Sliding Window
- Dynamic Programming
- Greedy
- Backtracking
- Heap / Priority Queue

## 🎯 Purpose

1. **Track progress** — See improvement over time
2. **Learn from mistakes** — Documenting failures prevents repeating them
3. **Build a personal cheatsheet** — Quick reference before interviews
4. **Spaced repetition** — Retry list ensures long-term retention

## 📄 License

This project is licensed under the MIT License.
