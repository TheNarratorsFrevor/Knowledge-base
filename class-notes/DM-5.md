# Counting

## 5.1 Fibonacci Sequence
- The Fibonacci sequence is defined recursively as:
$$
F_0 = 0, \quad F_1 = 1, \quad F_n = F_{n-1} + F_{n-2} \quad \text{for } n \geq 2
$$
- First few terms: $0, 1, 1, 2, 3, 5, 8, 13, \dots$

### Closed Form: Binet's Formula
$$
F_n = \frac{\phi^n - (1 - \phi)^n}{\sqrt{5}}
$$
Where $\phi = \frac{1 + \sqrt{5}}{2}$ (the golden ratio).

---

## 5.2 Inclusion-Exclusion Principle for 2 and 3 Sets
### Two Sets
If $A$ and $B$ are sets, then:
$$
|A \cup B| = |A| + |B| - |A \cap B|
$$

### Three Sets
For sets $A$, $B$, and $C$:
$$
|A \cup B \cup C| = |A| + |B| + |C| - |A \cap B| - |B \cap C| - |A \cap C| + |A \cap B \cap C|
$$

---

## 5.3 Dispositions, Combinations, Permutations

### 5.3.1 Dispositions with Repetition
- Number of arrangements of $r$ elements chosen from $n$ elements **with repetition**:
$$
n^r
$$
Example: Arranging 3 digits with repetition from 0-9:
$$
10^3 = 1000
$$

### 5.3.2 Permutations and Dispositions Without Repetition
#### Dispositions Without Repetition
- Number of arrangements of $r$ elements chosen from $n$ **without repetition**:
$$
P(n, r) = \frac{n!}{(n - r)!}
$$
Example: Arranging 2 letters from "ABC":
$$
P(3, 2) = \frac{3!}{(3-2)!} = 6
$$

#### Permutations
- Number of arrangements of $n$ elements:
$$
P(n) = n!
$$
Example: Permuting "ABC":
$$
3! = 6
$$

---

### 5.3.3 Combinations
- Number of ways to choose $r$ elements from $n$ elements (order does not matter):
$$
C(n, r) = \binom{n}{r} = \frac{n!}{r!(n-r)!}
$$
Example: Choosing 2 elements from 5:
$$
C(5, 2) = \binom{5}{2} = \frac{5!}{2!(5-2)!} = 10
$$

---

### Applications: Pascal's Triangle and Binomial Theorem
#### Pascal's Triangle
- Each entry is the sum of the two directly above it.

#### Binomial Theorem
For any $n \geq 0$:
$$
(a + b)^n = \sum_{k=0}^n \binom{n}{k} a^{n-k} b^k
$$
Example: Expanding $(x + 1)^3$:
$$
(x + 1)^3 = \binom{3}{0}x^3 + \binom{3}{1}x^2(1) + \binom{3}{2}x(1)^2 + \binom{3}{3}(1)^3
$$
$$
= x^3 + 3x^2 + 3x + 1
$$
