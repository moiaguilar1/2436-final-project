# Chapter 1 Lab Report: Binary Search

## Student Information
- **Name:** Moises Aguilar
- **Date:** 05/08/2026 (for lack of a better date)
- **Course:** COSC 2436

## Algorithm Summary

### Linear Search
Linear search is the simplest way to find something in a list.

Imagine you have a stack of papers and you’re looking for a specific name. You start at the first paper, check it, then move to the next one, and keep going until you either:

* find the item, or
* reach the end of the list.

#### Example
List: `[4, 7, 2, 9, 5]`

Find `9`:
1. Check `4` -> not correct
2. Check `7` -> not correct
3. Check `2` -> not correct
4. Check `9` -> found it!

#### Time Complexity
* Best case: `O(1)`
    * The item is the first element.
* Worst case: `O(n)`
    * The item is at the end or not present.
* Average case: `O(n)`

`n` represents the number of items in the list.

This is exactly how linear search works in programming.

#### When to Use Linear Search
Use linear search when:
* the list is **small**
* the data is **unsorted**
* simplicity matters more than speed
* searches are to be occasionally performed

#### Advantages
* *Very* easy to implement
* Works on unsorted data
* No preparation needed

#### Disadvantages
* Slow for large datasets/lists
* Must potentially check every item

### Binary Search
Binary search is a much faster method compared to linear search, but it
only works on **sorted** data.

Instead of checking every item one by one, binary search repeatedly cuts
the search area in half.

Imagine guessing a number between 1 and 100:
* If someone says "higher" or "lower", you eliminate half the possibilities each time.

That is how binary search works.

#### Example

Given this sorted list: ```[2, 4, 5, 7, 9, 12, 15]```

Find `9`:
1. Check the middle value -> `7`
2. `9` is larger than `7`, so ignore the left half
3. Remaining list: ```[9, 12, 15]```
4. Check middle again -> `12`
5. `9` is smaller than `12`, so ignore the right half
6. Check the remaining value -> `9` found

#### Time Complexity
* Best case: `O(1)`
    * The middle element is the target.
* Worst case: `O(log n)`
* Average case: `O(log n)`

`log n` means the problem size gets cut in half each step.

####  When to Use Binary Search
Use binary search when:
* the data is **sorted**
* the dataset is **large**
* fast searching is important
* searching the same dataset many times 

#### Advantages
* Very fast on large datasets
* Efficient and scalable

#### Disadvantages
* Requires sorted data
* *Slightly* more complex to implement
* Sorting the data first may take extra time

## Test Results

```
Binary Search vs Linear Search Time Comparison
================================================
Searching in a sorted list of 128 numbers

Searching for: 1
Linear search time: 0.00000191 seconds
Binary search time: 0.00000286 seconds
Linear search result: 0
Binary search result: 0
Binary search is 0.67x faster

Searching for: 64
Linear search time: 0.00000501 seconds
Binary search time: 0.00000167 seconds
Linear search result: 63
Binary search result: 63
Binary search is 3.00x faster

Searching for: 128
Linear search time: 0.00000334 seconds
Binary search time: 0.00000238 seconds
Linear search result: 127
Binary search result: 127
Binary search is 1.40x faster

Searching for: 50
Linear search time: 0.00000215 seconds
Binary search time: 0.00000143 seconds
Linear search result: 49
Binary search result: 49
Binary search is 1.50x faster

Searching for: 100
Linear search time: 0.00000238 seconds
Binary search time: 0.00000072 seconds
Linear search result: 99
Binary search result: 99
Binary search is 3.33x faster

Searching for: 25
Linear search time: 0.00000072 seconds
Binary search time: 0.00000072 seconds
Linear search result: 24
Binary search result: 24
Binary search is 1.00x faster

Searching for: 75
Linear search time: 0.00000191 seconds
Binary search time: 0.00000072 seconds
Linear search result: 74
Binary search result: 74
Binary search is 2.67x faster

Searching for: 10
Linear search time: 0.00000048 seconds
Binary search time: 0.00000048 seconds
Linear search result: 9
Binary search result: 9
Binary search is 1.00x faster

Searching for: 90
Linear search time: 0.00000191 seconds
Binary search time: 0.00000072 seconds
Linear search result: 89
Binary search result: 89
Binary search is 2.67x faster

Searching for: 200
Linear search time: 0.00000310 seconds
Binary search time: 0.00000072 seconds
Linear search result: None
Binary search result: None
Binary search is 4.33x faster

Lab Challenge Answer:
Maximum steps for binary search in 128 items:
log2(128) = 7 steps maximum
```
