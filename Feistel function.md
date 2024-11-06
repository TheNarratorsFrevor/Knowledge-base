# The Feistel Function

## Overview

The Feistel function is a critical component in symmetric cryptographic algorithms, particularly in Feistel-based ciphers such as DES. It operates on one half of the data block and performs several operations including expansion, key mixing, substitution, and permutation. The function provides the basis for both diffusion and confusion, key elements of secure encryption.

## Structure of the Feistel Function $F$

The Feistel function $F$ takes in two inputs:
1. A half-block of data, usually 32 bits (denoted as $R$).
2. A subkey $K_i$ specific to the current encryption round.

Its output is a 32-bit transformed half-block that is combined with the other half-block in the Feistel round.

### Steps in the Feistel Function

1. **Expansion (E)**
   - The 32-bit half-block $R$ is expanded to 48 bits. This is achieved by duplicating and rearranging bits to introduce additional redundancy and spread the influence of each bit across the output.
   - Notationally:
     $$
     E(R) : \{0,1\}^{32} \rightarrow \{0,1\}^{48}
     $$

2. **XOR with Subkey**
   - The 48-bit expanded half-block $E(R)$ is XORed with the 48-bit subkey $K_i$ for round $i$.
   - This operation combines the data with the key, introducing confusion:
     $$
     E(R) \oplus K_i
     $$

3. **Substitution (S-Boxes)**
   - The XOR result is divided into eight 6-bit segments, each of which passes through a unique S-box. Each S-box maps a 6-bit input to a 4-bit output, implementing a non-linear transformation crucial for security.
   - Each S-box function $S_i$ is represented as:
     $$
     S_i : \{0,1\}^6 \rightarrow \{0,1\}^4
     $$
   - The eight 4-bit outputs are concatenated to form a 32-bit block.

4. **Permutation (P)**
   - The 32-bit output from the S-boxes undergoes a fixed permutation $P$. This operation reorders the bits, further diffusing the influence of each S-box output across the half-block.
   - Permutation function:
     $$
     P : \{0,1\}^{32} \rightarrow \{0,1\}^{32}
     $$

### Full Function

The entire Feistel function $F$ can be represented as:
$$
F(R, K_i) = P(S(E(R) \oplus K_i))
$$

## Role in Feistel Ciphers

In a Feistel cipher, the function $F$ is used in each round to transform one half of the block, with the output XORed with the other half. Specifically, given two halves $(L_i, R_i)$ of the block:
$$
L_{i+1} = R_i
$$
$$
R_{i+1} = L_i \oplus F(R_i, K_i)
$$

This structure ensures that each round diffuses the data and key influence throughout the block. Since $F$ is non-invertible, it also helps prevent straightforward attacks on the cipher.

## Security Properties

- **Confusion**: The XOR with $K_i$ and S-box substitution add confusion, making the relationship between key and ciphertext complex.
- **Diffusion**: Expansion and permutation steps spread out the influence of each input bit across the output, contributing to security.

The non-linearity and bit mixing introduced by $F$ are essential for the overall cryptographic strength of Feistel-based ciphers like DES.
