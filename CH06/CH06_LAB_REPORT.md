# Lab 6: Breadth-First Search

## Student Information
- **Name:** Moises Aguilar
- **Date:** 05/10/2026  

---

# Graph Concepts

## Adjacency List Representation

The graph is stored using an adjacency list. Each city (vertex) keeps a list of 
neighboring cities directly connected by roads (edges). This representation is 
memory efficient for sparse graphs because only existing connections are stored.

---

## BFS Algorithm Steps

1. Start at the beginning vertex.
2. Add the starting vertex to a queue.
3. Mark the starting vertex as visited.
4. Remove a vertex from the front of the queue.
5. Check all neighboring vertices.
6. Add unvisited neighbors to the queue and mark them visited.
7. Continue until the destination is found or the queue becomes empty.
8. The first path found is the shortest path by number of edges.

---

# Test Results

| Start | End | Path | Edges |
|-------|-----|------|-------|
| Houston | El Paso | Houston → San Antonio → El Paso | 2 |
| Houston | McKinney | Houston → Dallas → Plano → McKinney | 3 |
| Dallas | Laredo | Dallas → Austin → San Antonio → Laredo | 3 |

---

# Reflection Questions

## 1. Why does BFS use a queue instead of a stack?

BFS uses a queue because it processes vertices in the order they are 
discovered (FIFO). This allows the algorithm to explore 
all vertices at one distance level before moving to the next level, 
which guarantees the shortest path in an unweighted graph.

---

## 2. What's the difference between BFS shortest path and actual shortest distance?

BFS finds the shortest path based on the fewest number of edges between 
vertices. It does not consider real-world distances or weights. Actual 
shortest distance problems use weighted graphs and algorithms such as 
Dijkstra’s algorithm.

---

## 3. When would you use BFS vs DFS?

Use BFS when you need the shortest path in an unweighted graph or want to explore nodes 
level by level. Use DFS when exploring all possible paths, traversing deep structures, 
or solving problems like maze generation, recursion, and topological traversal.