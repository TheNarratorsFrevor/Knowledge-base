# Advanced Algorithms Cheatsheet

## 0. Complexity Theory

### Time Complexity Classes

- Constant: $O(1)$  
- Logarithmic: $O(\log n)$  
- Polylogarithmic: $O((\log n)^k)$  
- Linear: $O(n)$  
- Quasilinear: $O(n \log n)$  
- Polynomial: $O(n^k)$  
- Exponential: $O(2^n)$  
- Factorial: $O(n!)$

### Big-O Notation Family

- $O(f(n))$ — upper bound
- $\Omega(f(n))$ — lower bound
- $\Theta(f(n))$ — tight bound
- $o(f(n))$ — strict upper
- $\omega(f(n))$ — strict lower

---

## 1. Sorting Algorithms

| Algorithm         | Time (Best/Average/Worst) | Space | Stable | Notes |
|------------------|---------------------------|-------|--------|-------|
| Bubble Sort      | $O(n)/O(n^2)/O(n^2)$      | $O(1)$| Yes    | educational trash |
| Insertion Sort   | $O(n)/O(n^2)/O(n^2)$      | $O(1)$| Yes    | fast on nearly-sorted |
| Merge Sort       | $O(n \log n)$             | $O(n)$| Yes    | divide & conquer |
| Quick Sort       | $O(n \log n)/O(n^2)$      | $O(\log n)$| No | in-place, cache-friendly |
| Heap Sort        | $O(n \log n)$             | $O(1)$| No     | uses binary heap |
| Radix Sort       | $O(nk)$                   | $O(n+k)$| Yes  | for fixed-length keys |
| TimSort          | $O(n \log n)$             | $O(n)$| Yes    | hybrid (Python, Java) |

---

## 2. Searching Algorithms

- Binary Search: $O(\log n)$ on sorted array  
- Ternary Search: $O(\log_3 n)$ on unimodal function  
- Interpolation Search: $O(\log\log n)$ best-case  
- Exponential Search: locate bound then binary search  
- Jump Search: $O(\sqrt{n})$ on sorted arrays

---

## 3. Graph Algorithms

### Representations

- Adjacency List: $O(V + E)$ space
- Adjacency Matrix: $O(V^2)$ space

### Traversals

- DFS (recursive or iterative) — $O(V + E)$  
- BFS — $O(V + E)$

### Shortest Path

- Dijkstra: $O((V + E)\log V)$ (binary heap)  
- Bellman-Ford: $O(VE)$ (handles negatives)  
- A* Search: uses heuristic $f(n) = g(n) + h(n)$  
- Floyd-Warshall: all-pairs $O(V^3)$  
- Johnson's Algorithm: reweights graph to use Dijkstra on negatives

### MST (Minimum Spanning Tree)

- Kruskal’s: $O(E \log E)$ (uses Union-Find)  
- Prim’s: $O(E \log V)$ (heap + adjacency list)  
- Borůvka’s: $O(E \log V)$

### Network Flow

- Ford-Fulkerson: $O(E f)$ (if integral)  
- Edmonds-Karp: $O(VE^2)$  
- Dinic’s Algorithm: $O(E \sqrt{V})$ or better  
- Push-Relabel: $O(V^3)$ worst-case

### Connectivity

- Tarjan’s SCC: $O(V + E)$  
- Kosaraju’s SCC: $O(V + E)$  
- Articulation Points & Bridges (DFS-based)  
- Union-Find (DSU): $O(\alpha(n))$ per op

---

## 4. Dynamic Programming

### Core Ideas

- Optimal substructure
- Overlapping subproblems
- Bottom-up vs top-down (memoization)

### Classical Problems

- Knapsack (0/1, bounded, unbounded)
- Longest Common Subsequence / Substring
- Edit Distance
- Matrix Chain Multiplication
- LIS (Longest Increasing Subsequence): $O(n \log n)$
- DP on Trees (e.g. subtree values, rerooting)
- Bitmask DP
- DP with Convex Hull Trick or Monotonic Queue

---

## 5. Divide & Conquer

- Merge Sort
- Binary Search
- Karatsuba’s Fast Multiplication
- Closest Pair of Points: $O(n \log n)$
- Strassen Matrix Mult.: $O(n^{\log_2 7}) \approx O(n^{2.81})$

