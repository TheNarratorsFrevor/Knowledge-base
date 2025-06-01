# Sets, Relations, and Functions

## 1. Operations on Sets
- **Union**: $A \cup B = \{x \mid x \in A \text{ or } x \in B\}$
- **Intersection**: $A \cap B = \{x \mid x \in A \text{ and } x \in B\}$
- **Difference**: $A \setminus B = \{x \mid x \in A \text{ and } x \notin B\}$
- **Complement**: $\overline{A} = U \setminus A$, where $U$ is the universal set.
- **Subset**: $A \subseteq B \iff \forall x (x \in A \implies x \in B)$

## 1.1 Graphs
- A **graph** $G$ is a pair $(V, E)$ where:
  - $V$: Set of vertices
  - $E$: Set of edges (pairs of vertices)
- Types of graphs:
  - **Undirected**: Edges have no orientation.
  - **Directed (digraph)**: Edges have direction $e = (u, v)$.
- Graph properties:
  - Degree of a vertex $v$: $\deg(v)$ is the number of edges incident to $v$.
  - Path: A sequence of vertices connected by edges.

## 1.2 Cartesian Product and Relations
- **Cartesian Product**: $A \times B = \{(a, b) \mid a \in A, b \in B\}$
- **Relation**: A subset of the Cartesian product: $R \subseteq A \times B$
- **Properties of relations**:
  - Reflexive: $\forall a \in A, (a, a) \in R$
  - Symmetric: $(a, b) \in R \implies (b, a) \in R$
  - Transitive: $(a, b) \in R \land (b, c) \in R \implies (a, c) \in R$

## 1.3 Partitions
- A **partition** of a set $A$ is a collection of subsets $\{A_1, A_2, \dots, A_n\}$ such that:
  - $A_i \cap A_j = \emptyset$ for $i \neq j$
  - $\bigcup_{i=1}^n A_i = A$

## 1.4 Matrices
- Representation of relations:
  - For a relation $R \subseteq A \times B$, matrix $M$:
    - $M[i][j] = 1$ if $(a_i, b_j) \in R$, else $M[i][j] = 0$.
- Matrix operations:
  - Transpose: $M^T$
  - Multiplication: $(M_1 \cdot M_2)[i][j] = \sum_k M_1[i][k] \cdot M_2[k][j]$

## 1.5 Functions
- A **function** $f: A \to B$ assigns exactly one element of $B$ to each element of $A$.
- Types of functions:
  - **Injective**: $f(a_1) = f(a_2) \implies a_1 = a_2$
  - **Surjective**: $\forall b \in B, \exists a \in A$ such that $f(a) = b$
  - **Bijective**: Both injective and surjective.

## 1.6 Functions and Operators on Bits
- Boolean functions:
  - AND: $f(a, b) = a \land b$
  - OR: $f(a, b) = a \lor b$
  - XOR: $f(a, b) = a \oplus b$
  - NOT: $f(a) = \neg a$
- Bitwise operations:
  - $a \land b, a \lor b, a \oplus b, \neg a$

## 1.7 Bijections on Finite Sets: Permutations
- A **permutation** of a set $S = \{1, 2, \dots, n\}$ is a bijection $f: S \to S$.
- Number of permutations: $n!$
- Cycle notation:
  - $(1\ 2\ 3)$ means $1 \to 2, 2 \to 3, 3 \to 1$.

## 1.8 Walks on Graphs and Adjacency Matrix
- A **walk** in a graph is a sequence of vertices $v_1, v_2, \dots, v_k$ such that $(v_i, v_{i+1}) \in E$.
- **Adjacency matrix** $A$:
  - $A[i][j] = 1$ if $(v_i, v_j) \in E$, else $A[i][j] = 0$.
- Walks of length $k$:
  - Number of walks from $v_i$ to $v_j$: $(A^k)[i][j]$

## 1.9 Proof by Induction
1. **Base case**: Prove for the initial value (e.g., $n = 1$).
2. **Inductive hypothesis**: Assume the statement holds for $n = k$.
3. **Inductive step**: Prove the statement for $n = k + 1$ using the hypothesis.

Example:
$$
P(n): 1 + 2 + \dots + n = \frac{n(n+1)}{2}
$$
- Base case: $P(1) = 1 = \frac{1(1+1)}{2}$ (True)
- Inductive step: Assume $P(k)$. Show $P(k+1)$:
$$
1 + 2 + \dots + k + (k+1) = \frac{k(k+1)}{2} + (k+1) = \frac{(k+1)(k+2)}{2}
$$
