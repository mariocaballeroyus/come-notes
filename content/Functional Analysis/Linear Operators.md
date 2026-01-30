***`Previous`***: [[Completeness]]

**Definition** (`injective operator`). An operator $L: V \to U$ is *one-to-one* or *injective* if no two distinct elements of $X$ are mapped to the same element in $Y$. That is, 
$$
Lv_1 = v_2 \, \text{only if } v_1 = v_2
$$
**Definition** (`surjective operator`). An operator $L: V \to U$ is *surjective* or *onto* if $L(V) = U$. 

**Definition** (`isomorphism`). An operator $L: V \to U$ is called an *bijective* or an isomorphism* if it is both injective and surjective.

**Definition** (`embedding`). Let $V, U$ be linear spaces and $W$ a subspace of $V$. Let $L: V \to U$ be an injective linear map. Then $W \subset V$ and $L(W) \subset U$ are isomorphic. We say that $L$ embeds $W$ into $U$. $L$ is an *embedding*.  

**Definition** (`continuous operator`). Let $V,W$ be normed linear spaces. A linear map $L: V \to W$ is *continuous* on $V$ iff it is continuous in in $0 \in V$. 

**Definition** (`boundedness`). Let $V, W$ be normed linear spaces with norms $||\cdot||_V$, $||\cdot||_W$. A linear map $L: V \to W$ is called *bounded* if there exists a constant $C \geq 0$ s.th.
$$
||Lw||_W \leq C ||v||_V \qquad \text{for all } v \in V.
$$
**Lemma**. Let $V,W$ be normed spaces, $L: V \to W$. Then $L$ is continuous iff $L$ is bounded.

**Definition** (`Riesz representation theorem`). Let $H$ be a Hilbert space with inner product $\left< \cdot,\cdot \right>$ and $L: V \to \mathbb{R}$ a continuous linear functional on $H$. Then there exists a unique element $u \in H$ s.th.
$$
Lv = \left< u,v \right> \qquad \text{for all } v \in H
$$
Furthermore,
$$
||L|| = ||u||.
$$

**Definition** (`Lax-Milgram theorem`). 

***`Next`***: [[Classical and Weak Solutions]]
