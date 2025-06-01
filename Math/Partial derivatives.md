# 📘 Partial Derivatives Cheatsheet

## 0. Definitions

- **Partial derivative**: derivative w.r.t. one variable while holding others constant  
  $$
  \frac{\partial f}{\partial x},\quad \frac{\partial f}{\partial y},\quad \text{etc.}
  $$
- **Order**:
  - First: $\frac{\partial f}{\partial x}$
  - Second: $\frac{\partial^2 f}{\partial x^2}$, $\frac{\partial^2 f}{\partial x \partial y}$, etc.
- **Mixed derivatives**:
  $$
  \frac{\partial^2 f}{\partial x \partial y} = \frac{\partial^2 f}{\partial y \partial x} \quad \text{(if } f \in C^2)
  $$

---

## 1. Gradient

$$
\nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z}, \dots \right)
$$  
→ points in direction of steepest increase

---

## 2. Chain Rule

### a. Single-parameter case (e.g. $x(t), y(t)$):

$$
\frac{df}{dt} = \frac{\partial f}{\partial x}\frac{dx}{dt} + \frac{\partial f}{\partial y}\frac{dy}{dt}
$$

### b. Multivariable chain rule (matrix form):

If $\vec{x} = \vec{x}(u,v)$ and $f = f(\vec{x})$, then:  
$$
\frac{\partial f}{\partial u} = \nabla f \cdot \frac{\partial \vec{x}}{\partial u}
$$

---

## 3. Directional Derivatives

$$
D_{\vec{v}} f = \nabla f \cdot \hat{v}
$$  
rate of change of $f$ in direction $\vec{v}$

---

## 4. Hessian Matrix

Matrix of second partial derivatives:
$$
H_f = \begin{bmatrix}
\frac{\partial^2 f}{\partial x^2} & \frac{\partial^2 f}{\partial x \partial y} \\
\frac{\partial^2 f}{\partial y \partial x} & \frac{\partial^2 f}{\partial y^2}
\end{bmatrix}
$$  
Used for concavity and optimization

---

## 5. Taylor Expansion (Multivariable)

$$
f(x + h, y + k) \approx f(x, y) + f_x h + f_y k + \frac{1}{2}\left( f_{xx} h^2 + 2f_{xy} hk + f_{yy} k^2 \right)
$$

---

## 6. Critical Points & Optimization

- Critical points: where $\nabla f = 0$
- Use **second derivative test**:

Let $D = f_{xx}f_{yy} - (f_{xy})^2$
- if $D > 0$ and $f_{xx} > 0$ → local min
- if $D > 0$ and $f_{xx} < 0$ → local max
- if $D < 0$ → saddle
- if $D = 0$ → inconclusive

---

## 7. Lagrange Multipliers

Constrained extrema of $f(x,y)$ subject to $g(x,y)=c$:

$$
\nabla f = \lambda \nabla g
$$

System:
$$
\begin{cases}
\frac{\partial f}{\partial x} = \lambda \frac{\partial g}{\partial x} \\
\frac{\partial f}{\partial y} = \lambda \frac{\partial g}{\partial y} \\
g(x,y) = c
\end{cases}
$$

---

## 8. Jacobian Matrix

For vector function $\vec{F} = (f_1, f_2, \dots, f_n)$:

$$
J = \begin{bmatrix}
\frac{\partial f_1}{\partial x_1} & \cdots & \frac{\partial f_1}{\partial x_n} \\
\vdots & \ddots & \vdots \\
\frac{\partial f_m}{\partial x_1} & \cdots & \frac{\partial f_m}{\partial x_n}
\end{bmatrix}
$$

Used in coordinate transforms and change of variables

---

## 9. Implicit Function Theorem (sketch)

Given $F(x,y) = 0$ with $\frac{\partial F}{\partial y} \ne 0$ near a point,  
you can locally solve $y = y(x)$

---

## 10. Coordinate Changes

### a. Polar

$$
x = r\cos\theta,\quad y = r\sin\theta \Rightarrow \frac{\partial f}{\partial x} = \frac{\partial f}{\partial r} \frac{\partial r}{\partial x} + \frac{\partial f}{\partial \theta} \frac{\partial \theta}{\partial x}
$$

### b. Jacobian determinant

For $dx\,dy \to du\,dv$,  
$$
dx\,dy = \left| \frac{\partial(x,y)}{\partial(u,v)} \right| du\,dv
$$

---

## 11. Clairaut’s Theorem

If $f \in C^2$, then mixed partials are equal:  
$$
\frac{\partial^2 f}{\partial x \partial y} = \frac{\partial^2 f}{\partial y \partial x}
$$

---

## 12. Surface Tangents & Normals

- Surface $f(x,y,z) = c$:  
  Gradient $\nabla f$ is normal vector
- Tangent plane at point $(x_0,y_0,z_0)$:  
  $$
  f_x(x_0,y_0,z_0)(x - x_0) + f_y(x_0,y_0,z_0)(y - y_0) + f_z(x_0,y_0,z_0)(z - z_0) = 0
  $$

---

## 13. Laplacian

Scalar operator:
$$
\Delta f = \nabla \cdot \nabla f = \frac{\partial^2 f}{\partial x^2} + \frac{\partial^2 f}{\partial y^2} + \frac{\partial^2 f}{\partial z^2}
$$  
Shows up in PDEs like heat & wave equations

---

## 14. Applications

- **Thermo**: heat equation involves $\frac{\partial u}{\partial t}$ and $\Delta u$
- **Econ**: marginal rates via partials
- **Physics**: gradients, flux, divergence all use partials
- **ML**: gradient descent uses $\nabla f$

---
