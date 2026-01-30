A membrane plate is a structural element characterized by a state where only membrane action and no bending or twisting is present. Internal forces are distributed exclusively within the plane of the element, resulting in normal and shear stresses that are assumed to be constant through the thickness. Because the loading is confined to the $xy$-plane, the mechanical response is described entirely by the mid-surface displacements.

## Stress Resultants

By integrating the stress components through the thickness of the plate, we define the **stress resultants**, which represent the total force per unit length acting on the cross-section. In Voigt notation, these read as:
$$
\mathbf{n} 
=
\int_{-t/2}^{t/2} \begin{Bmatrix} \sigma_{xx} \\ \sigma_{yy} \\ \tau_{xy} \end{Bmatrix} dz 
=
t \begin{Bmatrix} \sigma_{xx} \\ \sigma_{yy} \\ \tau_{xy} \end{Bmatrix} 
=
\begin{Bmatrix} n_x \\ n_y \\ n_{xy} \end{Bmatrix}
$$
Because the formulation has been condensed to the mid-surface, the external energy is described by the work of forces acting on the 2D domain. We will be therefore using area $\mathbf{q}$ and line $\mathbf{p}$ loads respectively to represent the external traction and body forces integrated over the thickness.
## Governing Equations
### Equilibrium Equations

The equilibrium of internal and external (area) forces at an infinitesimal small element, $\nabla \cdot \boldsymbol{\sigma} + \mathbf{f} = 0$, gives after thickness pre-integration:
$$
\begin{aligned}
\frac{\partial n_x}{\partial x} + \frac{\partial n_{yx}}{\partial y} + p_x &= 0 \\
\frac{\partial n_y}{\partial y} + \frac{\partial n_{xy}}{\partial x} + p_y &= 0 \\
n_{xy} &= n_{yx}
\end{aligned}
$$
### Kinematic Equations

The total strain is defined at any point $\boldsymbol{\varepsilon} = \frac{1}{2}(\nabla \mathbf{u} + (\nabla \mathbf{u})^T)$ by its three components:
$$
\varepsilon_x = \frac{\partial u}{\partial x}, 
\qquad
\varepsilon_y = \frac{\partial v}{\partial y},
\qquad
\gamma_{xy} = \frac{\partial u}{\partial y} + \frac{\partial v}{\partial x} = 2 \varepsilon_{xy}
$$
The distinction between tensor shear strain $\varepsilon_{xy}$ and $\gamma_{xy}$ is a critical convention that enables a consistent Voigt notation.
### Constitutive Equations

For a membrane plate using **Voigt notation**, we replace the fourth-order tensors with the material stiffness matrix **$\mathbf{D}$**, such that the relationship between the stress resultants $\mathbf{n}$ and the strains $\boldsymbol{\varepsilon}$ is expressed as $\mathbf{n} = t \mathbf{D} \boldsymbol{\varepsilon}$.  

Alternatively, for hand calculations, and inverse transformation $\boldsymbol{\varepsilon} = \frac{1}{t} \mathbf{D}^{-1} \mathbf{n}$ might be preferred.
#### Plane Stress

The material stiffness $\mathbf{D}$ and compliance $\mathbf{D}^{-1}$ matrices are defined as follows:
$$
\mathbf{D} = \frac{E}{1-\nu^2} 
\begin{bmatrix} 
1 & \nu & 0 \\ 
\nu & 1 & 0 \\ 
0 & 0 & \frac{1-\nu}{2} 
\end{bmatrix},
\qquad
\mathbf{D}^{-1} = \frac{1}{E} \begin{bmatrix} 1 & -\nu & 0 \\ -\nu & 1 & 0 \\ 0 & 0 & 2(1+\nu) \end{bmatrix}
$$
#### Plane Strain

The material stiffness $\mathbf{D}$ and compliance $\mathbf{D}^{-1}$ matrices are defined as follows:
$$
\mathbf{D} = \frac{E}{(1+\nu)(1-2\nu)} 
\begin{bmatrix} 
1-\nu & \nu & 0 \\ 
\nu & 1-\nu & 0 \\ 
0 & 0 & \frac{1-2\nu}{2} 
\end{bmatrix},
\qquad
\mathbf{S} = \frac{1+\nu}{E} \begin{bmatrix} 1-\nu & -\nu & 0 \\ -\nu & 1-\nu & 0 \\ 0 & 0 & 2 \end{bmatrix}
$$
### Compatibility Condition

In this membrane plate formulation, we are solving for a total of **8 unknowns**: 3 stress resultants ($n_x, n_y, n_{xy}$), 3 strains ($\varepsilon_x, \varepsilon_y, \gamma_{xy}$), and 2 displacements ($u, v$). These are governed by **8 field equations**: 2 for equilibrium, 3 for constitutive behavior, and 3 for kinematics.

