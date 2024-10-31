# Conservation Laws in Physics

Conservation laws are core ideas in physics that describe how certain quantities, like energy and momentum, stay the same in a system over time (as long as nothing from the outside messes with it!). In this document, we’ll go over the main conservation laws, some equations, and examples of how they work in real-world and theoretical situations.

## Table of Contents
1. [Introduction](#introduction)
2. [Conservation of Energy](#conservation-of-energy)
3. [Conservation of Momentum](#conservation-of-momentum)
4. [Conservation of Angular Momentum](#conservation-of-angular-momentum)
5. [Conservation of Charge](#conservation-of-charge)
6. [Symmetries and Noether's Theorem](#symmetries-and-noethers-theorem)
7. [Applications in Modern Physics](#applications-in-modern-physics)

---

## Introduction

Conservation laws are principles that help us understand how the universe behaves. In an isolated system (think of it like a closed box where nothing from outside can get in or out), certain quantities don’t change over time. These conserved quantities make it easier to understand and solve complicated problems.

## Conservation of Energy

The conservation of energy means that in a closed system, the total energy stays the same, even if energy shifts between different forms (like from potential to kinetic energy).

### Mathematical Formulation

If $E_{\text{total}}$ is the total energy in a system, we can say:

$$
\frac{dE_{\text{total}}}{dt} = 0
$$

This just means the rate of change in energy is zero. In many cases, total energy can be split into **kinetic** (movement) energy and **potential** (stored) energy:

$$
E_{\text{total}} = K + U
$$

where $K$ is kinetic energy, and $U$ is potential energy.

## Conservation of Momentum

Momentum conservation tells us that, without any outside forces, the total momentum of a system doesn’t change over time. This is why in collisions (like in a game of pool), the total momentum before and after the collision remains the same.

### Mathematical Formulation

For particles with masses $m_i$ and velocities $v_i$:

$$
\sum_{i} m_i v_i = \text{constant}
$$

In other words, the sum of all particle momenta stays constant in a closed system.

## Conservation of Angular Momentum

Angular momentum is about rotating objects and how they keep spinning unless something stops them. It’s why a spinning figure skater can pull in their arms to spin faster!

### Mathematical Formulation

If $\vec{L}$ is angular momentum, we can write:

$$
\frac{d\vec{L}}{dt} = 0
$$

For something spinning, $\vec{L} = I \vec{\omega}$, where $I$ is the inertia (how much it resists spinning) and $\vec{\omega}$ is the angular speed.

## Conservation of Charge

Charge conservation is a principle that the total electric charge in an isolated system remains constant. It’s central to electromagnetism and explains why charges don’t just appear or disappear.

### Mathematical Formulation

If $Q_{\text{total}}$ is the total electric charge:

$$
\frac{dQ_{\text{total}}}{dt} = 0
$$

Charge conservation helps establish foundational laws like **Gauss’s Law** and **Maxwell’s Equations**.

## Symmetries and Noether's Theorem

One of the most interesting parts of conservation laws is that they’re related to symmetries in nature. Noether's theorem shows that every symmetry in a system corresponds to a conservation law.

### Examples

- **Time Translation Symmetry** → Conservation of Energy
- **Space Translation Symmetry** → Conservation of Momentum
- **Rotational Symmetry** → Conservation of Angular Momentum

### Mathematical Formulation

For a system with Lagrangian $\mathcal{L}$, a continuous symmetry means:

$$
\frac{d}{dt} \left( \frac{\partial \mathcal{L}}{\partial \dot{q}} \right) = 0
$$

where $q$ is a generalized coordinate (like position, for instance).

## Applications in Modern Physics

### Quantum Mechanics

In quantum mechanics, conservation laws relate to operators that don’t change the total energy, called Hamiltonians. For example, angular momentum conservation is due to the angular momentum operator:

$$
[H, L_z] = 0
$$

where $H$ is the total energy (or Hamiltonian) operator, and $L_z$ is angular momentum in the z-axis.

---

## Summary

In short, conservation laws are like nature’s way of keeping things balanced. They’re found in nearly every area of physics, from objects in motion to charges and even at the quantum level, helping us understand how systems behave across scales.
