# Lab 05: Hash Table

## Student Information
- **Name:** Moises Aguilar
- **Date:** 05/08/2026

## Key Concepts

### What is a Hash Table?
A hash table is a data structure that stores key-value pairs and allows very fast insertion and searching. 
It works by using a hash function to convert a key into an index in an array. The value is then stored at that index.

For example:
```python
hash("apple") -> index 3
```

The value associated with `"apple"` would be stored at index 3 in the table.

Hash tables are commonly used for dictionaries, maps, and fast lookups.

### Linear Probing
Linear probing is a collision handling technique used when two keys hash to the same index.

If a position in the table is already occupied, the program checks the next position until it finds an empty slot.

Example:
```
Index 2 occupied
Try index 3
If occupied, try index 4
Continue until empty slot found
```

Linear probing helps keep all data inside the same array without using linked lists.

## Tracing Exercise

Assume:
- Table size = 10
- Hash results:
  - `apple → 3`
  - `banana → 5`
  - `orange → 3`

### Insert "apple"

```
Index: 0 1 2 3 4 5 6 7 8 9
Value: - - - apple - - - - - -
```

### Insert "banana"

```
Index: 0 1 2 3 4 5 6 7 8 9
Value: - - - apple - banana - - - -
```

### Insert "orange"

`orange` hashes to index 3, but index 3 is already occupied by `apple`.

Using linear probing:
- Check index 4 → empty
- Insert at index 4

```
Index: 0 1 2 3 4 5 6 7 8 9
Value: - - - apple orange banana - - - -
```

## Complexity Analysis

| Operation | Average Case | Worst Case |
|---|---|---|
| Insert | O(1) | O(n) |
| Search | O(1) | O(n) |

## Reflection Questions

1. What are the advantages of using a hash table?

Hash tables provide very fast insertion, deletion, and searching on average. They are efficient 
for storing and retrieving large amounts of data using keys.

2. How does the hash function affect the performance of a hash table?

A good hash function distributes keys evenly across the table, reducing collisions and improving 
performance. A poor hash function causes many collisions, making operations slower.

3. What are other collision resolution techniques besides linear probing?

Other collision resolution techniques include:
- Quadratic probing
- Double hashing
- Separate chaining using linked lists
- Cuckoo hashing