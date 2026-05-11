# Chapter 11: Dynamic Programming — Lab Report

## Student Information
- **Name:** Moises Aguilar
- **Date:** 05/10/2026
- **Course:** COSC 2436

## Algorithm Summary

- **How it works:**  
Dynamic programming solves complex problems by breaking them into smaller overlapping 
subproblems and storing previously computed results. In this lab, the knapsack algorithm 
builds a table that tracks the best combination of items for every possible weight limit. 
By reusing earlier results, the algorithm avoids redundant calculations and efficiently 
finds the optimal solution.

- **Time complexity:**  
O(n × W), where `n` is the number of items and `W` is the knapsack capacity.

- **When to use it:**  
Dynamic programming is useful for optimization problems with overlapping subproblems and 
optimal substructure, such as the Knapsack Problem, shortest paths, sequence alignment, 
Fibonacci numbers, and scheduling problems.

## Test Results

| Input | Result | Notes |
|------|------|------|
| Capacity = 6 | GUITAR, iPHONE, GOLD BAR, LAPTOP | Highest total value |
| Total Weight | 6 | Did not exceed capacity |
| Total Value | $35,500 | Optimal solution found |

### Sample Program Output

```
Capacity 6:
Selected Items:
- GUITAR
- LAPTOP
- iPHONE
- GOLD BAR

Total Value: $35500
```

## Reflection Questions

### 1. Why is dynamic programming more efficient than brute force for the knapsack problem?

Brute force checks every possible combination of items, which becomes extremely slow as 
the number of items increases. Dynamic programming stores solutions to smaller subproblems 
and reuses them, greatly reducing repeated work.

### 2. What is the difference between greedy algorithms and dynamic programming?

Greedy algorithms make the best immediate choice at each step without reconsidering previous 
decisions. Dynamic programming evaluates many combinations systematically and guarantees an 
optimal solution when the problem has optimal substructure.

### 3. Why does the algorithm use a 2D grid?

The 2D grid stores the best solution for every combination of item count and weight capacity. 
Each row represents considering more items, while each column represents a possible weight limit.

## Challenges Encountered

One challenge was understanding how the dynamic programming table stored partial solutions for 
each capacity value. Another difficulty was tracing how included and excluded item combinations were 
compared to determine the highest-value solution. This was resolved by carefully stepping through 
the algorithm row by row and examining how values were propagated through the grid.