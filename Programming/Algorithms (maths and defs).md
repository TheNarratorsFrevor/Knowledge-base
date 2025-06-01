# Algorithmic Mathematics & Definitions Cheatsheet

## 1. Functions and Growth

### Asymptotic Notation

- $f(n) = O(g(n)) \Rightarrow \exists c, n_0$ s.t. $f(n) \leq c \cdot g(n)$ for $n > n_0$
- $f(n) = \Theta(g(n)) \Rightarrow f(n) = O(g(n))$ and $f(n) = \Omega(g(n))$
- $f(n) = o(g(n)) \Rightarrow \lim_{n \to \infty} f(n)/g(n) = 0$
- $f(n) = \omega(g(n)) \Rightarrow \lim_{n \to \infty} f(n)/g(n) = \infty$

### Common Function Orders

$$
\log \log n < \log n < n^\epsilon < n < n \log n < n^2 < 2^n < n! < n^n
$$

---

## 2. Recurrences

### Master Theorem (Divide and Conquer)

Given $T(n) = aT(n/b) + f(n)$:

- If $f(n) = O(n^{\log_b a - \epsilon})$, then $T(n) = \Theta(n^{\log_b a})$
- If $f(n) = \Theta(n^{\log_b a} \log^k n)$, then $T(n) = \Theta(n^{\log_b a} \log^{k+1} n)$
- If $f(n) = \Omega(n^{\log_b a + \epsilon})$ and regularity holds, then $T(n) = \Theta(f(n))$

### Recurrence Types

- Linear homogeneous: $T(n) = aT(n-1) + b$
- Divide-and-conquer: $T(n) = aT(n/b) + f(n)$
- Dynamic programming recurrences: grid or DAG-based

---

## 3. Counting & Combinatorics

### Basics

- Permutations: $P(n, k) = \frac{n!}{(n-k)!}$
- Combinations: $C(n, k) = \binom{n}{k} = \frac{n!}{k!(n-k)!}$
- Stars and Bars: number of non-negative integer solutions to $x_1 + x_2 + \dots + x_k = n$ is $\binom{n + k - 1}{k - 1}$

### Inclusion-Exclusion

$$
|A \cup B| = |A| + |B| - |A \cap B|
$$

General form:

$$
|\bigcup_{i=1}^n A_i| = \sum |A_i| - \sum |A_i \cap A_j| + \sum |A_i \cap A_j \cap A_k| - \dots
$$

---

## 4. Probability

### Basics

- Uniform: $P(A) = \frac{|A|}{|S|}$  
- Conditional: $P(A \mid B) = \frac{P(A \cap B)}{P(B)}$  
- Independence: $P(A \cap B) = P(A)P(B)$  
- Bayes’ Theorem: $P(A \mid B) = \frac{P(B \mid A)P(A)}{P(B)}$

### Distributions

- Bernoulli, Binomial: Discrete counting
- Geometric: Trials until first success
- Poisson: Events per time/unit
- Uniform, Normal, Exponential: Continuous

### Expectation & Variance

- $E[X] = \sum x P(x)$ or $\int x f(x) dx$
- $Var(X) = E[X^2] - (E[X])^2$
- Linearity: $E[X+Y] = E[X] + E[Y]$ (even if $X$, $Y$ dependent)

---

## 5. Number Theory

### GCD, LCM

- $\gcd(a, b)$: greatest common divisor
- $a, b$ coprime $\iff \gcd(a, b) = 1$
- $\text{lcm}(a, b) = \frac{ab}{\gcd(a, b)}$

### Modular Arithmetic

- Congruence: $a \equiv b \pmod{m}$
- Modular inverse: $a^{-1} \equiv x \Rightarrow ax \equiv 1 \pmod{m}$
- Fermat's Little Theorem: $a^{p-1} \equiv 1 \pmod{p}$ if $p$ is prime
- Euler’s theorem: $a^{\phi(m)} \equiv 1 \pmod{m}$

---

## 6. Graph Theory

### Definitions

- Graph: $G = (V, E)$
- Degree: number of edges per vertex
- Path, Cycle, Tree, DAG
- Connected vs Strongly Connected

### Matrix Representations

- Adjacency Matrix $A_{ij} = 1$ if edge from $i$ to $j$
- Degree Matrix $D_{ii} = \text{deg}(v_i)$
- Laplacian: $L = D - A$

### Tree Properties

- $n$ nodes → $n-1$ edges
- Unique path between any two vertices

---

## 7. Logic & Boolean Algebra

### Propositional Logic

- $A \rightarrow B = \neg A \lor B$
- $A \leftrightarrow B = (A \rightarrow B) \land (B \rightarrow A)$

### Boolean Identities

- De Morgan’s: $\neg(A \land B) = \neg A \lor \neg B$
- Absorption: $A \lor (A \land B) = A$
- Distributive: $A \land (B \lor C) = (A \land B) \lor (A \land C)$

### SAT & CNF

- CNF: conjunction of disjunctions  
- 3-SAT: known NP-complete

---

## 8. Linear Algebra

### Basics

- Vector: ordered tuple in $\mathbb{R}^n$
- Matrix multiplication: $(AB)_{ij} = \sum_k A_{ik} B_{kj}$
- Dot product: $a \cdot b = \sum a_i b_i$
- Norm: $\|x\| = \sqrt{\sum x_i^2}$

### Matrix Types

- Identity $I$, Diagonal, Symmetric, Orthogonal
- Inverse: $AA^{-1} = I$
- Rank: dimension of row space

### Determinants

- $n \times n$ matrix → scalar
- $\det(AB) = \det(A)\det(B)$
- $\det(A) = 0$ ⇔ singular ⇔ no inverse

---

## 9. Set Theory

### Definitions

- Union: $A \cup B$
- Intersection: $A \cap B$
- Complement: $A^c$
- Power set: $\mathcal{P}(A)$ has $2^{|A|}$ elements

### Cardinality

- Finite vs Countable vs Uncountable
- $\mathbb{N}, \mathbb{Z}, \mathbb{Q}$ are countable
- $\mathbb{R}$ is uncountable

---

## 10. Logic & Computability

### Turing Machines

- Alphabet, tape, states, transition function
- Accept/reject on halting
- Church-Turing Thesis

### Computability

- Decidable: there exists a halting TM
- Undecidable: no algorithm exists (e.g. Halting Problem)

### Complexity Classes

- P ⊆ NP ⊆ PSPACE ⊆ EXP
- NP: verifiable in poly time
- NP-Complete: hardest in NP
- Reductions: $A \leq_p B$ → $A$ reduces to $B$ in poly time

---
