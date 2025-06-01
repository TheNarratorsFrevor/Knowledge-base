## constrained optimization

finding the critical points (maxima and minima) of a function $f(x)$ constrained by the domain $d_{f}$.

let's aim at maximizing the function $f(x,y) = x^{2}y$ on the set $x^{2}+ y^{2}=1$.

first, we compute the gradients:  
$$
\nabla f = (f_{x}, f_{y}) = (2xy, x^{2})
$$
$$
\nabla g = (g_x, g_y) = (2x, 2y)
$$

we impose the [[lagrange multipliers]] condition:  
$$
\nabla f = \lambda \nabla g
$$
which gives the system of equations:  
$$
2xy = \lambda 2x
$$
$$
x^2 = \lambda 2y
$$
$$
x^2 + y^2 = 1
$$

solving this system gives the critical points. we then use the weierstrass theorem, which guarantees that a continuous function on a compact set attains its maximum and minimum. in this case, the set $x^2 + y^2 = 1$ is compact, so we only need to check the values of $f(x, y)$ at the critical points to determine extrema.

### generalization

#### the constraint is expressed in implicit form

$$
g(x,y) = g_{0}
$$

if $f$ and $g$ are continuously differentiable ($c^1$ class functions), and $g$ defines a constraint surface, we apply the method of lagrange multipliers.

we define the lagrangian function:

$$
\mathcal{L}(x,y,\lambda) = f(x,y) - \lambda (g(x,y) - g_{0})
$$

to find extrema, we solve the system:

$$
\frac{\partial \mathcal{L}}{\partial x} = 0, \quad \frac{\partial \mathcal{L}}{\partial y} = 0, \quad \frac{\partial \mathcal{L}}{\partial \lambda} = 0
$$

this is equivalent to the gradient parallelism condition $\nabla f = \lambda \nabla g$.

#### the constraint is in parametric form

if the constraint is given parametrically as:

$$
x = x(t), \quad y = y(t)
$$

then we substitute these expressions directly into $f(x,y)$ to obtain a single-variable function:

$$
h(t) = f(x(t), y(t))
$$

the extrema of $h(t)$ are found by differentiating and solving:

$$
\frac{d}{dt} f(x(t), y(t)) = 0
$$

and checking second-order conditions if necessary.

#### constraint is given in cartesian form

if the constraint is explicitly given as $y = g(x)$, we substitute this directly into $f(x, y)$ to get a single-variable function:

$$
h(x) = f(x, g(x))
$$

then we differentiate:

$$
\frac{d}{dx} h(x) = \frac{\partial f}{\partial x} + \frac{\partial f}{\partial y} \cdot g'(x)
$$

setting this derivative to zero gives critical points:

$$
\frac{\partial f}{\partial x} + \frac{\partial f}{\partial y} \cdot g'(x) = 0
$$

to determine if these points are maxima, minima, or saddle points, we examine the second derivative:

$$
\frac{d^2}{dx^2} h(x) = \frac{\partial^2 f}{\partial x^2} + 2 \frac{\partial^2 f}{\partial x \partial y} g'(x) + \frac{\partial^2 f}{\partial y^2} (g'(x))^2 + \frac{\partial f}{\partial y} g''(x)
$$

if this second derivative is positive, we have a local minimum; if negative, a local maximum. if zero, further analysis is needed.


## Example one

Function: $f(x,y) = x - y$
Constraint: $x^{2}+ y^{2} = 2$

we seek to determine the extrema of $f(x, y)$ subject to the constraint.

---

### method 1: lagrange multipliers

#### theorem (lagrange multipliers)
*let $f, g: \mathbb{R}^n \to \mathbb{R}$ be continuously differentiable functions. if $f$ attains a local extremum at $(x_0, y_0, \dots)$ subject to the constraint $g(x, y, \dots) = g_0$, and if $\nabla g(x_0, y_0, \dots) \neq 0$, then there exists a scalar $\lambda$ such that:*
$$
\nabla f(x_0, y_0, \dots) = \lambda \nabla g(x_0, y_0, \dots).
$$

#### applying the theorem
define the constraint function:
$$
g(x, y) = x^2 + y^2 - 2.
$$
compute the gradients:
$$
\nabla f = (1, -1), \quad \nabla g = (2x, 2y).
$$
imposing the lagrange condition:
$$
\nabla f = \lambda \nabla g
$$
yields the system:
$$
1 = \lambda 2x,
$$
$$
-1 = \lambda 2y,
$$
$$
x^2 + y^2 = 2.
$$

#### solving for $\lambda$
from the first equation:
$$
\lambda = \frac{1}{2x}.
$$
from the second equation:
$$
\lambda = -\frac{1}{2y}.
$$
equating both expressions:
$$
\frac{1}{2x} = -\frac{1}{2y}.
$$
multiplying by $2xy$:
$$
y = -x.
$$

#### solving for critical points
substituting into the constraint:
$$
x^2 + (-x)^2 = 2,
$$
$$
2x^2 = 2,
$$
$$
x^2 = 1 \Rightarrow x = \pm 1.
$$
thus, the critical points are $(1, -1)$ and $(-1,1)$.

#### evaluating $f(x,y)$ at critical points
$$
f(1, -1) = 1 - (-1) = 2,
$$
$$
f(-1, 1) = -1 - 1 = -2.
$$

#### theorem (weierstrass extreme value theorem)
*a continuous function on a compact set attains both a maximum and a minimum value.*

since $x^2 + y^2 = 2$ is a compact set, the obtained critical points correspond to the global maximum and minimum.

**conclusion:**  
the maximum value is $2$ at $(1,-1)$, and the minimum value is $-2$ at $(-1,1)$.

---

### method 2: direct substitution

