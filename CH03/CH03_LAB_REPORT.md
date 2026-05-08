# Lab 3: Recursion

## Student Information
- **Name:** Moises Aguilar
- **Date:** 05/08/2026

## Recursion Concepts

### Two Parts of Every Recursive Function
1. **Base Case:** The condition that stops the recursive function from calling itself again. It provides a direct answer without further recursion.
2. **Recursive Case:** The part of the function where the function calls itself with a smaller or simpler version of the problem.

### The Call Stack
The call stack keeps track of active function calls in a program. Each time a 
recursive function is called, a new stack frame is added to the top of the 
stack. When a function finishes, its frame is removed from the stack.

Example using `fact(3)`:

```python
fact(3)
-> 3 * fact(2)
-> 3 * (2 * fact(1))
-> 3 * (2 * 1)
-> 6
```

Stack order:
1. `fact(3)` added
2. `fact(2)` added
3. `fact(1)` added
4. `fact(1)` returns 1 and is removed
5. `fact(2)` returns 2 and is removed
6. `fact(3)` returns 6 and is removed

## Function Analysis

| Function | Base Case | Recursive Case | Time Complexity |
|----------|-----------|----------------|-----------------|
| countdown | i <= 0 | countdown(i-1) | O(n) |
| fact | x <= 1 | x * fact(x-1) | O(n) |
| recursive_sum | empty list | first + sum(rest) | O(n) |
| recursive_count | empty list | 1 + count(rest) | O(n) |
| recursive_max | single item | max(first, max(rest)) | O(n) |

## Reflection Questions

1. What happens if you forget the base case?
If you forget the base case, the recursive function will continue calling itself forever 
until the program runs out of memory or reaches the maximum recursion depth, causing 
a stack overflow or recursion depth error.

2. Why is the naive Fibonacci implementation inefficient?
The naive Fibonacci implementation is inefficient because it repeatedly recalculates the 
same values many times. This creates an exponential number of function calls, resulting 
in a time complexity of approximately O(2^n).

3. Draw the call stack for fact(4).
```
fact(4)
L__ 4 * fact(3)
    L__ 3 * fact(2)
        L__ 2 * fact(1)
            L__ 1

Returns:
fact(1) = 1
fact(2) = 2 * 1 = 2
fact(3) = 3 * 2 = 6
fact(4) = 4 * 6 = 24
```