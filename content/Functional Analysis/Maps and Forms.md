***`Previous`***: [[Spaces and Subspaces]]

**Definition** (`mapping`). Let $X, Y$ be sets. $f: X \rightarrow Y, x \mapsto f(x)$ is called a *map* or a *mapping* if $f$ assigns exactly one $f(x) = y \in Y$ to every $x \in X$. 

**Definition** (`linear mapping`). Let $V, W$ be linear spaces over $\mathbb{K}$. A map $L: V \rightarrow W$ is called *linear* for all $u,v \in V, \alpha \in \mathbb{K}$ if:

- $L(u+v) = L(u) + L(v)$
- $L(\alpha \cdot v) = \alpha \cdot L(v)$

**Definition** (`linear form`). Let $V$ be a linear space over $\mathbb{K}$. A linear map $L: V \rightarrow \mathbb{K}$ is called a *linear form*.

```
In other words, a form is a mapping from a linear space into its underlying field.
```

**Definition** (`bilinear form`). Let $V, W$ be linear spaces over $\mathbb{R}$. A map $a: V \times W \rightarrow \mathbb{R}, (v, w) \mapsto a(v, w)$ is a bilinear form if it is a linear form in both of its arguments:

- $a_w: V \times W \rightarrow \mathbb{R}, u \mapsto a_w(u) := a(u, w)$
- $a_v: V \times W \rightarrow \mathbb{R}, u \mapsto a_v(u) := a(v, u)$

***`Next`***: [[Inner Products]]