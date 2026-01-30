***``Previous``***: [[Maps and Forms]]

**Definition** (`inner product`). Let $V$ be a real linear space. A bilinear form $a: V \times V \rightarrow \mathbb{R}$ is called:

- *symmetric* if $a(v, w) = a(w, v)$ for all $v, w \in V$
- *positive semi-definite* if $a(v, v) \geq 0$ for all $v \in V$ 
- *positive definite* if it is positive semi-definite and $a(v, v) = 0$ if $v = 0$. 

A bilinear form $a: V \times V \rightarrow \mathbb{R}$ is called *inner product* of $V$ if it is symmetric and positive definite.

A real linear space with inner product is called *inner product space*. Its usual notation is $(V, \left< \cdot,\cdot \right>)$.

**Definition** (`orthogonality`). Let $V$ be an inner product space with inner product $\left< \cdot,\cdot \right>$. $u, v \in V$ are called orthogonal w.r.t. $\left< \cdot,\cdot \right>$ if $u, v \neq 0$ and $\left< u,v \right> = 0$.

**Theorem** (`Cauchy-Schwarz inequality`). Let $V$ be an inner product space. Then the inequality $\left< u,v \right>^2 \leq \left< u,u \right> \left< v,v \right>$ is valid for all $u,v \in V$.

**Example** (`Euclidean inner product`). 
$$
V = \mathbb{R}^n, \qquad a(v, w) = <v, w> := \sum_{i=1}^{n}v_iw_i
$$
This inner product is also called Euclidean product. 
$$
V = C([0,1], \mathbb{R}), \qquad a(f, g) = \int_{0}^{1}{f(x)g(x) \, \text{d}x}
$$
***`Next`***: [[Norms and Metrics]]