# 🔙 Backtracking

Backtracking is a powerful algorithmic technique used to solve constraint satisfaction problems, combinatorial problems, and optimization problems. It systematically explores all possible solutions and abandons paths that cannot yield valid results.

## 📌 Table of Contents
- [Introduction](#introduction)
- [How Backtracking Works](#how-backtracking-works)
- [General Backtracking Template](#general-backtracking-template)
- [Types of Problems Solved by Backtracking](#types-of-problems-solved-by-backtracking)
- [Example Problems](#example-problems)
- [Complexity Analysis](#complexity-analysis)
- [Advantages and Disadvantages](#advantages-and-disadvantages)
- [Resources for Learning](#resources-for-learning)
- [Practice Problems](#practice-problems)
- [Contributing](#contributing)
- [License](#license)

---

## 🚀 Introduction
Backtracking is a **brute-force** search technique that incrementally builds a solution while ensuring that constraints are met. If a certain path is invalid, it **backtracks** by undoing the last decision and explores another path.

It is commonly used in:
- **Combinatorial Generation** (Permutations, Combinations, Subsets)
- **Constraint Satisfaction Problems** (Sudoku, N-Queens)
- **Graph Problems** (Hamiltonian Cycle, Coloring)
- **Optimization Problems** (Traveling Salesman Problem)

---

## 🔄 How Backtracking Works
1. **Choose** – Select a candidate for the solution.
2. **Explore** – Proceed with the choice and recursively solve the problem.
3. **Backtrack** – If the current choice is invalid, undo the last step and try another option.

---

## 📝 General Backtracking Template
```
function BACKTRACK(path, options):
    if is_solution(path):
        process_solution(path)
        return
    
    for each option in options:
        if is_valid(option, path):
            path.append(option)  // Make a choice
            BACKTRACK(path, new_options)  // Explore further
            path.pop()  // Undo the choice (backtrack)

```