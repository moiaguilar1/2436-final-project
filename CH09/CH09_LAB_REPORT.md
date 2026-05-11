# Chapter 9: Dijkstra's Algorithm — Lab Report

## Student Information
- **Name:** Moises Aguilar
- **Date:** 05/10/2026
- **Course:** COSC 2436

## Algorithm Summary

- **How it works:**  
Dijkstra’s algorithm finds the shortest path between two nodes in a weighted graph. 
It starts at a source node, repeatedly selects the unvisited node with the smallest 
known cost, and updates the distances to neighboring nodes if a shorter route is 
found. The process continues until the destination node has the minimum possible cost.

- **Time complexity:**  
O(V^2) in this implementation because it scans all nodes to find the next lowest-cost node.

- **When to use it:**  
Dijkstra’s algorithm is useful for finding shortest paths in weighted graphs with non-negative 
edge weights, such as road maps, network routing, GPS navigation systems, and transportation planning.

---

## Test Results

| Input | Result | Notes |
|------|------|------|
| A → D | A → B → D | Total cost = 7 |
| Houston → Dallas | Houston → Dallas | Direct edge available |
| Austin → El Paso | Austin → San Antonio → El Paso | Shortest weighted route |

### Sample Program Output

```text
Shortest path: Houston -> Dallas
Total cost: 4
```

---

## Reflection Questions

### 1. Why can't Dijkstra’s algorithm handle negative edge weights?

Dijkstra’s algorithm assumes that once a node has the lowest known cost, that cost is final. 
Negative edge weights can later produce a cheaper path, which breaks this assumption and can 
lead to incorrect results.

---

### 2. How does Dijkstra’s algorithm differ from BFS?

Breadth-First Search finds the shortest path based only on the number of edges, while Dijkstra’s 
algorithm considers weighted edge costs. BFS works best for unweighted graphs, while Dijkstra’s 
is designed for weighted graphs with non-negative weights.

---

### 3. Why are parent nodes tracked during the algorithm?

Parent nodes allow the algorithm to reconstruct the shortest path after the search is complete. 
By tracing backward from the destination node to the start node, the full route can be displayed 
in the correct order.

---

## Challenges Encountered

One challenge was keeping the graph display readable while also highlighting the shortest path. 
Another difficulty was correctly reconstructing the path after Dijkstra’s algorithm finished running. 
This was resolved by storing parent nodes and reversing the reconstructed list at the end. Understanding 
how costs update dynamically during traversal also required careful debugging and testing with different 
graph layouts.