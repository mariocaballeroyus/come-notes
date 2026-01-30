### Strong Form

The plate bending problem is described by a fourth-order Partial Differential Equation (PDE), representing the point-wise equilibrium of internal resultant forces and moments on a plate.
$$
D \nabla^4 w = q
$$
Here, $w$ is the transversal displacement, $q$ is the uniformly applied load per unit area, and $D$ is the flexural rigidity of the material, defined as:
$$
D = \frac{Et^3}{12(1-\nu^2)}
$$
where $E$ is the Young's modulus, $t$ is the plate thickness and $\nu$ is the Poisson's ratio.
### Weak Form

By the Principle of Virtual Work (PVW), we state that for a body in equilibrium, the total virtual work done by all forces must be zero for any arbitrary virtual displacement $\delta{w}$.
$$
D \int_{\Omega} { (\nabla^4{w}) \delta{w} \, \text{d}x } = \int_{\Omega} { q \delta{w} \, \text{d}x }
$$
Applying integration by parts twice allows us to identify the virtual work done at the boundaries. The first integration by parts retrieves the contribution of shear moments:
$$\begin{aligned}
\int_{\Omega} { (\nabla^4{w}) \delta{w} \, \text{d}x } 
&=
\int_{\Omega} { \text{div}(\nabla(\nabla^2w)) \delta{w} \, \text{d}x }
\\ &=
- \int_{\Omega} { (\nabla \delta{w}) \cdot (\nabla(\nabla^2{w})) \, \text{d}x }
+ \int_{\partial\Omega} { (\nabla(\nabla^2{w}) \cdot \mathbf{n}) \delta{w} \, \text{d}s }
\end{aligned}$$
Whereas the second integration by parts retrieves the contribution of bending moments:
$$
\int_{\Omega} { (\nabla\delta{w}) \cdot (\nabla(\nabla^2{w})) }
=
- \int_{\Omega} { (\nabla^2{w})(\nabla^2{\delta{w}}) \, \text{d}x } 
+ \int_{\partial\Omega} { (\nabla^2{w} \cdot \mathbf{n}) \cdot \nabla{\delta{w}} \, \text{d}s }
$$
Putting everything together yields the final expression of the weak form, representing the equilibrium of internal and external virtual work done by the distributed load $q$ and the boundary resultants.
$$
\int_{\Omega} { D(\nabla^2{w})(\nabla^2{\delta{w}}) \, \text{d}x } 
- \underbrace{
  \int_{\partial\Omega} { D(\nabla^2{w} \cdot \mathbf{n}) \cdot \nabla{\delta{w}} \, \text{d}s } 
}_{\text{boundary moment}}
+ \underbrace{
  \int_{\partial\Omega} { D(\nabla(\nabla^2{w}) \cdot \mathbf{n}) \delta{w} \, \text{d}s }
}_{\text{boundary shear}}
= \int_{\Omega} { q \delta{w} \, \text{d}x }
$$
From a variational perspective, the form above requires $w \in H^2(\Omega)$, meaning the displacement and its first derivatives must be $C^1$ continuous across elements.
## Biharmonic Splitting

Many standard finite element libraries are based on $C^0$ continuous elements. To bypass the need for specialized $C^1$ elements, we use Biharmonic Splitting. 

This technique transforms the single fourth-order PDE into a system of two coupled second-order PDEs. By introd´cing an auxiliary variable, typically the bending moment tensor, we can work within the $H^1(\Omega)$ space, which only requires $C^0$ continuity. 

The split equations typically take the following form:
$$\begin{aligned}

- \nabla^2 w &= \boldsymbol\kappa(\mathbf{M}) \\

\nabla^2 M &= -\mathbf{q}

\end{aligned}$$

