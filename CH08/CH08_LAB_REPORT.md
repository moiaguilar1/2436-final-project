## Lab Report

### Student Information
- **Name:** Moises Aguilar
- **Date:** 05/10/2026

## Algorithm Analysis

### AVL Trees

- **Balance Factor Range:** -1 to +1
- **Why rebalance?** AVL trees rebalance to keep the tree height small, ensuring operations remain efficient. Without balancing, the tree could become skewed like a linked list.
- **Time Complexity (all operations):** O(log n)

### Rotation Cases

| Case | Imbalance | Fix |
|------|-----------|-----|
| LL   | Left subtree of left child is heavy | Single right rotation |
| RR   | Right subtree of right child is heavy | Single left rotation |
| LR   | Right subtree of left child is heavy | Left rotation, then right rotation |
| RL   | Left subtree of right child is heavy | Right rotation, then left rotation |

## Reflection Questions

### 1. Why is an unbalanced BST bad?

An unbalanced BST can become very tall and skewed, making operations such as search, insertion, and deletion much slower. In the worst case, performance degrades from O(log n) to O(n).

### 2. How do rotations maintain the BST property?

Rotations rearrange nodes while preserving the inorder relationship between values. The left subtree still contains smaller values and the right subtree still contains larger values after the rotation.

### 3. What other self-balancing trees exist?

Other self-balancing trees include:
- Red-Black Trees
- B-Trees
- Splay Trees
- Treaps
- AA Trees
- 2-3 Trees
- 2-3-4 Trees
