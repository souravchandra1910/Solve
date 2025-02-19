# 🔙 Backtracking

Backtracking is a powerful algorithmic technique used to solve constraint satisfaction problems, combinatorial problems, and optimization problems. It systematically explores all possible solutions and abandons paths that cannot yield valid results.

## 📌 Table of Contents
- [Introduction](#introduction)
- [How Backtracking Works](#how-backtracking-works)
- [General Backtracking Template](#general-backtracking-template)
- [Types of Problems Solved by Backtracking](#types-of-problems-solved-by-backtracking)
- [Practice Problems](#practice-problems)
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
function backtrack(int index,int n,List ds,int []arr):
    // base case
    if(index==n){
        ans.add(ds);
        return;
    }
    //pick an element 
    ds.add(arr[index])
    solve(index+1,n,ds,arr);

    //don't pick the element
    ds.removeLast();
    solve(index+1,n,ds,arr);
```

