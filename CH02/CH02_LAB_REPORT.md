# Lab 2: Selection Sort

## Student Information
- **Name:** Moises Aguilar
- **Date:** 05/08/2026

## Algorithm Summary

### Selection Sort
- **Time Complexity:** O(n²)
- **Space Complexity:** O(1)
- **How it works:** Selection sort repeatedly finds the smallest element in the unsorted portion of the list
 					and swaps it into the correct position at the beginning. This process continues until
 					the entire list is sorted.

## Array vs Linked List Analysis

| Operation | Array | Linked List | Why? |
|-----------|-------|-------------|------|
| Read      | O(1)  | O(n)        | Arrays allow direct index access, while linked lists must traverse nodes one by one. |
| Insert    | O(n)  | O(1)        | Arrays may need to shift elements after insertion, while linked lists can insert at the head by changing pointers. |
| Delete    | O(n)  | O(1)        | Arrays must shift elements after deletion, while linked lists can remove a node by updating pointers. |

## Test Results
```
Loaded 20 cities

============================================================
PART 1: SELECTION SORT
============================================================

Sorting cities by population (smallest first)...
Selection Sort: 190 comparisons, 10 swaps

Top 5 smallest cities:
  McAllen: 142,210
  Pasadena: 151,950
  Killeen: 153,095
  Brownsville: 183,392
  McKinney: 195,308

Sorting cities by population (largest first)...
Selection Sort: 190 comparisons, 0 swaps

Top 5 largest cities:
  Houston: 2,304,580
  San Antonio: 1,547,253
  Dallas: 1,304,379
  Austin: 978,908
  Fort Worth: 918,915

----------------------------------------
Comparison with Python's built-in sort:
Python Built-in Sort: O(n log n) - Timsort

============================================================
PART 2: ARRAY VS LINKED LIST
============================================================

--- Python List (Array) Operations ---
Array access by index [10]: 'Lubbock' - O(1) - 1.19 µs
Array insert at beginning: O(n) - 1.67 µs

--- Linked List Operations ---
Created linked list with 20 cities
LinkedList insert at head: O(1) - 1.67 µs

Searching for 'Dallas' in linked list...
LinkedList Search: Found in 4 comparisons

============================================================
PART 3: BIG O SUMMARY
============================================================

    Selection Sort: O(n²)
    - For 20 cities: ~190 comparisons
    - For 1000 cities: ~500,000 comparisons
    - For 1,000,000 cities: ~500 billion comparisons!
    
    Python's Timsort: O(n log n)  
    - For 20 cities: ~86 comparisons
    - For 1000 cities: ~10,000 comparisons
    - For 1,000,000 cities: ~20 million comparisons
    
    Array vs Linked List:
    ┌───────────┬─────────┬─────────────┐
    │ Operation │  Array  │ Linked List │
    ├───────────┼─────────┼─────────────┤
    │ Read      │  O(1)   │    O(n)     │
    │ Insert    │  O(n)   │    O(1)*    │
    │ Delete    │  O(n)   │    O(1)*    │
    └───────────┴─────────┴─────────────┘
    * O(1) only at head; O(n) to find position
```

## Reflection Questions

1. Why is selection sort O(n²)?

	Selection sort is O(n^2) because it uses nested loops. That is, for every element in the array, 
	it searches through the remaining unsorted elements to find the smallest value. This results 
	in approximately n times n comparisons.

2. When would you choose a linked list over an array?

	A linked list is useful when frequent insertions and deletions are needed, especially at 
	the beginning of the list. Linked lists are also useful when the size of the data changes 
	often.

3. Why does Python use arrays (lists) as the default sequence type?

	Python uses arrays (lists) because they provide fast indexing, efficient memory usage, and 
	good overall performance for common operations. Arrays are also cache-friendly, and work 
	well for most general-purpose programming tasks.