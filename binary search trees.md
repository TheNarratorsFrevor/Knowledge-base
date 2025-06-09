# binary search trees (bst)

## basics

bst is a type of binary tree where each node holds a key, and for every node:

- keys in the left subtree < node’s key
- keys in the right subtree > node’s key

this strict ordering means searching is faster than linear structures, often $O(\log n)$ on average, but can degrade to $O(n)$ if the tree is unbalanced (think linked list vibes).

bsts allow quick search, insert, delete — all based on the same principle of moving left/right depending on key comparison.

---

## core operations

- **search**: start at root, go left if target < current node, right if >, stop if equal or null
- **insert**: find proper leaf spot following search logic, then insert new node
- **delete**: trickiest. 3 cases:
  1. leaf node — just remove
  2. node with one child — replace node with its child
  3. node with two children — find **inorder successor** (smallest node in right subtree) or **inorder predecessor** (largest in left subtree), replace node’s key, then delete that successor/predecessor

---

## balanced vs unbalanced bst

plain bst is prone to skewed shape if data is sorted or adversarial input.

balancing variants fix this:

- **AVL trees**
  - balance factor (height difference of left/right subtree) ≤ 1 at every node
  - rotations used on insert/delete to restore balance
- **red-black trees**
  - color-coded nodes (red/black) with rules to ensure approx balanced height $O(\log n)$
  - simpler to maintain than AVL, widely used in std libs (e.g. C++ std::map)
- **splay trees**
  - self-adjusting, recently accessed nodes move closer to root
  - amortized $O(\log n)$ access

---

## advanced BST concepts

- **order statistic tree**
  - BST augmented with subtree sizes for quick rank/select queries
- **augmented BST**
  - store extra info like subtree sums, min/max, to support range queries
- **persistent BST**
  - immutability and versioning; keep old versions after updates
- **treaps**
  - BST + heap combo, keys maintain BST order, priorities maintain heap property for probabilistic balancing

---

## complexity

| operation | average | worst case    |
|-----------|---------|--------------|
| search    | $O(\log n)$ | $O(n)$ (skewed) |
| insert    | $O(\log n)$ | $O(n)$           |
| delete    | $O(\log n)$ | $O(n)$           |

balanced BSTs guarantee $O(\log n)$ worst-case for all ops.

---

## cheatsheet

| op      | idea                                 | complexity           | notes                         |
|---------|------------------------------------|----------------------|-------------------------------|
| search  | descend left/right by comparing key| $O(\log n)$ avg      | $O(n)$ worst unbalanced       |
| insert  | like search, insert at null spot   | $O(\log n)$ avg      | rebalance if AVL/red-black    |
| delete  | 3 cases, replace with successor    | $O(\log n)$ avg      | trickiest op                  |
| rotate  | fix AVL/red-black tree balance     | $O(1)$ per rotation  | left/right rotations          |
| inorder | left-root-right traversal for sorted order | $O(n)$           | useful for debugging/printing |

---

## related topics

- [[binary trees]]
- [[avl trees]]
- [[red-black trees]]
- [[splay trees]]
- [[order statistic trees]]
- [[balanced search trees]]
- [[tree rotations]]
