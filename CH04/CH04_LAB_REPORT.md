# Lab 04: Quicksort

## Student Information
- **Name:** Moises Aguilar
- **Date:** 05/08/2026

## Quicksort Concepts

### Divide and Conquer
Quicksort uses divide-and-conquer by breaking a large problem into smaller problems. It chooses a 
pivot value, divides the array into smaller arrays based on the pivot, then recursively sorts 
those smaller arrays. After the smaller arrays are sorted, they are combined into one fully sorted array.

### The Three Steps
1. **Choose pivot:** Select one element from the array to act as the pivot. The pivot is used to split the array into smaller sections.
2. **Partition:** Compare every other element to the pivot. Values smaller than the pivot go into the "less" list, and values greater than the pivot go into the "greater" list.
3. **Recurse and combine:** Recursively apply quicksort to the smaller lists, then combine the results as:
   ```python
   quicksort(less) + [pivot] + quicksort(greater)
   ```

## Tracing Quicksort
```
quicksort([3, 5, 2, 1, 4])

Pivot = 3
Less = [2, 1]
Greater = [5, 4]

    quicksort([2, 1])

    Pivot = 2
    Less = [1]
    Greater = []

        quicksort([1])
        Base case: return [1]

        quicksort([])
        Base case: return []

    Combine:
    [1] + [2] + [] = [1, 2]

    quicksort([5, 4])

    Pivot = 5
    Less = [4]
    Greater = []

        quicksort([4])
        Base case: return [4]

        quicksort([])
        Base case: return []

    Combine:
    [4] + [5] + [] = [4, 5]

Final combine:
[1, 2] + [3] + [4, 5]

Result:
[1, 2, 3, 4, 5]
```

### Trace: quicksort([3, 5, 2, 1, 4])
[Draw out each recursive call step by step, showing the pivot, less, and greater at each level]

## Complexity Analysis

| Case | Time Complexity | Why? |
|------|----------------|------|
| Best | O(n log n) | The pivot divides the array into two equal halves each time, creating balanced recursion. |
| Average | O(n log n) | On average, the partitions are reasonably balanced, so the algorithm remains efficient. |
| Worst | O(n²) | The pivot creates extremely unbalanced partitions, such as one side having all elements and the other side being empty. |

## Reflection Questions

1. What happens if the array is already sorted and you always pick the first element as pivot?
If the array is already sorted and the first element is always chosen as the pivot, quicksort creates very unbalanced 
partitions. One side will contain all remaining elements, causing worst-case performance of O(n²).

2. How could you improve pivot selection to avoid worst-case performance?
You can improve pivot selection by choosing a random pivot or using the median-of-three method (first, middle, and 
last elements). This helps create more balanced partitions.

3. How does quicksort compare to other sorting algorithms you know (e.g., bubble sort, merge sort)?
Quicksort is usually much faster than bubble sort because bubble sort has O(n²) average performance. Quicksort is 
often faster in practice than merge sort because it has lower memory usage and good cache performance, although merge sort guarantees O(n log n) even in the worst case.

4. Why do we use `array[1:]` instead of `array` when building the less and greater lists?
We use `array[1:]` to skip the pivot element at index 0. If we included the entire array, the pivot would be 
compared against itself and incorrectly added to one of the partitions.