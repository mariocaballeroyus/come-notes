We consider a **Reissner-Mindlin** plate where the kinematic unknowns at the midsurface are the transverse displacement $w$ and the rotations of the normal $\boldsymbol\varphi^T = \begin{Bmatrix} \varphi_{x} & \varphi_{y}  \end{Bmatrix}$. 

The **stress resultants** (internal forces and moments per unit length) are collected as
$$
\mathbf{n} = \begin{Bmatrix} n_{x} \\ n_{y} \\ n_{xy} \end{Bmatrix}
, \qquad
\mathbf{m} = \begin{Bmatrix} m_{x} \\ m_{y} \\ m_{xy} \end{Bmatrix}
, \qquad
\mathbf{q} = \begin{Bmatrix} q_{x} \\ q_{y} \end{Bmatrix}
$$
The associated **generalized strains** are
$$
\boldsymbol\varepsilon = \begin{Bmatrix} \varepsilon_{x} \\ \varepsilon_{y} \\ 2\varepsilon_{xy} \end{Bmatrix}
, \qquad
\boldsymbol\kappa = \begin{Bmatrix} \kappa_{x} \\ \kappa_{y} \\ 2\kappa_{xy} \end{Bmatrix}
, \qquad
\boldsymbol\gamma = \begin{Bmatrix} \gamma_{x} \\ \gamma_{y} \end{Bmatrix}
$$
where $\boldsymbol\varepsilon$ is the in-plane strain, $\boldsymbol\kappa$ the curvature tensor, and $\boldsymbol\gamma$ the transverse shear strain vector.

To write everything compactly, we introduce the 2D **differential operators**
$$
\mathbf{L} = \begin{bmatrix} 
\frac{\partial}{\partial x} & 0 \\
0 & \frac{\partial}{\partial y} \\
\frac{\partial}{\partial y} & \frac{\partial}{\partial x}
\end{bmatrix}
, \qquad
\nabla = \begin{bmatrix} \frac{\partial}{\partial x} \\ \frac{\partial}{\partial x} \end{bmatrix}
$$
## Equilibrium

For a plate loaded by a transverse load $p(x, y)$, the static Reissner-Mindlin equilibrium equations in terms of stress resultants are
$$
\nabla^T \mathbf{q} + p = 0
, \qquad
\mathbf{L}^T \mathbf{m} - \mathbf{q} = 0
$$
## Kinematics

In Reissner-Mindlin theory, normals to the midsurface remain straight but not necessarily normal after deformation (shear deformable). The generalized strains follow from $\boldsymbol\varphi$ and $w$ as
$$
\boldsymbol\kappa = \mathbf{L} \boldsymbol\varphi 
, \qquad
\boldsymbol\gamma = \nabla w + \boldsymbol\varphi 
, \qquad
\boldsymbol\varepsilon = z \mathbf{L} \boldsymbol\varphi = z \boldsymbol\kappa
$$
where the in-plane strain through the thickness is assumed as linearly varying with the thickness coordinate $z$.
### Constitutive Relations

For an isotropic, homogeneous plate of thickness $t$, the bending moments are related to the curvature by
$$
\mathbf{m} =
\begin{Bmatrix} m_x \\ m_y \\ m_{xy} \end{Bmatrix} = 
\underbrace{ \overbrace{\frac{Et^3}{12(1-\nu^2)}}^{D}
\begin{bmatrix} 1 & \nu & 0 \\ \nu & 1 & 0 \\ 0 & 0 & \frac{1-\nu}{2}\end{bmatrix}  }_{\mathbf{D}_b}
\begin{Bmatrix} \kappa_x \\ \kappa_y \\ 2\kappa_{xy} 
\end{Bmatrix}
= \mathbf{D}_b \boldsymbol\kappa = \mathbf{D}_b \mathbf{L} \boldsymbol\varphi
$$
where $E$ and $\nu$ are the Young's modulus and Poisson ratio, respectively.

The transverse shear resultants satisfy
$$
\mathbf{q} =
\begin{Bmatrix} q_x \\ q_y \end{Bmatrix} = 
\underbrace{
\alpha G t \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} 
}_{\mathbf{D}_s}
\begin{Bmatrix} \gamma_x \\ \gamma_y \end{Bmatrix}
= \mathbf{D}_s \boldsymbol\gamma = \mathbf{D}_s (\nabla w + \boldsymbol\varphi)
$$
where $G$ is the shear modulus and $\alpha$ is the shear correction factor.
### The ABD Matrix

In the context of **Classical Laminated Plate Theory (CLPT)**, the constitutive matrices for membrane and bending action define the $\mathbf{A}$ and $\mathbf{D}$ matrices for a single, homogenous, isotropic layer of thickness $t$.
$$
\begin{Bmatrix} \mathbf{N} \\ \hline \mathbf{M} \end{Bmatrix} = \begin{bmatrix} \mathbf{A} & \mathbf{B} \\ \hline \mathbf{B} & \mathbf{D} \end{bmatrix} \begin{Bmatrix} \boldsymbol{\varepsilon} \\ \hline \boldsymbol{\kappa} \end{Bmatrix}
$$
where $\mathbf{A}$ is the extensional stiffness matrix, $\mathbf{D}$ is the bending stiffness matrix and $\mathbf{B}$ is the coupling stiffness matrix. The last one is only zero for symmetrically arranged laminates.
## Principle of Virtual Work

