# 📘 ODEs Cheatsheet

## 0. Definitions

- **ODE**: an equation involving a function and its derivatives:  
  $$F(x, y, y', y'', ..., y^{(n)}) = 0$$  
- **Order**: highest derivative in the equation  
- **Degree**: exponent of the highest derivative (assuming rational form)  
- **Linear**: linear in $y$, $y'$, ..., $y^{(n)}$  
- **Homogeneous (linear)**: RHS = 0  
- **Nonhomogeneous**: RHS ≠ 0

---

## 1. First-Order ODEs

### a. Separable

$$\frac{dy}{dx} = f(x)g(y) \Rightarrow \int \frac{1}{g(y)}\,dy = \int f(x)\,dx$$

---

### b. Linear

$$\frac{dy}{dx} + P(x)y = Q(x)$$  
Integrating factor:  
$$\mu(x) = Ce^{\int P(x)\,dx}$$  
Solution:  
$$y = \frac{1}{\mu(x)} \int \mu(x)Q(x)\,dx$$

---

### c. Exact

$$M(x,y)dx + N(x,y)dy = 0$$  
Exact if:  
$$\frac{\partial M}{\partial y} = \frac{\partial N}{\partial x}$$  
Then:  
$$\frac{dF}{dx} = M,\quad \frac{dF}{dy} = N \Rightarrow F(x,y) = C$$

---

### d. Integrating Factor (for non-exact)

Find $\mu(x)$ or $\mu(y)$ s.t.  
$$\mu M dx + \mu N dy$$  
becomes exact

---

### e. Bernoulli

$$\frac{dy}{dx} + P(x)y = Q(x)y^n$$  
Divide by $y^n$, set $v = y^{1-n}$, turns into linear

---

### f. Homogeneous (not linear)

$$\frac{dy}{dx} = F\left( \frac{y}{x} \right)$$  
Substitute $v = y/x \Rightarrow y = vx$

---

### g. Clairaut's Equation

$$y = x \frac{dy}{dx} + f\left( \frac{dy}{dx} \right)$$  
General sol: $y = xp + f(p)$  
Singular sol: eliminate $p$

---

## 2. Second-Order Linear ODEs

### a. General Form

$$a(x)y'' + b(x)y' + c(x)y = f(x)$$  
- Homogeneous: $f(x) = 0$  
- Constant coeff: $a,b,c$ constants

---

### b. Homogeneous w/ constant coefficients

$$ay'' + by' + cy = 0$$  
Characteristic equation:  
$$ar^2 + br + c = 0$$

Solutions:
- Distinct real roots $r_1, r_2$:  
  $$y = C_1 e^{r_1 x} + C_2 e^{r_2 x}$$
- Repeated root $r$:  
  $$y = (C_1 + C_2 x)e^{rx}$$
- Complex roots $r = \alpha \pm i\beta$:  
  $$y = e^{\alpha x}(C_1 \cos(\beta x) + C_2 \sin(\beta x))$$

---

### c. Nonhomogeneous: Method of Undetermined Coefficients

Try $y_p$ form similar to $f(x)$:
- Poly $\Rightarrow$ try poly
- $\sin$, $\cos$ $\Rightarrow$ try trig
- $e^{ax}$ $\Rightarrow$ try exponential
- multiply by $x^n$ if overlap w/ homogeneous solution

---

### d. Variation of Parameters

Given:
$$y'' + p(x)y' + q(x)y = f(x)$$  
Let $y = u_1 y_1 + u_2 y_2$, where $y_1, y_2$ are homogeneous solutions  
Then:
$$
\begin{cases}
u_1' y_1 + u_2' y_2 = 0 \\
u_1' y_1' + u_2' y_2' = f(x)
\end{cases}
$$  
Solve for $u_1', u_2'$, then integrate

---

## 3. Systems of ODEs

### a. First-Order Linear Systems

$$\vec{y}' = A \vec{y}$$  
- Diagonalizable: $\vec{y} = P e^{Dt} \vec{c}$
- Eigenvalue method: $\vec{y}(t) = c_1 \vec{v}_1 e^{\lambda_1 t} + c_2 \vec{v}_2 e^{\lambda_2 t}$

---

### b. Nonlinear Systems

Linearize near equilibrium point $(x_0, y_0)$:
$$
\begin{bmatrix}
\dot{x} \\
\dot{y}
\end{bmatrix}
= 
J(x_0, y_0)
\begin{bmatrix}
x - x_0 \\
y - y_0
\end{bmatrix}
$$  
where $J$ is Jacobian matrix

---

## 4. Laplace Transforms

$$\mathcal{L}\{f(t)\} = \int_0^\infty e^{-st}f(t)dt$$

### a. Common Transforms

- $\mathcal{L}\{1\} = \frac{1}{s}$  
- $\mathcal{L}\{t^n\} = \frac{n!}{s^{n+1}}$  
- $\mathcal{L}\{e^{at}\} = \frac{1}{s-a}$  
- $\mathcal{L}\{\sin(at)\} = \frac{a}{s^2 + a^2}$  
- $\mathcal{L}\{\cos(at)\} = \frac{s}{s^2 + a^2}$

### b. Properties

- Linearity  
- Shifting: $\mathcal{L}\{e^{at}f(t)\} = F(s - a)$  
- Derivative: $\mathcal{L}\{f'\} = sF(s) - f(0)$

---

### c. Solving ODEs

1. Take Laplace of both sides  
2. Plug in initial conditions  
3. Solve algebraically for $Y(s)$  
4. Inverse Laplace

---

## 5. Existence & Uniqueness

### Picard-Lindelöf Theorem

For $\frac{dy}{dx} = f(x, y)$, if $f$ and $\partial f/\partial y$ are continuous near $(x_0, y_0)$, there exists a unique solution near $x_0$

---

## 6. Stability (Linear)

For $y'' + py' + qy = 0$:
- $\text{Re}(\lambda) < 0$ → stable
- $\text{Re}(\lambda) > 0$ → unstable
- $\text{Re}(\lambda) = 0$ → marginal

---

## 7. Numerical Methods

### a. Euler’s Method

$$y_{n+1} = y_n + h f(x_n, y_n)$$

### b. Improved Euler (Heun)

$$
\begin{aligned}
k_1 &= f(x_n, y_n) \\
k_2 &= f(x_n + h, y_n + h k_1) \\
y_{n+1} &= y_n + \frac{h}{2}(k_1 + k_2)
\end{aligned}
$$

### c. Runge-Kutta 4th Order

$$
\begin{aligned}
k_1 &= f(x_n, y_n) \\
k_2 &= f(x_n + \frac{h}{2}, y_n + \frac{h}{2}k_1) \\
k_3 &= f(x_n + \frac{h}{2}, y_n + \frac{h}{2}k_2) \\
k_4 &= f(x_n + h, y_n + hk_3) \\
y_{n+1} &= y_n + \frac{h}{6}(k_1 + 2k_2 + 2k_3 + k_4)
\end{aligned}
$$

---

## 8. Phase Plane & Qualitative Analysis

- Equilibrium points: $\dot{x} = \dot{y} = 0$  
- Linearize via Jacobian  
- Type from eigenvalues:
  - real, same sign → node (stable/unstable)
  - real, opposite signs → saddle
  - complex w/ nonzero real part → spiral
  - pure imaginary → center

---

## 9. Special Functions

- Bessel: $x^2 y'' + x y' + (x^2 - n^2)y = 0$  
- Legendre: $(1 - x^2)y'' - 2x y' + n(n+1)y = 0$  
- Airy: $y'' - xy = 0$  
- Error function (from heat equation)

---

## 10. PDE Reduction to ODEs

- Separation of variables → reduces PDE to ODEs
- Fourier series for spatial component
- Transforms (Laplace, Fourier) help too

---

## 11. Green's Function

Used for linear nonhomogeneous problems:  
$$Ly = f(x) \Rightarrow y(x) = \int G(x, s)f(s)\,ds$$

---
