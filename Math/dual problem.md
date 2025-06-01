# dual problem

the dual problem pops up mostly in optimization, especially convex optimization and linear programming. it’s the “shadow” or flipped version of your original optimization problem, called the primal. understanding the dual helps with theory (duality theorems), computation (sometimes dual is easier), and sensitivity analysis.

---

## basics

- **primal problem**: your original optimization problem, e.g.  
  $$\min_x f(x) \quad \text{subject to } g_i(x) \leq 0, \, h_j(x) = 0$$  
- **dual problem**: derived by forming the *lagrangian* and swapping min/max roles to get a problem in the dual variables (lagrange multipliers). the dual typically *maximizes* a lower bound on the primal objective.

- **lagrangian**:  
  $$L(x, \lambda, \nu) = f(x) + \sum_i \lambda_i g_i(x) + \sum_j \nu_j h_j(x)$$  
  where $\lambda_i \geq 0$ are dual variables for inequalities, and $\nu_j$ for equalities.

- **dual function**:  
  $$q(\lambda, \nu) = \inf_x L(x, \lambda, \nu)$$  
  gives a lower bound on the primal optimum for any feasible dual $(\lambda, \nu)$.

- **dual problem**:  
  $$\max_{\lambda \geq 0, \nu} q(\lambda, \nu)$$

- **weak duality**: the dual objective value is always ≤ primal objective value (for minimization problems).  

- **strong duality**: under some conditions (convexity + constraint qualifications like Slater’s condition), the optimal values match exactly, meaning no duality gap.

---

## advanced stuff

- **duality gap**: difference between primal and dual optimum values. zero in strong duality cases, positive otherwise. tells you how “tight” your relaxation is.

- **kkt conditions**: Karush-Kuhn-Tucker conditions are necessary (and sometimes sufficient) optimality conditions connecting primal and dual variables. they essentially unify stationarity, primal feasibility, dual feasibility, and complementary slackness:
  
  $$\begin{cases}
  \nabla f(x^*) + \sum_i \lambda_i^* \nabla g_i(x^*) + \sum_j \nu_j^* \nabla h_j(x^*) = 0 \\
  g_i(x^*) \leq 0, \quad h_j(x^*) = 0 \\
  \lambda_i^* \geq 0 \\
  \lambda_i^* g_i(x^*) = 0 \quad \text{(complementary slackness)} \\
  \end{cases}$$

- **lagrange duality in linear programming**: the dual of a LP is another LP, switching constraints and objective coefficients. solving dual LP can be faster or more insightful.

- **fenchel duality**: extends duality beyond lagrange multipliers using convex conjugates, important for advanced convex analysis.

- **duality in nonlinear optimization**: more subtle. strong duality might fail unless regularity conditions hold.

---

## why care

- **algorithm design**: some methods (e.g. subgradient, dual ascent) work directly on the dual.

- **bounds**: dual gives guaranteed bounds on primal problem, useful in combinatorial optimization and relaxations.

- **sensitivity analysis**: dual variables tell you how sensitive the optimal value is to changes in constraints (shadow prices in economics).

---

## cheatsheet

| term                | notation            | meaning                                      |
|---------------------|---------------------|----------------------------------------------|
| primal problem      | $\min_x f(x)$       | original optimization problem                |
| lagrangian          | $L(x, \lambda, \nu)$ | combines objective + constraints weighted by dual vars |
| dual variables      | $\lambda, \nu$      | multipliers for inequality/equality constraints |
| dual function       | $q(\lambda, \nu)$   | $\inf_x L(x, \lambda, \nu)$, lower bound on primal |
| dual problem        | $\max_{\lambda \geq 0, \nu} q(\lambda, \nu)$ | maximizes dual function |
| weak duality        | $q(\lambda, \nu) \leq f(x)$ | dual objective ≤ primal objective          |
| strong duality      | primal opt = dual opt | zero duality gap, under convexity + constraints |
| kkt conditions      | see above           | necessary optimality conditions tying primal & dual |
| complementary slackness | $\lambda_i g_i(x) = 0$ | either constraint active or multiplier zero  |

---

see also [[lagrange multipliers]], [[convex optimization]], [[kkt conditions]], [[fenchel duality]], [[linear programming]]