The **internal virtual work** can be expressed as a sum of the bending and shear contributions:
$$\begin{aligned}
-(\delta{U}) &=
\overbrace{
\int_{\Omega}{ \mathbf{m} \cdot \delta{\boldsymbol\kappa} \, \text{d}x }
}^{\text{bending}}
+ \overbrace{
  \int_{\Omega}{ \mathbf{q} \cdot \delta{\boldsymbol\gamma} \, \text{d}x }
}^{\text{shear}}
\\ &=
\int_{\Omega}{ \delta\boldsymbol\kappa^T \mathbf{D}_b \boldsymbol\kappa \, \text{d}x }
+ \int_{\Omega}{ \delta\boldsymbol\gamma^T \mathbf{D}_s \boldsymbol\gamma \, \text{d}x }
\\ &=
\int_{\Omega}{ \delta(\mathbf{L}\boldsymbol\varphi)^T \mathbf{D}_b \mathbf{L}\boldsymbol\varphi \, \text{d}x }
+ \int_{\Omega}{ \delta(\nabla{w} + \boldsymbol\varphi)^T \mathbf{D}_s (\nabla{w} + \boldsymbol\varphi) \, \text{d}x }
\end{aligned}$$
As for the **external virtual work**:
$$
-(\delta{W}) = 
\int_{\Omega}{ p \delta{w} \, \text{d}x }
+ \int_{\Gamma_N}{ \delta\boldsymbol\varphi^T \bar{\mathbf{m}} \, \text{d}s }
+ \int_{\Gamma_N}{ \delta{w}^T \mathbf{q} \, \text{d}s }
$$
## Finite Element Discretization

We collect the nodal **degrees of freedom** in the vector
$$
\mathbf{u} = \begin{Bmatrix} w_1 & \varphi_{x1} & \varphi_{y1} & \dots & w_n & \varphi_{xn} & \varphi_{yn} \end{Bmatrix}^T
$$
Using **standard interpolation** (same scalar shape function $N_i$ for all three DOFs at node $i$), we write
$$\begin{aligned}
w &= \mathbf{N}_w \mathbf{u} \\
\boldsymbol\varphi = \begin{Bmatrix} \varphi_{x} \\ \varphi_{y} \end{Bmatrix} &= \mathbf{N}_{\varphi} \mathbf{u}
\end{aligned}$$
with
$$\begin{aligned}
\mathbf{N}_{w} &= \begin{bmatrix} N_1 & 0 & 0 & \dots & N_n & 0 & 0 \end{bmatrix} \\
\mathbf{N}_{\varphi} &= \begin{bmatrix} 0 & N_1 & 0 & \dots & 0  & N_n & 0 \\ 0 & 0 & N_1 & \dots & 0 & 0 & N_n \end{bmatrix}
\end{aligned}$$
From the kinematic relations we obtain the standard **strain-displacement matrices**
$$\begin{aligned}
\mathbf{B}_b &= \mathbf{L} \mathbf{N}_{\varphi} \\
\mathbf{B}_s &= \nabla{\mathbf{N}_w} + \mathbf{N}_{\varphi}
\end{aligned}$$
Inserting the interpolations into the virtual work expression and collecting terms in $\delta{\mathbf{u}}$ and $\mathbf{u}$, we obtain
$$\begin{aligned} 
-\delta U 
&= 
\delta\mathbf{u}^T \left( 
\int_{\Omega} \mathbf{B}_b^T \mathbf{D}_b \mathbf{B}_b \, dx 
+ \int_{\Omega} \mathbf{B}_s^T \mathbf{D}_s \mathbf{B}_s \, dx 
\right) \mathbf{u} 
&&= 
\delta\mathbf{u}^T \left( \mathbf{K}_b + \mathbf{K}_s \right) \mathbf{u} 
\\ 
\delta W 
&= 
\delta\mathbf{u}^T \left( 
\int_{\Omega} \mathbf{N}_w^T p \, dx 
+ \int_{\Gamma_N}{ \mathbf{N}_{\varphi} \bar{\mathbf{m}} \, \text{d}s }
+ \int_{\Gamma_N}{ \mathbf{N}_w \bar{\mathbf{q}} \, \text{d}s }
\right) 
&&= 
\delta\mathbf{u}^T \mathbf{f} 
\end{aligned}$$
Since $\delta{\mathbf{u}}$ is arbitrary, the discrete equilibrium equation is
$$
(\mathbf{K}_b + \mathbf{K}_s) \mathbf{u} = \mathbf{f}
$$
with contributions from both the bending and shear stiffness.

## Kirchhoff-Love Theory

In K-L theory, only the bending term remains in the virtual work expression:
$$
-\delta{U} = \delta{\mathbf{u}}^T \left(
\int_{\Omega}{ (\mathbf{L} \tilde{\mathbf{N}}_{\varphi})^T \mathbf{D}_b (\mathbf{L} \tilde{\mathbf{N}}_{\varphi}) \, \text{d}x } 
\right) \mathbf{u}
$$
where the shape functions are modified to respect the Kirchhoff constraint:
$$
\boldsymbol\varphi = \tilde{\mathbf{N}}_{\varphi} \mathbf{u} = -\nabla{w} = -\nabla \mathbf{N}_w \mathbf{u}
$$
leading to:
$$\begin{aligned}
-\delta{U} &= \delta{\mathbf{u}}^T \left(
\int_{\Omega}{ (\nabla \mathbf{L} \mathbf{N}_{w})^T \mathbf{D}_b (\nabla \mathbf{L} \mathbf{N}_{w}) \, \text{d}x } 
\right) \mathbf{u}
\\ &= 
\delta{\mathbf{u}}^T \left(
\int_{\Omega}{ \mathbf{B}_{b}^T \mathbf{D}_b \mathbf{B}_{b} \, \text{d}x } 
\right) \mathbf{u}
\end{aligned}$$
and second order derivatives of the shape functions in the work functional. Thus, the stiffness matrix reduces to: