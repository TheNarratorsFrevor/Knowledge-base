$$
\boxed{
y(t) = y_{\mathrm{hom}}(t) + \sum_{k=0}^n A_k \int_0^t \frac{(t-\tau)^k}{k!} \, h(\tau) \, d\tau
}
$$
Where
$$

y_{\mathrm{hom}}(t) = \begin{cases}
C_1 e^{r_1 t} + C_2 e^{r_2 t}, & r_1 \neq r_2 \in \mathbb{R} \\
(C_1 + C_2 t) e^{r t}, & r_1 = r_2 = r \\
e^{\alpha t} \big( C_1 \cos(\beta t) + C_2 \sin(\beta t) \big), & r_{1,2} = \alpha \pm i \beta
\end{cases}

$$and
$$



h(t) = \mathcal{L}^{-1} \left[ \frac{1}{s^2 + a s + b} \right]

$$
.