#### theorem (implicit constraint reduction)
*if a constraint is given in the form $g(x,y) = 0$ and is solvable for $y$ in terms of $x$, then the optimization problem $\max f(x, y)$ can be rewritten as $\max h(x)$ where $h(x) = f(x, g(x))$, reducing the dimension.*

the constraint is:
$$
x^2 + y^2 = 2.
$$
solving for $y$:
$$
y = \pm \sqrt{2 - x^2}.
$$
substituting into $f(x,y)$:
$$
h(x) = x - \sqrt{2 - x^2}.
$$

#### computing critical points
differentiate:
$$
\frac{d}{dx} h(x) = 1 - \frac{-x}{\sqrt{2 - x^2}} = 1 + \frac{x}{\sqrt{2 - x^2}}.
$$
setting to zero:
$$
1 + \frac{x}{\sqrt{2 - x^2}} = 0.
$$
solving:
$$
\frac{x}{\sqrt{2 - x^2}} = -1.
$$
squaring both sides:
$$
x^2 = 2 - x^2.
$$
solving for $x$:
$$
2x^2 = 2,
$$
$$
x^2 = 1 \Rightarrow x = \pm 1.
$$
substituting for $y$, we recover the points $(1,-1)$ and $(-1,1)$.

thus, both methods confirm that the extrema are:
- **maximum**: $f(1,-1) = 2$
- **minimum**: $f(-1,1) = -2$

--- 
## Example two

**function:**  
$$
f(x,y) = x + y
$$  
**constraint (parametric form):**  
$$
x = \cos t, \quad y = \sin t, \quad t \in [0, 2\pi].
$$

we seek the extrema of $f(x,y)$ given this parameterization.

---

### method: parametric optimization

#### theorem (parametric extrema)
*if a function $f(x,y)$ is constrained by parametric equations $x = x(t)$, $y = y(t)$, then we define the single-variable function:*
$$
h(t) = f(x(t), y(t)).
$$
*critical points occur where*example two  
$$
\frac{d}{dt} h(t) = 0.
$$

#### applying the theorem
substituting the parameterization into $f(x,y)$:
$$
h(t) = \cos t + \sin t.
$$
differentiate:
$$
\frac{d}{dt} h(t) = -\sin t + \cos t.
$$
set to zero:
$$
\cos t - \sin t = 0.
$$
solving:
$$
\cos t = \sin t.
$$
dividing by $\cos t$ (valid where $\cos t \neq 0$):
$$
1 = \tan t.
$$
so:
$$
t = \frac{\pi}{4} + k\pi, \quad k \in \mathbb{Z}.
$$
restricting to $t \in [0,2\pi]$, we get:
$$
t = \frac{\pi}{4}, \quad t = \frac{5\pi}{4}.
$$

#### computing critical values
evaluating at $t = \frac{\pi}{4}$:
$$
x = \cos \frac{\pi}{4} = \frac{\sqrt{2}}{2}, \quad y = \sin \frac{\pi}{4} = \frac{\sqrt{2}}{2}.
$$
$$
f\left( \frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2} \right) = \sqrt{2}.
$$

evaluating at $t = \frac{5\pi}{4}$:
$$
x = \cos \frac{5\pi}{4} = -\frac{\sqrt{2}}{2}, \quad y = \sin \frac{5\pi}{4} = -\frac{\sqrt{2}}{2}.
$$
$$
f\left( -\frac{\sqrt{2}}{2}, -\frac{\sqrt{2}}{2} \right) = -\sqrt{2}.
$$

#### theorem (weierstrass extreme value theorem)
*a continuous function on a compact set attains both a maximum and a minimum.*

since the unit circle is compact, the obtained values must be the global extrema.

---

### conclusion
- **maximum value**: $\sqrt{2}$ at $\left(\frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2} \right)$.
- **minimum value**: $-\sqrt{2}$ at $\left(-\frac{\sqrt{2}}{2}, -\frac{\sqrt{2}}{2} \right)$.

---


## Example three

### problem statement

**function:**  
$$
f(x,y) = e^x y.
$$  
**constraint (explicit form):**  
$$
y = x - 1.
$$

we seek the extrema of $f(x,y)$ under this constraint.

---

### method: substitution and single-variable optimization

#### theorem (implicit constraint reduction)
*if a constraint is given explicitly as $y = g(x)$, then the optimization problem $\max f(x, y)$ reduces to a single-variable problem:*
$$
h(x) = f(x, g(x)).
$$
*critical points occur where*  
$$
\frac{d}{dx} h(x) = 0.
$$

#### applying the theorem

substituting $y = x - 1$ into $f(x,y)$:
$$
h(x) = e^x (x - 1).
$$

#### computing critical points

differentiate:
$$
\frac{d}{dx} h(x) = e^x (x - 1) + e^x (1).
$$
$$
= e^x (x - 1 + 1) = e^x x.
$$

set to zero:
$$
e^x x = 0.
$$

since $e^x > 0$ for all $x$, the only solution is:
$$
x = 0.
$$

#### computing function values

at $x = 0$:
$$
y = 0 - 1 = -1.
$$
$$
f(0, -1) = e^0 (-1) = -1.
$$

#### second derivative test

compute:
$$
\frac{d^2}{dx^2} h(x) = \frac{d}{dx} (e^x x) = e^x x + e^x = e^x (x + 1).
$$

evaluating at $x = 0$:
$$
h''(0) = e^0 (0 + 1) = 1 > 0.
$$

since $h''(0) > 0$, $x = 0$ is a **local minimum**.

---

### conclusion

- **minimum value**: $-1$ at $(0, -1)$.
- **no maximum**: as $x \to \infty$, $h(x) \to \infty$.


