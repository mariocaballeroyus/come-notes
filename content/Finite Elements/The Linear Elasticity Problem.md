## Equilibrium of Forces

For a (quasi-static) 3D elastic body, balance of linear momentum (Newton's second law without inertia) gives **Cauchy's equilibrium equations**
$$
\nabla \cdot \boldsymbol{\sigma} + \mathbf{f} = 0
\qquad \text{in } \Omega
$$
where $\boldsymbol\sigma$ is the Cauchy stress tensor, $\mathbf{f}$ is the body force per unit volume and $\Omega$ is the reference configuration of the body.

The boundary $\partial\Omega$ is decomposed into a Dirichlet part $\Gamma_D$ and a Neumann part $\Gamma_N$, with $\Gamma_D \cap \Gamma_N = \emptyset$ and $\Gamma_D \cup \Gamma_N = \partial\Omega$. On these, we prescribe
$$\begin{aligned}
\mathbf{u} &= \bar{\mathbf{u}}
\qquad &\text{on } \Gamma_D\\
\boldsymbol\sigma \cdot \mathbf{n} &= \mathbf{t}
\qquad &\text{on } \Gamma_N
\end{aligned}$$
where $\mathbf{u}$ is the displacement field, $\bar{\mathbf{u}}$ is the prescribed displacement, $\mathbf{n}$ is the outward unit normal to $\partial\Omega$ and $\mathbf{t}$ is the prescribed traction.

This set of PDEs together with the boundary conditions is what we call the **strong form** of the linear elasticity problem.
## Principal of Virtual Work

To derive the **weak form**, choose a virtual displacement (test function) $\delta \mathbf{u}$ that vanishes on $\Gamma_D$ (i.e. kinematically admissible), multiply the strong form by $\delta\mathbf{u}$ and integrate over the domain:
$$
\int_{\Omega}{ \left( (\nabla \cdot \boldsymbol{\sigma}) \cdot \delta \mathbf{u} \right) \, \text{d}x } + 
\int_{\Omega}{ \mathbf{f} \cdot \delta \mathbf{u} \, \text{d}x } = 0
$$
Applying integration by parts and the divergence theorem, we obtain
$$
\begin{align}
\int_{\Omega}{ \left( (\nabla \cdot \boldsymbol{\sigma}) \cdot \delta \mathbf{u} \right) \, \text{d}x } &= 
\int_{\Omega}{\nabla \cdot \left( \boldsymbol{\sigma} \cdot \delta \mathbf{u} \right) \, \text{d}x } - 
\int_{\Omega}{ \boldsymbol{\sigma} : \left( \nabla \cdot \delta \mathbf{u} \right) \, \text{d}x } 
\\ &= 
\int_{\partial\Omega}{(\boldsymbol{\sigma} \cdot \mathbf{n}) \cdot \delta \mathbf{u} \, \text{d}s} - 
\int_{\Omega}{ \boldsymbol{\sigma} : \delta \boldsymbol{\varepsilon} \, \text{d}x }
\end{align}
$$
Since $\delta\mathbf{u} = 0$ on $\Gamma_D$, only $\Gamma_N$ contributes on the boundary, where $\boldsymbol\sigma \cdot \mathbf{n} = \mathbf{t}$. Substituting everything into the starting equation and rearranging terms yields the **principle of virtual work**:
$$
\int_{\Omega}{ \boldsymbol{\sigma} : \delta \boldsymbol{\varepsilon} \, \text{d}x }
=
\int_{\Omega}{ \mathbf{f} \cdot \delta \mathbf{u} \, \text{d}x } +
\int_{\Gamma_N}{\mathbf{t} \cdot \delta \mathbf{u} \, \text{d}s}
$$
## Principle of Minimum Potential Energy

For a linear elastic body under conservative loading, the **total potential energy** functional is defined as
$$
\Pi[\mathbf{u}] = U[\mathbf{u}] - W[\mathbf{u}] 
= 
\int_{\Omega}{\frac{1}{2}\boldsymbol{\sigma}:\boldsymbol{\varepsilon} \, \text{d}x} 
- \int_{\Omega}{\mathbf{f} \cdot \mathbf{u} \, \text{d}x}
- \int_{\Gamma_N}{\mathbf{t} \cdot \mathbf{u} \, \text{d}s}
$$
where $U$ is the internal (strain) potential energy, and $W$ is the work done by external forces (body forces and tractions).
 
 Among all kinematically admissible displacement fields $\delta\mathbf{u}$ (satisfying the Dirichlet boundary conditions), the actual equilibrium displacement $\mathbf{u}$ makes $\Pi[\mathbf{u}]$ stationary:
$$
\delta\Pi[\mathbf{u};\delta\mathbf{u}] = 0
\qquad \forall \delta\mathbf{u} = 0 \text{on } \Gamma_D
$$
Computing $\delta\Pi = 0$ by the Gateaux derivative of the potential energy functional gives the **principle of virtual work**, i.e. the weak form of the linear elasticity problem.

In contrast, the principle of minimum potential energy does not extend to systems with non-conservative forces. Typical examples are friction or follower forces. 