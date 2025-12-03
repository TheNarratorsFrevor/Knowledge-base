
**Theory:** Model pod placement as $\min \text{trace}(G \odot C(\ell))$ where:
- $G \in \{0,1\}^{n\times n}$: communication adjacency  
- $C(\ell) \in \mathbb{R}^{n\times n}$: ode congestion costs per layout $\ell$
- $\frac{d\mathbf{C}}{dt} = A(\ell) \mathbf{C} + B(\ell) \mathbf{R} \to \mathbf{C}^* = -(A+B)^{-1}B\mathbf{R}$

**A construction:** $A_{ij} = 0.3\delta_{ij} + 0.15 \cdot \mathbb{1}_{\ell(i)=\ell(j), i\neq j}$ (zero-lat co-location coupling)
