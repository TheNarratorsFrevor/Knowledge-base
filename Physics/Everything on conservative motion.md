# Everything on Conservative Motion

Conservative forces, like gravity and spring forces, play a huge role in physics because they allow energy to be stored as potential energy and converted back without loss. In conservative systems, total mechanical energy remains constant, giving us tools to solve for motion, speed, and position in various scenarios. Let’s explore conservative motion, the $E = U + W$ relationship, and apply these ideas through examples.

## Table of Contents
1. [What is Conservative Motion?](#what-is-conservative-motion)
2. [Understanding Potential Energy](#understanding-potential-energy)
3. [The $E = U + K$ Relationship](#the-e--u--w-relationship)
4. [Conservative Forces and Work](#conservative-forces-and-work)
5. [Examples and Problems](#examples-and-problems)
6. [Applications in Physics and Engineering](#applications-in-physics-and-engineering)

---

## What is Conservative Motion?

Conservative motion describes systems where the **total mechanical energy** is conserved. When forces acting on a system are conservative, the energy can switch between **kinetic** and **potential** forms, but the total energy remains constant. Examples include:

- **[[Gravity]]**: In a gravitational field, objects have potential energy that converts to kinetic energy as they fall.
- **[[Springs & Elasticity]]**: A stretched or compressed spring stores potential energy that converts to kinetic energy upon release.

## Understanding Potential Energy

Potential energy, $U$, is the stored energy due to an object’s position in a force field (like gravitational or elastic). For any conservative force field, we can define a **potential energy function** $U(\vec{r})$ based on the position vector $\vec{r}$.

### Examples of Potential Energy

1. **Gravitational Potential Energy**: Near Earth’s surface, gravitational potential energy $U$ is given by:
   
   $$
   U = mgh
   $$
   
   where $m$ is mass, $g$ is gravitational acceleration, and $h$ is the height above a reference level.

2. **Elastic (Spring) Potential Energy**: For a spring displaced by $x$ from its rest position:
   
   $$
   U = \frac{1}{2}kx^2
   $$

   where $k$ is the spring constant.

3. **Electrostatic Potential Energy**: For a charge $q$ in an electric field $E$:
   
   $$
   U = qV
   $$
   
   where $V$ is the electric potential.

## The $E = U + K$ Relationship

The principle of **conservation of mechanical energy** can be represented as:

$$
E = K + U
$$

where:
- $E$ is the total mechanical energy.
- $K$ is the kinetic energy, given by $K = \frac{1}{2}mv^2$.
- $U$ is the potential energy.

In the presence of external work $W_{\text{ext}}$, the total energy changes, giving us:

$$
E_{\text{final}} = E_{\text{initial}} + W_{\text{ext}}
$$

For conservative forces where $W_{\text{ext}} = 0$, mechanical energy remains constant, so:

$$
E_{\text{initial}} = E_{\text{final}}
$$

## Conservative Forces and Work

**Conservative forces** are unique because the work done by these forces is path-independent — it depends only on the initial and final positions, not on the path taken. This property allows us to define potential energy functions for these forces.

### Work Done by Conservative Forces

The work done by a conservative force $\vec{F}$ over a displacement $\vec{dr}$ can be written as:

$$
W = -\int_{a}^{b} \vec{F} \cdot d\vec{r}
$$

For conservative forces, this work is equal to the **change in potential energy**:

$$
W = U(a) - U(b)
$$

### Gradient and Conservative Fields

For a force field to be conservative, it must be the **gradient of a potential energy function**:

$$
\vec{F} = -\nabla U
$$

where $\nabla U$ represents the spatial rate of change in potential energy. This equation means that conservative forces always act in the direction of decreasing potential energy.

## Examples and Problems

Let’s apply these principles with some examples that illustrate how the $E = U + K$ relation works.

### Example 1: Pendulum Motion

Consider a pendulum of mass $m$ at height $h$ swinging to a lower point. At the highest point, the energy is entirely potential:

$$
E = U = mgh
$$

As it swings, potential energy converts to kinetic energy, and at the lowest point, $U = 0$, so:

$$
E = K = \frac{1}{2}mv^2
$$

Solving for $v$ gives:

$$
v = \sqrt{2gh}
$$

### Example 2: Mass on a Spring

A mass $m$ attached to a spring with spring constant $k$ is displaced by $x$ and released. Initially, the potential energy is:

$$
U = \frac{1}{2}kx^2
$$

When the mass passes through the equilibrium position, all this potential energy has converted to kinetic energy:

$$
K = \frac{1}{2}mv^2 = \frac{1}{2}kx^2
$$

Solving for $v$:

$$
v = x\sqrt{\frac{k}{m}}
$$

### Example 3: Projectile Motion with Gravity

For an object of mass $m$ launched vertically with initial speed $v_0$, the total energy $E$ at launch is:

$$
E = \frac{1}{2}mv_0^2 + mgh_0
$$

As it rises, kinetic energy converts to potential energy. At maximum height, kinetic energy is zero, so:

$$
E = U = mgh_{\text{max}}
$$

Solving for $h_{\text{max}}$:

$$
h_{\text{max}} = \frac{v_0^2}{2g} + h_0
$$
