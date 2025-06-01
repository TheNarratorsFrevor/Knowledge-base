# Boolean Functions and Logic

## 3.1 Logic and Boolean Functions with $n = 2$
- A **Boolean function** with $n$ inputs maps $\{0, 1\}^n \to \{0, 1\}$.
- For $n = 2$, there are $2^{2^n} = 16$ possible functions.

### Truth Table for $n = 2$
| $x_1$ | $x_2$ | AND $(x_1 \land x_2)$ | OR $(x_1 \lor x_2)$ | XOR $(x_1 \oplus x_2)$ | NOT $x_1$ |
|-------|-------|-----------------------|---------------------|-----------------------|-----------|
| 0     | 0     | 0                     | 0                   | 0                     | 1         |
| 0     | 1     | 0                     | 1                   | 1                     | 1         |
| 1     | 0     | 0                     | 1                   | 1                     | 0         |
| 1     | 1     | 1                     | 1                   | 0                     | 0         |

### Common Boolean Operators
- **AND**: $x_1 \land x_2 = 1$ if both $x_1 = 1$ and $x_2 = 1$.
- **OR**: $x_1 \lor x_2 = 1$ if either $x_1 = 1$ or $x_2 = 1$.
- **XOR**: $x_1 \oplus x_2 = 1$ if $x_1 \neq x_2$.
- **NOT**: $\neg x_1 = 1$ if $x_1 = 0$.

## 3.2 The Implication $⇒$
- Logical implication $x_1 \implies x_2$ evaluates as:
$$
x_1 \implies x_2 = \neg x_1 \lor x_2
$$
- Truth Table:
| $x_1$ | $x_2$ | $x_1 \implies x_2$ |
|-------|-------|--------------------|
| 0     | 0     | 1                  |
| 0     | 1     | 1                  |
| 1     | 0     | 0                  |
| 1     | 1     | 1                  |

- Example: If $x_1$ is "It rains" and $x_2$ is "I use an umbrella", $x_1 \implies x_2$ means "If it rains, I use an umbrella."

## 3.3 The Double Implication $⇔$
- Logical equivalence $x_1 \iff x_2$ evaluates as:
$$
x_1 \iff x_2 = (x_1 \land x_2) \lor (\neg x_1 \land \neg x_2)
$$
- Truth Table:
| $x_1$ | $x_2$ | $x_1 \iff x_2$ |
|-------|-------|----------------|
| 0     | 0     | 1              |
| 0     | 1     | 0              |
| 1     | 0     | 0              |
| 1     | 1     | 1              |

- Example: If $x_1$ is "I study" and $x_2$ is "I pass", $x_1 \iff x_2$ means "I study if and only if I pass."

## 3.4 Boolean Functions and Information Technology
### Applications
1. **Digital Circuits**:
   - Boolean functions model logic gates (AND, OR, NOT, etc.).
   - Combinational logic circuits use these gates to perform arithmetic and decision-making.

2. **Data Compression**:
   - Boolean functions optimize encoding/decoding algorithms.
   - Example: Huffman coding uses bitwise operations.

3. **Error Detection and Correction**:
   - Boolean functions are used in CRC and parity checks.

4. **Search Algorithms**:
   - Boolean logic enables efficient querying in databases.

### Example: Simplifying a Boolean Function
Given: $f(x_1, x_2, x_3) = (x_1 \land x_2) \lor (\neg x_1 \land x_3)$

Using the **truth table** or **Boolean algebra**:
$$
f(x_1, x_2, x_3) = x_1x_2 + \neg x_1x_3
$$
This represents a multiplexer in digital logic.
