# 🧱 Data Structures Cheatsheet

## 1. Arrays & Lists

### Arrays
- Fixed-size, contiguous memory
- Access: $O(1)$, Insert/Delete: $O(n)$ (shift required)
- Good for random access, bad for dynamic sizing

### Dynamic Arrays (e.g., Python list, C++ vector)
- Amortized insert: $O(1)$ (due to resizing)
- Backed by doubling-size reallocation

### Linked Lists
- Singly: Each node → next
- Doubly: prev + next pointers
- Access: $O(n)$, Insert/Delete (given pointer): $O(1)$

---

## 2. Stacks & Queues

### Stack (LIFO)
- Push/Pop: $O(1)$
- Use: recursion, undo, syntax parsing

### Queue (FIFO)
- Enqueue/Dequeue: $O(1)$
- Use: BFS, scheduling, buffering

### Deque (Double-Ended Queue)
- Insert/Delete both ends in $O(1)$

---

## 3. Hash Tables

- Key → hash → index
- Avg-case: Insert/Search/Delete = $O(1)$
- Worst-case: $O(n)$ (collision hell)
- Handle collisions via:
  - Chaining (linked list at each bucket)
  - Open addressing (linear probing, quadratic, double hashing)

### Load Factor
$$
\alpha = \frac{\text{num elements}}{\text{table size}}
$$

Resize when $\alpha$ exceeds threshold (e.g. 0.75)

---

## 4. Trees

### Binary Trees

- Each node has ≤ 2 children
- Depth: $\log n$ (balanced), $n$ (degenerate)

### Binary Search Tree (BST)

- Left < Root < Right
- Search/Insert/Delete: $O(\log n)$ avg, $O(n)$ worst
- Unbalanced = degenerate linked list

### AVL Tree

- Self-balancing BST
- Balance factor ∈ $\{-1, 0, 1\}$
- Rotations to maintain balance
- All ops: $O(\log n)$

### Red-Black Tree

- BST + coloring rules
- Less rigid than AVL, faster insertions
- All ops: $O(\log n)$
- Used in C++ STL map/set

### B-Trees

- Generalization of BST, optimized for disk
- Nodes with many keys/children
- Used in databases, file systems

---

## 5. Heaps

### Binary Heap (Min/Max)

- Complete binary tree
- Min-heap: parent ≤ children
- Max-heap: parent ≥ children
- Insert: $O(\log n)$ (bubble up)
- Delete-min: $O(\log n)$ (heapify down)
- Use: priority queues, Dijkstra, heapsort

### Heap Variants

- Fibonacci heap: better amortized time for decrease-key: $O(1)$
- Binomial heap: mergeable heap with tree structure

---

## 6. Tries (Prefix Trees)

- Store strings by character paths
- Insert/Search: $O(k)$ for string of length $k$
- Space-efficient w/ large vocab, good for autocomplete
- Can be compressed to radix/patricia trie

---

## 7. Graph Representations

### Adjacency Matrix

- $V \times V$ matrix
- Edge: $O(1)$ lookup
- Space: $O(V^2)$
- Good for dense graphs

### Adjacency List

- Array of lists
- Edge lookup: $O(\deg(v))$
- Space: $O(V + E)$
- Good for sparse graphs

---

## 8. Disjoint Set (Union-Find)

- Supports:
  - `find(x)`: returns root
  - `union(x, y)`: merges sets
- Optimizations:
  - Union by rank
  - Path compression
- Time: $O(\alpha(n))$ (inverse Ackermann)
- Use: Kruskal’s MST, connected components

---

## 9. Segment Trees

- Binary tree storing range information
- Each node = function of child ranges
- Build: $O(n)$, Query/Update: $O(\log n)$
- Used for range min/max/sum queries

### Lazy Propagation

- Defers updates to children
- Useful for range updates in $O(\log n)$

---

## 10. Fenwick Tree (Binary Indexed Tree)

- Stores prefix sums
- Update/query: $O(\log n)$
- Space: $O(n)$
- Simpler than segment tree for prefix-sum

---

## 11. Bloom Filters

- Probabilistic set
- No false negatives, false positives possible
- Use $k$ hash functions
- Insert: set $k$ bits
- Query: check $k$ bits
- Space-efficient, fast

---

## 12. Skip Lists

- Probabilistic alternative to balanced BST
- Multiple levels of linked lists
- Search/Insert/Delete: expected $O(\log n)$
- Simple to implement, used in Redis

---

## 13. LRU Cache

- Uses hash map + doubly linked list
- Insert/Search/Delete: $O(1)$
- Least Recently Used item eviction
- Used in caching systems, OS page replacement

---

## 14. Suffix Trees & Arrays

- String data structures
- Suffix Tree: all suffixes as paths, $O(n)$ time
- Suffix Array: sorted suffixes array, $O(n \log n)$
- Use: substring search, LCP, bioinformatics

---

## 15. Rope

- Balanced tree storing strings in leaves
- Efficient insert/delete/concat: $O(\log n)$
- Useful for large text buffers

---

## 16. KD-Trees

- Space partitioning for $k$-dim data
- Used in nearest neighbor, range queries
- Insert/Search: $O(\log n)$ avg, $O(n)$ worst

---

## 17. Bloomier Filter

- Generalization of Bloom filter
- Maps keys to values with space efficiency
- Probabilistic errors allowed

---

## 18. Treaps

- BST + heap (priority)
- Maintains BST on key, heap on random priority
- Expected $O(\log n)$ ops
- Simpler randomized balancing

---
