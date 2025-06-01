# 📐 Data Structures: Math & Definitions Cheatsheet

## 1. Arrays & Indexing

- **Definition**: Ordered collection of fixed size.
- **Mathematical model**: Function $A: \{0, 1, \dots, n-1\} \rightarrow D$  
- **Random access**: $A[i]$ in $O(1)$

---

## 2. Linked Lists

- **Singly linked**: Node = $(v, \text{next})$
- **Mathematical representation**: Recursive structure
  $$
  \text{List} ::= \text{Nil} \;|\; \text{Cons}(x, \text{List})
  $$
- Access: $O(n)$, insert at head: $O(1)$

---

## 3. Trees

- **Recursive def**: A tree is a node + list of subtrees.
- **Binary Tree**: $T ::= \emptyset \;|\; \text{Node}(v, T_\text{left}, T_\text{right})$
- **Size**: $|T| = 1 + |T_\text{left}| + |T_\text{right}|$
- **Height**: $h(T) = 1 + \max(h(T_\text{left}), h(T_\text{right}))$

---

## 4. Binary Search Trees (BSTs)

- **Invariant**: $T = \text{Node}(k, L, R) \Rightarrow \forall x \in L, x < k; \forall x \in R, x > k$
- **Operations**: search, insert, delete ∈ $O(h)$
- Worst case $O(n)$, avg case $O(\log n)$

---

## 5. AVL Trees

- Balanced BST where $\left| \text{height}(L) - \text{height}(R) \right| \leq 1$
- Rebalancing via rotations
- Guarantees $O(\log n)$ ops

---

## 6. Red-Black Trees

- Binary search tree w/ color invariant:
  - Every path from root to null has same number of black nodes
  - No two red nodes in a row
- Ensures height $\leq 2\log(n+1)$

---

## 7. Heaps

- **Definition**: Complete binary tree where parent ≤ children
- Min-heap property: $\forall v \in T$, $v \leq \text{children}(v)$
- Insert: bubble up, $O(\log n)$
- Delete-min: swap root w/ last, bubble down

---

## 8. Hash Tables

- **Hash function**: $h: K \rightarrow \{0, 1, \dots, m-1\}$
- **Uniform hashing assumption**: $P(h(k_1) = h(k_2)) = 1/m$
- Expected lookup/insert/delete: $O(1)$
- Collisions resolved via chaining or probing

---

## 9. Disjoint Sets (Union-Find)

- **Equivalence classes**: $a \sim b$ iff in same set
- Represented via parent pointers + path compression
- Union by rank + compression → $O(\alpha(n))$ time
- $\alpha(n)$ = inverse Ackermann, basically constant

---

## 10. Tries

- Rooted tree with edges labeled by symbols
- Path from root = string prefix
- Used to implement prefix search in $O(k)$
- Trie of strings $S \subseteq \Sigma^*$

---

## 11. Graphs

- **Definition**: $G = (V, E)$ with $E \subseteq V \times V$
- Directed if $(u, v) \in E$ ≠ $(v, u)$
- Degree: $\deg(v) = \text{number of adjacent nodes}$
- Adjacency matrix: $A_{ij} = 1 \iff (i, j) \in E$
- Adjacency list: $A[i] = \{j \mid (i, j) \in E\}$

---

## 12. Segment Trees

- Binary tree storing range aggregates
- Node $v$ stores: $T[v] = f(T[2v], T[2v+1])$
- Used for RMQ, RSQ in $O(\log n)$

---

## 13. Fenwick Tree (BIT)

- Array-based structure for prefix operations
- $A[i]$ stores partial sum of some subset of elements
- Least significant bit (LSB) controls range
- Query/update in $O(\log n)$

---

## 14. Bloom Filters

- Probabilistic structure for set membership
- $k$ hash functions: $h_1, \dots, h_k$
- Insert: set $k$ bits
- Query: check all $k$ bits
- False positives possible; false negatives not

---

## 15. Skip Lists

- Layers of linked lists
- Level $i$ contains $\approx 1/2^i$ of nodes
- Expected search time $O(\log n)$
- Probabilistic balancing, no rotation

---

## 16. Suffix Trees / Arrays

- Compact trie of all suffixes of string $S$
- Used in: LCP computation, pattern matching, bioinformatics
- Suffix array: sorted list of suffix indices
- LCP array: $\text{LCP}[i] = \text{length of common prefix}(S[i:], S[i+1:])$

---

## 17. Priority Queues

- Abstract structure: supports `insert`, `extract-min`
- Implemented using:
  - Binary heap: $O(\log n)$ ops
  - Fibonacci heap: $O(1)$ amortized insert, $O(\log n)$ extract

---

## 18. KD-Trees

- Space-partitioning trees for $k$-dimensional data
- Recursive axis-based splitting
- Used for NN search, range queries
- Balanced → depth $O(\log n)$

---

## 19. Mathematical Complexity Definitions

### Big-O

$$
f(n) = O(g(n)) \Rightarrow \exists c, n_0: f(n) \leq c g(n), \forall n > n_0
$$

### Inverse Ackermann

$$
\alpha(n) = \min \{ k \mid A(k, 4) \geq n \}
$$
- Appears in Union-Find complexity
- $\alpha(n) < 5$ for all practical $n$

---

## 20. Category-Theoretic View (esoteric)

- Many DS are **monoids** under merge: $(S, \circ, e)$
- Union-find: disjoint sets with idempotent merge
- Segment trees: monoid folding over intervals
- Tries: prefix closure over $\Sigma^*$

---
