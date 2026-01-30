***`Previous`***: [[Classical and Weak Solutions]]

**Theorem**. Let $V$ be a linear space, $a: V \times V \to \mathbb{R}$ an inner product on $V$ and assume $L: V \to \mathbb{R}, v \mapsto Lv$ is a continuously differentiable linear form and $F: V \to \mathbb{R}$ is given by:
$$
F(v) := \frac{1}{2}a(v,v) - Lv
$$
Then $u \in V$ minimizes $F(\cdot)$, $F(u) = \min_{v \in V}{F(v)}$, iff $u \in V$ solves the variational problem:
$$
a(u,v) = Lv \qquad \text{for all } v \in V
$$
**Theorem** (`Riesz Representation Theorem`). Let $V$ be a Hilbert space with inner product $<\cdot,\cdot>$ and $L: V \to \mathbb{R}$ a continuous linear form. Then there exists a unique $u \in V$ s.th.
$$
Lv = <u,v> \qquad \text{for all } v \in V
$$
**Theorem** (`Lax-Milgram Lemma`). Let $V$ be a Hilbert space with natural norm $|| \cdot ||, L: V \to \mathbb{R}$ a continuous linear form, $a: V \times V \to \mathbb{R}$ a bilinear form satisfying
$$
c ||v||^2 \leq a(v,v) \qquad \text{for all } v \in V \, \text{and some } c > 0
$$
and
$$
a(u,v) \leq K ||u|| \, ||v|| \qquad \text{for all } u,v \in V \, \text{and some } K > 0
$$
Then there exists a unique $u \in V$ s.th.
$$
a(u,v) = Lv \qquad \text{for all } v \in V.
$$**Definition** (`coercive and continous`). Let $V$ be an inner product space with inner product $<\cdot,\cdot>$ and related norm $|| \cdot ||$. A bilinear form $a: V \times V \to \mathbb{R}$ is called:

- coercive iff there is a constant $c > 0$ such that
$$
|a(v,v)| \geq c ||v||^2 \qquad \text{for all } v \in V
$$
- continuous w.r.t. $|| \cdot ||$ iff there is a constant $K > 0$ s.th.
$$
|a(u,v)| \leq K ||u|| \, ||v|| \qquad \text{for all } u,v \in V.
$$

***`Next`***: [[Existence of Solutions]]