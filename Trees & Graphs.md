# trees & graphs

trees and graphs are the backbone of data structures that model relationships and hierarchies. they overlap but serve different purposes. trees are a special kind of graph—specifically, an acyclic connected graph with a hierarchical structure.

---

## basics

- **graph:** a set of vertices (nodes) connected by edges (links). can be **directed** or **undirected**. edges can have weights or be unweighted.
  
- **tree:** a connected, acyclic, undirected graph. it has exactly $n-1$ edges for $n$ nodes, no cycles, and exactly one path between any two nodes.

- **rooted tree:** a tree with a designated root node; all edges implicitly point away from the root (parent to child).

- **binary tree:** each node has at most two children (left, right).

- **forest:** a collection of disjoint trees.

---

## advanced concepts

- **graph representations:**

  - **adjacency list:** stores edges as lists per node, efficient for sparse graphs.
  
  - **adjacency matrix:** 2D matrix $n \times n$ indicating edge presence/weight, good for dense graphs but uses more space.
  
  - **edge list:** simple list of edges, useful for some algorithms like kruskal.

- **graph types:**

  - **directed acyclic graph (dag):** directed graph with no cycles, used in scheduling, dependency resolution.
  
  - **weighted graph:** edges carry weights (costs, distances).
  
  - **bipartite graph:** nodes divided into two sets, edges only go between sets.
  
  - **cyclic vs acyclic:** cycle = path that starts and ends on the same node.
  
- **tree traversals:**

  - **dfs (depth-first search):** **go deep before wide**, uses stack/recursion.
  
  - **bfs (breadth-first search):** go **level by level**, uses queue.
  
  - **preorder, inorder, postorder:** specific DFS orders on rooted trees, important for expression trees, parsing.

- **key algorithms:**

  - **minimum spanning tree (mst):** find subset of edges connecting all nodes with minimal total weight. algorithms: kruskal, prim.
  
  - **shortest path:** dijkstra (non-negative weights), bellman-ford (can handle negative edges), floyd-warshall (all pairs).
  
  - **topological sort:** linear ordering of dag nodes, no edge points backward.

- **special trees:**

  - **binary search tree (bst):** left child < parent < right child, enables $O(\log n)$ avg searches.
  
  - **balanced trees:** avl, red-black, to maintain height $O(\log n)$ for efficiency.
  
  - **trie:** prefix tree used for fast string lookup.

---

## cheatsheet

| Concept             | Definition/Usage                         | Complexity                          |
|---------------------|----------------------------------------|-----------------------------------|
| graph (directed/undirected) | nodes + edges                       | $O(V+E)$ traversal                 |
| adjacency list       | array of neighbors                      | $O(V+E)$ space                    |
| adjacency matrix     | 2D boolean/integer matrix               | $O(V^2)$ space                   |
| dfs                 | deep traversal, stack/recursion         | $O(V+E)$                         |
| bfs                 | level traversal, queue                   | $O(V+E)$                         |
| mst (kruskal/prim)  | minimal connecting edges                 | $O(E \log V)$                    |
| shortest path (dijkstra) | shortest path from source, no negative weights | $O((V+E)\log V)$ with heap  |
| topological sort     | order nodes in dag                       | $O(V+E)$                         |
| bst                  | sorted binary tree                       | avg $O(\log n)$ search, worst $O(n)$ |
| balanced tree        | self-adjusting bst                       | $O(\log n)$                     |
| trie                 | prefix search tree for strings          | $O(m)$ for search, $m$ = key length |

---

## links

- for heaps & priority queues check [[heaps & priority queues]]  
- for dynamic programming on graphs see [[dynamic programming]]  
- for recursion & backtracking in graph traversal [[recursion & backtracking]]  
- for union-find (disjoint sets) data structures used in kruskal [[disjoint set union (union-find)]]

---

## flashcards
#flashcards/trees  
what is a graph?::a collection of nodes (vertices) connected by edges; can be directed or undirected  
what makes a tree different from a general graph?::a tree is a connected acyclic undirected graph with $n-1$ edges for $n$ nodes  
name two common graph representations::adjacency list and adjacency matrix  
what traversal method visits nodes level by level?::breadth-first search (bfs)  
what is a minimum spanning tree?::a subset of edges connecting all nodes with the smallest total edge weight, no cycles  
what data structure is used for prefix string searches?::trie
which algorithm finds shortest paths in graphs with non-negative weights?::dijkstra's algorithm  
what is a topological sort?::linear ordering of dag nodes so that for every edge $u \to v$, $u$ comes before $v$  
what are balanced trees?::bst variants (avl, red-black) that keep height logarithmic to ensure efficient operations  
what is the difference between dfs and bfs?::dfs explores as deep as possible first, bfs explores all neighbors level-wise