---

## 6. Greedy Algorithms

- Activity Selection  
- Huffman Coding  
- Fractional Knapsack  
- Kruskal’s MST  
- Scheduling (Earliest Deadline First, etc.)  
- Interval Partitioning

Use greedy when:
- Greedy choice property
- Optimal substructure

---

## 7. Data Structures

### Classical

- Arrays, Linked Lists, Stacks, Queues
- Deques (e.g. Monotonic Queue)
- Priority Queues (Heaps)
- Hash Tables: $O(1)$ expected insert/lookup
- Trees (Binary, BST, AVL, Red-Black)

### Advanced

- Segment Trees (Range queries, updates): $O(\log n)$  
- Fenwick Tree / BIT: $O(\log n)$  
- Treaps / Splay Trees  
- Trie / Radix Tree  
- Disjoint Set Union (Union-Find)  
- Heavy-Light Decomposition  
- Euler Tour Tree  
- Link-Cut Tree

---

## 8. Number Theory & Math

- Euclid’s GCD: $O(\log n)$  
- Modular Inverse: $a^{-1} \equiv a^{\phi(m)-1} \pmod{m}$  
- Sieve of Eratosthenes: $O(n \log \log n)$  
- Segmented Sieve  
- Modular Exponentiation: $O(\log b)$  
- CRT (Chinese Remainder Theorem)  
- Extended Euclidean Algorithm  
- Fermat’s Little Theorem, Euler’s Theorem  
- Miller-Rabin Primality Test  
- Pollard’s Rho Factorization

---

## 9. Geometry

- Convex Hull: Graham Scan $O(n \log n)$, Andrew’s Monotone  
- Line Sweep (e.g. intersection detection)  
- Closest Pair of Points: $O(n \log n)$  
- Rotating Calipers  
- Point in Polygon: Ray Casting / Winding Number  
- Segment Intersection  
- Voronoi Diagram / Delaunay Triangulation

---

## 10. String Algorithms

- KMP (Knuth-Morris-Pratt): $O(n + m)$  
- Rabin-Karp (hash-based): $O(n + m)$ expected  
- Z-Algorithm  
- Suffix Array: $O(n \log n)$  
- Suffix Tree: $O(n)$  
- Aho-Corasick (multi-pattern search): $O(n + m + z)$  
- Manacher’s Algorithm (palindromes): $O(n)$  
- Rolling Hash / Polynomial Hashing

---

## 11. Computational Algebra

- FFT (Fast Fourier Transform): $O(n \log n)$  
- NTT (modulo prime transform)  
- Polynomial Multiplication via FFT  
- Berlekamp-Massey  
- Gauss-Jordan Elimination  
- Sparse Linear Algebra (e.g. CSR format)  
- LU/QR/Cholesky Decomposition

---

## 12. Miscellaneous

### Randomized Algorithms

- QuickSelect: $O(n)$ avg  
- Randomized Treaps  
- Monte Carlo vs Las Vegas  
- Reservoir Sampling  
- Hashing w/ Universal Hash Functions

### Parallel & Approximation

- MapReduce  
- Bloom Filters (space-efficient membership)  
- Count-Min Sketch  
- Locality-Sensitive Hashing  
- Greedy Approximation (e.g. Set Cover)

### Online Algorithms

- Paging: LRU, LFU  
- Caching / Prefetching  
- k-Server Problem  
- Competitive Ratio

---

## 13. NP-Completeness

### Common NP-complete problems

- SAT / 3-SAT  
- Vertex Cover  
- Clique  
- Subset Sum  
- Hamiltonian Path  
- Traveling Salesman  
- Partition Problem

### Reductions

$A \le_P B$: if $B$ is poly-time solvable ⇒ so is $A$  
Cook-Levin Theorem: SAT is NP-complete

---

## 14. Metaheuristics & Advanced Optimization

- Simulated Annealing  
- Genetic Algorithms  
- Tabu Search  
- Ant Colony Optimization  
- Particle Swarm  
- Branch and Bound  
- Integer Linear Programming  
- Cutting Planes, Gomory’s method

---