While the system appears balanced, a fundamental geometric constraint arises because we have **3 strain components derived from only 2 displacement fields**. This mathematical redundancy means that the strains are not independent; they must be related to one another to ensure that the material remains a continuous "continuum" without gaps or overlaps. The **Compatibility Condition** provides the necessary second-order partial differential equation to enforce this physical reality:

$$
\frac{\partial^2 \varepsilon_x}{\partial y^2} + \frac{\partial^2 \varepsilon_y}{\partial x^2} = \frac{\partial^2 \gamma_{xy}}{\partial x \partial y}
$$
In the **Displacement Method** commonly used in Finite Element Analysis, this condition is satisfied automatically because strains are computed directly from continuous displacement functions.

## Stress Method: Airy Stress Function

The **Airy Stress Function** is a powerful mathematical tool used to solve 2D elasticity problems by reducing the multiple governing equations of equilibrium into a single scalar function.

Instead of solving for the stress resultants $n_x, n_y,$ and $n_{xy}$ separately while trying to satisfy the equilibrium equations, we define them as derivatives of a single potential function $F$:
$$
n_x = t \frac{\partial^2 F}{\partial y^2}, \quad n_y = t \frac{\partial^2 F}{\partial x^2}, \quad n_{xy} = -t \frac{\partial^2 F}{\partial x \partial y}
$$
By defining the stresses this way, the **Equilibrium Equations** are automatically satisfied. The problem then shifts from satisfying equilibrium to satisfying **Compatibility**. When these stress definitions are substituted into the compatibility equation, we arrive at the **Biharmonic Equation**:
$$\frac{\partial^4 F}{\partial x^4} + 2 \frac{\partial^4 F}{\partial x^2 \partial y^2} + \frac{\partial^4 F}{\partial y^4} = 0 \quad \implies \quad \nabla^4 F = 0$$
This approach is the foundation of the **Stress Method**. In this framework, solving a complex membrane problem becomes a task of finding a function $F$ that satisfies the biharmonic equation while matching the specific force boundaries of the plate.
## Displacement Method: Principle of Virtual Work

Applying thickness pre-integration on the Principle of Virtual Work (PVW):
$$
\begin{aligned}
-(\delta \Pi) = -(\delta U + \delta W) 
&= 
\int_V{ \boldsymbol{\sigma} : \delta \boldsymbol{\varepsilon} \, \text{d}V } -
\int_V{ \mathbf{f} \cdot \delta \mathbf{u} \, \text{d}V } -
\int_S{\mathbf{t} \cdot \delta \mathbf{u} \, \text{d}S}
\\ &=
\int_A \left( \int_t \boldsymbol{\sigma} : \delta \boldsymbol{\varepsilon} \, \text{d}z \right) \text{d}A - 
\int_A \left( \int_t \mathbf{f} \cdot \delta \mathbf{u} \, \text{d}z \right) \text{d}A -
\int_{E} \left( \int_t \mathbf{t} \cdot \delta \mathbf{u} \, \text{d}z \right) \text{d}E 
\\ &=
\int_A {\boldsymbol{\mathbf{n}} : \delta \boldsymbol{\varepsilon}} \, \text{d}A - 
\int_A \mathbf{q} \cdot \delta \mathbf{u} \, \text{d}A - 
\int_{E} \mathbf{p} \cdot \delta \mathbf{u} \, \text{d}E 
\end{aligned}
$$
Such that:
$$
\mathbf{n} = \begin{bmatrix} \sigma_{xx} & \tau_{xy} \\ \tau_{yx} & \sigma_{yy} \end{bmatrix}, \quad \delta \boldsymbol{\varepsilon} = \begin{bmatrix} \delta \varepsilon_{xx} & \delta \gamma_{xy}/2 \\ \delta \gamma_{yx}/2 & \delta \varepsilon_{yy} \end{bmatrix}
$$
## Finite Element Formulation

### 3-Node Triangle

The shape functions can be defined w.r.t. the $xy$-coordinate system as:
$$\begin{aligned}
N_1(x,y) &= \frac{1}{2 \Delta} \left( x_2y_3 - x_3y_2 + (y_2-y_3)x + (x_3-x_2)y \right) \\
N_2(x,y) &= \frac{1}{2 \Delta} \left( x_3y_1 - x_1y_3 + (y_3-y_1)x + (x_1-x_3)y \right) \\
N_2(x,y) &= \frac{1}{2 \Delta} \left( x_1y_2 - x_2y_1 + (y_1-y_2)x + (x_2-x_1)y \right)
\end{aligned}$$
where $\Delta$ is the triangle element area.
### 4-Node Quadrilateral

