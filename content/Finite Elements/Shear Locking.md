Shear locking is a finite‑element pathology that occurs when a shear‑deformable (Reissner-Mindlin‑type) element  becomes artificially stiff as the plate becomes very thin, because the element cannot represent pure bending without generating large, unphysical transverse shear strains.
## Kinematics

The transverse shear strains (averaged through the thickness) are given by:
$$
\gamma_{\alpha} = \frac{\partial{w}}{\partial {\alpha}} + \theta_{\alpha}
$$
The Kirchoff-Love thin-plate assumes that the normals remain orthogonal to the mid-surface after deformation, i.e. transverse shear strains vanish ($\gamma_{\alpha} = 0$), and therefore the rotations are no longer independent.

However, the Reissner-Mindlin treats the rotations of the normals $\theta_{\alpha}$ as independent kinematic variables, such that the transverse shear strains $\gamma_{\alpha}$ are generally non-zero.

## Incompatibility in the thin-plate limit

For a thin plate, the exact Reissner-Mindlin solution should approach the Kirchhoff-Love kinematics, so we expect $\gamma_{\alpha} \to 0$ as $t \to 0$. 

In finite element methods, we approximate
$$
w^h \in W_h, \qquad \theta_{\alpha}^h \in \Theta_h
$$
and approximate discrete shear strains as
$$
\gamma_{\alpha}^{h} = \frac{\partial{w^h}}{\partial{x_\alpha}} + \theta_{\alpha}^{h}
$$
Shear locking occurs when the chosen spaces $W_h$ and $\Theta_h$ are the same, that is, they are kinematically incompatible with the Kirchhoff constraint, and we cannot enforce $\gamma_{\alpha}^{h}$ over the element.
## Artificial Stiffness

In Reissner-Mindlin plate theory, the shear contribution to the strain energy scales as $U_s \propto t$, whereas the bending contribution scales as $U_b \propto t^3$. 

In a locking finite element, the discrete fields cannot enforce $\gamma_{\alpha}^{h} \approx 0$ in bending, so a spurious, thickness-independent shear strain remains. 
## Remedies

### Reduced Integration

Reduced integration alleviates shear locking by evaluating the shear part of the stiffness with a lower-order quadrature rule, often one Gauss point instead of the full set. 

This relaxed some of the spurious shear constraints at the integration level, so the discrete solution is no longer forced to satisfy an over-constrained shear field. 
### Mixed Interpolation of Tensorial Components (MITC)

MITC elements attack the problem at the level of strain interpolation rather than just the quadrature. The idea is that the displacement/rotation fields ($w^{h}, \theta^{h}$) are still interpolated in a standard way, but the transverse shear trains are reconstructed from these fields using a special mixed interpolation:
$$
\gamma_{\alpha}^{\text{MITC}}
\neq
\frac{\partial w^{h}}{\partial x_{\alpha}} + \theta_{\alpha}^{h}
$$
but are instead defined by projecting/sampling $\frac{\partial w^{h}}{\partial x_{\alpha}} + \theta_{\alpha}^{h}$ at selected points (typically edge midpoints) and then interpolating these sampled values with a lower-order.

<img src="mitc.jpg" alt="MITC4" width="50%" style="float: center; margin-left: 50px; margin-top: 25px; margin-bottom: 10px;"/>

$$
K = 
\int_{\Omega}{ \mathbf{B}^T \mathbf{D}_b \mathbf{B} \, \text{d}x }
+ \int_{\Omega}{ (\mathbf{B}_{s}^{\text{MITC}})^T \mathbf{D}_s \mathbf{B}_{s}^{\text{MITC}} \, \text{d}x }
$$
### Discrete Shear Gap (DGS)

Developed by Kai-Uwe-Bletzinger.