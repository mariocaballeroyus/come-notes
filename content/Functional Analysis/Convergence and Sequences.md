***`Previous`***: [[Norms and Metrics]]

**Definition** (`sequence`). Let $V$ be a normed space. A sequence $(v_n)_{n \in \mathbb{N}}$ is an ordered set in $V$ whose members can be labeled with positive integers. We write $\{ u_1,u_2,\dots \}$ or $\{ u_n \}_{n=1}^{\infty}$. 

**Definition** (`convergence of sequences`). A sequence $\{ u_n \}_{n \in \mathbb{N}} \subset V$  is *convergent* if there is a member $u \in W$ for which, given any $\epsilon > 0$, a number $N$ can be found such that
$$
|| u_n - u || < \epsilon \qquad \text{for all } n>N
$$
If this is the case, we write $u_n \to u$ and $u$ is called the limit of the sequence. This can also be stated as
$$
\lim_{n \to \infty}{|| u_n-u ||} = 0
$$
**Definition** (`equivalent norms`). If $(u_n)_{n \in \mathbb{N}}$ is a sequence in $W$ and $u_n \to u$ w.r.t. $|| \cdot ||_A$, meaning that $\lim_{n \to \infty}{|| u-u_n ||_A} = 0$, then $u_n \to u$ w.r.t. $|| \cdot ||_B$ as well. To see this, we note that
$$
||u-u_n||_B \leq M ||u-u_n||_A \to 0 \qquad \text{as } n \to \infty
$$
***`Next`***: [[Completeness]]