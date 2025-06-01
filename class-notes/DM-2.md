# Discrete Algebra

## 2.1 Algebraic Structures: Groups and Fields
- **Group**: A set $G$ with an operation $\cdot$ satisfying:
  1. Closure: $\forall a, b \in G, a \cdot b \in G$
  2. Associativity: $a \cdot (b \cdot c) = (a \cdot b) \cdot c$
  3. Identity: $\exists e \in G$ such that $a \cdot e = e \cdot a = a$
  4. Inverse: $\forall a \in G, \exists a^{-1} \in G$ such that $a \cdot a^{-1} = e$
- **Field**: A set $F$ with two operations $(+, \cdot)$ satisfying:
  - $(F, +)$ is an abelian group.
  - $(F \setminus \{0\}, \cdot)$ is an abelian group.
  - Distributive property: $a \cdot (b + c) = a \cdot b + a \cdot c$.

## 2.2 Vectors of Bits
- A **vector of bits** is an element of $\mathbb{F}_2^n$, where $\mathbb{F}_2 = \{0, 1\}$.
- Operations:
  - Addition: Bitwise XOR $\oplus$
  - Scalar multiplication: $c \cdot v$, where $c \in \mathbb{F}_2$

Example:
$$
\mathbf{v}_1 = (1, 0, 1), \mathbf{v}_2 = (0, 1, 1) \implies \mathbf{v}_1 + \mathbf{v}_2 = (1, 1, 0)
$$

## 2.3 Polynomials on Bits
### 2.3.1 Sum of Polynomials
- For polynomials $f(x), g(x) \in \mathbb{F}_2[x]$:
$$
f(x) + g(x) = \sum a_i x^i + \sum b_i x^i \pmod{2}
$$
Example:
$$
f(x) = x^2 + x, \ g(x) = x^2 + 1 \implies f(x) + g(x) = x + 1
$$

### 2.3.2 Product of Polynomials
- Multiply and reduce coefficients mod 2:
$$
f(x) \cdot g(x) = \left( \sum a_i x^i \right) \cdot \left( \sum b_j x^j \right) \pmod{2}
$$
Example:
$$
f(x) = x^2 + x, \ g(x) = x + 1 \implies f(x) \cdot g(x) = x^3 + x^2 + x^2 + x = x^3 + x
$$

### 2.3.3 Irreducible Polynomials
- A polynomial $f(x) \in \mathbb{F}_2[x]$ is **irreducible** if it cannot be factored into non-constant polynomials over $\mathbb{F}_2$.

Example: $x^2 + x + 1$ is irreducible in $\mathbb{F}_2$.

### 2.3.4 Reducible Polynomials in $\mathbb{F}_2$ and the Division Algorithm
- Division algorithm: For $f(x), g(x) \in \mathbb{F}_2[x]$, $\exists q(x), r(x)$ such that:
$$
f(x) = q(x) g(x) + r(x), \ \deg(r) < \deg(g)
$$
- Check reducibility by attempting to factorize.

## 2.4 First Application: The Field with 2 Bits $\mathbb{F}_4$
- $\mathbb{F}_4 = \{0, 1, \alpha, \alpha+1\}$ where $\alpha$ is a root of an irreducible polynomial in $\mathbb{F}_2[x]$, e.g., $x^2 + x + 1$.
- Addition and multiplication tables are defined mod $x^2 + x + 1$.

Example multiplication:
$$
\alpha \cdot (\alpha + 1) = \alpha^2 + \alpha = 1 + \alpha
$$

## 2.5 A Second Application: LFSR (Linear Feedback Shift Register)

### Definition
An **LFSR (Linear Feedback Shift Register)** is a mechanism for generating pseudo-random sequences of bits using a linear recurrence relation. It consists of:
1. A register with $n$ bits (initial state).
2. Feedback determined by a polynomial over $\mathbb{F}_2$.
3. Shift operations that update the register.

### Recurrence Relation
The next bit in the sequence is calculated as:
$$
x_{n+k} = c_{k-1} x_{n+k-1} + c_{k-2} x_{n+k-2} + \dots + c_0 x_n \pmod{2}
$$
where:
- $c_i \in \{0, 1\}$ are the coefficients of the feedback polynomial $f(x)$.
- $f(x) = x^k + c_{k-1}x^{k-1} + \dots + c_0$ is the feedback polynomial.

### Feedback Polynomial
- The **feedback polynomial** determines the taps (bits in the register involved in the feedback).
- Example: $f(x) = x^3 + x + 1$ defines a 3-bit LFSR with taps at the 3rd and 1st bits.

### Example of a 3-bit LFSR
1. Initial state: $(1, 0, 1)$
2. Feedback polynomial: $f(x) = x^3 + x + 1$
3. Steps:
   - Compute feedback: $x_3 = x_2 + x_0 \pmod{2}$
   - Shift left: $(x_2, x_1, x_0) \to (x_3, x_2, x_1)$

### Sequence Generation
Given an initial state $(1, 0, 1)$:
1. Feedback: $x_3 = x_2 + x_0 = 0 + 1 = 1$
2. New state: $(1, 1, 0)$
3. Repeat to produce: $(1, 0, 1), (1, 1, 0), (0, 1, 1), (1, 0, 1), \dots$

### Properties
- **Period**: Maximum length of the sequence is $2^n - 1$ for a register of $n$ bits (achieved when $f(x)$ is irreducible and primitive over $\mathbb{F}_2$).
- **Applications**:
  - Random number generation.
  - Stream ciphers in cryptography.
  - Error detection/correction (e.g., CRC).
