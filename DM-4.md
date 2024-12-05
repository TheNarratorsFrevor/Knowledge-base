# Clock Arithmetic

## 4.1 Operations on $\mathbb{Z}_n$
### Definition
Clock arithmetic, also known as **modular arithmetic**, is defined on the set $\mathbb{Z}_n = \{0, 1, 2, \dots, n-1\}$. Operations are performed modulo $n$.

### Modular Addition
$$
(a + b) \mod n
$$
Example: $(7 + 5) \mod 12 = 0$

### Modular Multiplication
$$
(a \cdot b) \mod n
$$
Example: $(3 \cdot 4) \mod 5 = 2$

### Modular Subtraction
$$
(a - b) \mod n
$$
Example: $(5 - 8) \mod 7 = 4$ (adjust for negative values by adding $n$)

### Modular Inverse
The modular inverse of $a$ modulo $n$ is a number $b$ such that:
$$
a \cdot b \equiv 1 \mod n
$$
It exists if and only if $\gcd(a, n) = 1$.

---

## 4.2 Graphs and Clocks
### Circular Representation
Clock arithmetic can be visualized as a circular graph, where:
- Each position represents an element of $\mathbb{Z}_n$.
- Moving clockwise corresponds to addition modulo $n$.

Example: $\mathbb{Z}_12$ forms a standard clock face.

---

## 4.3 Prime Numbers and Coprimality
### Prime Numbers
A number $p > 1$ is prime if its only divisors are $1$ and $p$.

### Coprimality
Two integers $a$ and $b$ are coprime if:
$$
\gcd(a, b) = 1
$$
Example: $\gcd(14, 15) = 1$ (14 and 15 are coprime).

---

## 4.4 Linear Equations
### Solving $ax \equiv b \mod n$
To solve the modular linear equation:
1. Check if $\gcd(a, n) \mid b$:
   - If not, no solution exists.
   - If yes, reduce the equation and solve using the inverse of $a \mod n$.
2. General solution:
$$
x = x_0 + k \cdot \frac{n}{\gcd(a, n)} \quad \text{for } k \in \mathbb{Z}
$$

---

## 4.5 Graphs and CRT (Chinese Remainder Theorem)
### Statement of CRT
If $n_1, n_2, \dots, n_k$ are pairwise coprime, then the system of congruences:
$$
x \equiv a_1 \mod n_1
$$
$$
x \equiv a_2 \mod n_2
$$
...
$$
x \equiv a_k \mod n_k
$$
has a unique solution modulo $N = n_1 \cdot n_2 \cdot \dots \cdot n_k$.

### Application
Solve using:
1. Compute $N = \prod n_i$.
2. For each $i$, calculate $M_i = \frac{N}{n_i}$.
3. Find the modular inverse of $M_i$ modulo $n_i$.
4. Compute:
$$
x = \sum_{i=1}^k a_i M_i M_i^{-1} \mod N
$$

---

## 4.6 Big Prime Numbers and Powers in $\mathbb{Z}_n$
### Fermat's Little Theorem
If $p$ is a prime and $a$ is not divisible by $p$, then:
$$
a^{p-1} \equiv 1 \mod p
$$

### Modular Exponentiation
Efficient computation of $a^b \mod n$ is performed using **exponentiation by squaring**.

---

## 4.7 Primitive Elements in $\mathbb{Z}_p$
### Definition
A number $g \in \mathbb{Z}_p$ is a **primitive root** modulo $p$ if:
$$
\{g^0, g^1, g^2, \dots, g^{p-2}\} \mod p = \mathbb{Z}_p^*
$$
Example: For $p = 7$, $g = 3$ is a primitive root.

---

## 4.8 An Application to Cryptography: The Key-Exchange
### Diffie-Hellman Key Exchange
1. Alice and Bob agree on a prime $p$ and a primitive root $g$.
2. Alice selects a private key $a$ and sends $A = g^a \mod p$ to Bob.
3. Bob selects a private key $b$ and sends $B = g^b \mod p$ to Alice.
4. Both compute the shared key:
   - Alice: $K = B^a \mod p$
   - Bob: $K = A^b \mod p$
5. Result: $K = g^{ab} \mod p$ is the shared secret.

### Example
- Public: $p = 23$, $g = 5$
- Alice: $a = 6$, sends $A = 5^6 \mod 23 = 8$
- Bob: $b = 15$, sends $B = 5^{15} \mod 23 = 19$
- Shared key: $K = 19^6 \mod 23 = 2$
