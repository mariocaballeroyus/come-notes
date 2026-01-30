***`Previous`***: [[Sets and Subsets]]

**Definition** (`Space`). Let $\mathbb{K}$ be a field, $\mathbb{K} = \mathbb{R}$ or $\mathbb{K} = \mathbb{C}$. A *linear space* over $\mathbb{K}$ is a set $V$ equipped with the *addition* and *scalar multiplication* operations:
$$
+: V \times V \rightarrow V, (u, v) \mapsto u+v \qquad  \text{for all } u,v \in V
$$
$$
\cdot: \mathbb{K} \times V \rightarrow V, (\alpha, v) \mapsto \alpha \cdot v \qquad \text{for all } \alpha \in \mathbb{K}, v \in V
$$
And further, it satisfies the following axioms:

- Closure under addition and scalar multiplication
$$
\alpha u + \beta v \in V  \qquad  \text{for all } u,v \in V \, \text{and } \alpha,\beta \in \mathbb{K},
$$
- There is an element $0 \in V$ that has the property 
$$
u + 0 = u \qquad \text{for all } u \in V.
$$
**Definition** (`Subspace`). Let $V$ be a linear space and $W \subset V$ a subset. W is called *subspace* of $V$ of $W$ is a linear space w.r.t. the addition and scalar multiplication of $V$.

**Definition** (`Basis`). Let $V$ be a linear space over $\mathbb{K}$. A subset $B \subset V$ is called *basis* of $V$ if:

(i) $B$ is a generating system of $V$, such that $v = \sum_{i=1}^{k}{\alpha_i \cdot b_i}$ , 
(ii) this representation is unique, i.e. the elements of $B$ are linearly independent.

***`Next`***: [[Maps and Forms]]