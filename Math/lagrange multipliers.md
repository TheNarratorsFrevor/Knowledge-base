# Lagrange multipliers

Lagrange multipliers are a method for finding the extrema (maxima or minima) of a function subject to one or more constraints. instead of solving a constrained optimization problem directly, the method transforms it into a system of equations using auxiliary variables (the Lagrange multipliers).

## intuition

say you want to optimize $f(x, y)$ subject to the constraint $g(x, y) = 0$. geometrically, you're looking for points on the constraint surface where $f$ is stationary — i.e., where its gradient $\nabla f$ is ***parallel*** to the gradient of the constraint $\nabla g$. this happens when:

$$
\nabla f(x, y) = \lambda \nabla g(x, y)
$$

for some scalar $\lambda$, the Lagrange multiplier.

## basic form

given:
- objective function: $f(x_1, x_2, \dots, x_n)$
- constraint: $g(x_1, x_2, \dots, x_n) = 0$

define the lagrangian:
$$
\mathcal{L}(x_1, \dots, x_n, \lambda) = f(x_1, \dots, x_n) - \lambda g(x_1, \dots, x_n)
$$

then solve the system:
$$
\nabla_{x_i} \mathcal{L} = 0 \quad \text{for all } i \\
\frac{\partial \mathcal{L}}{\partial \lambda} = -g(x_1, \dots, x_n) = 0
$$

## multiple constraints

with $m$ constraints $g_1, \dots, g_m$:

$$
\mathcal{L}(x, \lambda_1, \dots, \lambda_m) = f(x) - \sum_{j=1}^m \lambda_j g_j(x)
$$

the condition becomes:
$$
\nabla f = \sum_{j=1}^m \lambda_j \nabla g_j
$$

plus the constraint equations $g_j(x) = 0$.

## advanced stuff

- **inequality constraints** → use [[karush-kuhn-tucker conditions]]
- **geometric meaning**: Lagrange multipliers measure how much the objective function increases per unit increase in the constraint value — they're *shadow prices* in econ speak.
- **degenerate cases**: if $\nabla g = 0$ at a point, the method can fail — check constraint qualifications.
- **second order conditions**: to classify critical points, use [[bordered hessian]] or evaluate second derivatives along constraint surface.

## use cases

- [[constrained Optimization]]
- economics (maximizing utility/cost with budget constraints)
- physics (minimizing energy under conservation laws)
- ml (regularization, especially in dual formulations like [[svm]])

## cheatsheet

```text
given:
  f(x), g(x) = 0

1. define L(x, λ) = f(x) - λ g(x)
2. solve ∇L = 0:
     ∇f(x) = λ ∇g(x)
     g(x) = 0

with multiple g_i(x):
  L(x, λ₁...λ_m) = f(x) - Σ λᵢ gᵢ(x)
  ∇f = Σ λᵢ ∇gᵢ
  gᵢ(x) = 0 ∀i

lagrange multiplier λ tells how sensitive f* is to constraint change:
  ∂f*/∂c ≈ λ
```
## links

- [[constrained Optimization]]
    
- [[karush-kuhn-tucker conditions]]
    
- [[gradient]]
    
- [[svm]]
    
- [[euler-lagrange equations]]
    
- [[dual problem]]