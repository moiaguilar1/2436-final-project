## Student Information
**Name:** Moises Aguilar  
**Date:** 05/10/2026  
**Algorithm Analysis:** Greedy Truck Packing Algorithm  

---

# Algorithm Understanding

**What type of problem is this algorithm solving?**  
This algorithm solves an optimization and packing problem. It attempts to maximize the 
amount of cargo packed into a truck while staying within the truck’s total volume capacity.

---

**Is this greedy algorithm guaranteed to produce the optimal solution? Why or why not?**  
No, the greedy algorithm is not guaranteed to produce the optimal solution. It makes locally 
optimal choices by selecting the largest boxes first, but this may prevent combinations of smaller 
boxes that could use the truck space more efficiently.

---

**What is the greedy choice made in this algorithm?**  
The greedy choice is selecting the largest-volume boxes first and packing them whenever enough 
space remains in the truck.

---

# Implementation Questions

**Why do we sort the boxes in descending order of volume before packing?**  
Sorting boxes from largest to smallest attempts to maximize space usage quickly by prioritizing large 
boxes that take up the most volume.

---

**What would happen if we sorted the boxes in ascending order instead?**  
Sorting in ascending order would pack many smaller boxes first, which could leave fragmented leftover 
space and potentially prevent larger boxes from fitting later.

---

**Why do we keep track of `used_volume`?**  
`used_volume` keeps track of how much truck space has already been occupied so the algorithm can avoid 
exceeding the truck’s capacity.

---

# Extension: Dimension Constraints

**Why is checking only volume not sufficient for real-world packing?**  
A box may fit within the remaining volume mathematically but still not physically fit due to its shape 
or dimensions. Real packing must consider length, width, and height separately.

---

**Give an example where a box fits by volume but not by dimensions.**  
A truck may have dimensions of 10 × 10 × 10 and a volume of 1000 cubic units. A box with dimensions 
20 × 2 × 2 has a volume of only 80 cubic units, but it cannot fit because the length exceeds the truck’s length.

---

**How would you modify the algorithm to check dimension constraints before packing a box?**  
Before adding a box, the algorithm should compare the box’s length, width, and height against the 
truck’s remaining dimensions or available placement space. A box should only be packed if all dimensions 
fit physically inside the truck.

---

# Reflection Questions

**What is a limitation of this greedy approach? Provide a scenario where it fails to find the optimal solution.**  
The algorithm only considers immediate choices rather than all possible combinations. For example, a large box 
might block space that could have been used more efficiently by several medium-sized boxes with a higher total 
packed volume.

---

**How is this problem related to the Knapsack Problem?**  
This problem is similar to the Knapsack Problem because both involve selecting items with limited capacity 
constraints while trying to maximize value or usage efficiency.

---

**What type of algorithm would guarantee an optimal solution for this problem? What is the tradeoff?**  
Dynamic programming or exhaustive search algorithms can guarantee an optimal solution. The tradeoff is 
significantly higher computational complexity and slower performance for large numbers of boxes.

---

**If the truck had weight limits in addition to volume, how would the algorithm need to change?**  
The algorithm would need to track both total volume and total weight. A box could only be added if it fit 
within both the remaining volume and remaining weight capacity.

---

**Why are greedy algorithms often preferred despite not always being optimal?**  
Greedy algorithms are usually faster, simpler to implement, and use less memory than exhaustive algorithms. 
They often produce good approximate solutions in practical situations where perfect optimization is too 
expensive computationally.