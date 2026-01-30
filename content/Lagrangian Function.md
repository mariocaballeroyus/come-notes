
$$
\mathcal{L}(x, \lambda) = f(x) + \left< \lambda, g(x)\right>
$$

- $\lambda = 0$: inactive constraints
- $\lambda \geq 0$: active constraints

## KKT Conditions

The solution of the general constrained optimization problem satisfies the necessary **Karush-Kuhn-Tucker (KKT)** conditions:
$$\begin{aligned}
\frac{\partial \mathcal{L}}{\partial x_i} &= \frac{\partial f}{\partial x_i} + \sum_{j=1}^{p}{\lambda_j \frac{\partial g_j}{\partial x_i}} + \sum_{j=1}^{q}{\mu_j \frac{\partial h_j}{\partial x_i}} = 0 \\
\frac{\partial \mathcal{L}}{\partial \mu} &= h(\mathbf{x}) = 0 \\
\lambda_j \frac{\partial \mathcal{L}}{\partial \lambda_j} &= \lambda_j g_j(\mathbf{x}) = 0 \\
\lambda_j &\geq 0
\end{aligned}$$