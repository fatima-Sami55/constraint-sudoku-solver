# Sudoku CSP Solver Report

## Overview
This project implements a Sudoku solver using a **Constraint Satisfaction Problem (CSP)** approach.  
The following techniques were used:

- Backtracking Search  
- Forward Checking  
- AC-3 Algorithm (Arc Consistency)

Performance is evaluated using:
- Number of **BACKTRACK calls**
- Number of **BACKTRACK failures**

---

## Results

| Board       | Backtrack Calls | Failures |
|------------|---------------|----------|
| Easy       | 1             | 0        |
| Medium     | 2             | 0        |
| Hard       | 13            | 8        |
| Very Hard  | 53            | 40       |

---
> *Note: Values may vary depending on implementation.*

---

## Analysis & Comments

### Easy Board
The easy board required very few backtracking calls and failures.  
Most variables were already highly constrained, allowing **AC-3 and forward checking** to eliminate invalid values early.  
Thus, the solver reached the solution with minimal search effort.

---

### Medium Board
The medium board showed a moderate increase in both backtracking calls and failures.  
Although constraint propagation still helped reduce domains, the solver needed more trial-and-error.  
This reflects a **larger search space** compared to the easy board.

---

### Hard Board
The hard board required significantly more backtracking.  
Initial constraints were weaker, so AC-3 was less effective in pruning domains.  
As a result, the solver explored more possibilities, leading to a higher number of failures.

---

### Very Hard Board
The very hard board had the highest number of backtracking calls and failures.  
Constraint propagation alone was not sufficient, and the solver relied heavily on backtracking.  
This indicates a **very large and complex search space**, where many attempted assignments led to dead ends.

---

## Overall Observation

As puzzle difficulty increases:
- Constraint propagation becomes less effective  
- The search space grows significantly  
- Backtracking becomes the dominant factor  

**Conclusion:**  
Easy puzzles are mostly solved through constraint reasoning, while very hard puzzles require extensive search.

---
