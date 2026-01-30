[[Theory of Plates]]
## Forces per unit length

The **normal (membrane) forces per unit length** are given by:

$$
\begin{align}
n_x &= \int_{-t/2}^{t/2}{\sigma_x \, \text{d}z} = t \sigma_x \\
n_y &= \int_{-t/2}^{t/2}{\sigma_y \, \text{d}z} = t \sigma_x \\
n_{xy} = n_{yx} &= \int_{-t/2}^{t/2}{\tau_{xy} \, \text{d}z} = t \tau_{xy}
\end{align}
$$

On the other hand, the external (body) forces become:

$$
\begin{align}
p_x &= \int_{-t/2}^{t/2}{b_x \, \text{d}z} \\
p_y &= \int_{-t/2}^{t/2}{b_y \, \text{d}{z}}
\end{align}
$$
### Equilibrium equations

$$
\begin{align}
\frac{\partial n_x}{\partial x} + \frac{\partial n_{yx}}{\partial y} + p_x &= 0 \\
\frac{\partial n_y}{\partial y} + \frac{\partial n_{yx}}{\partial x} + p_y &= 0 \\
n_{xy} &= n_{yx}
\end{align}
$$

## Kinematic equations

$$
\begin{align}
\varepsilon_x &= \frac{\partial u}{\partial x} \\
\varepsilon &= \frac{\partial v}{\partial y} \\
\gamma_{xy} &= \frac{\partial u}{\partial y} + \frac{\partial v}{\partial x}
\end{align}
$$
**Note**: Do not confuse:

$$
\varepsilon_{xy} = \frac{1}{2} \gamma_{xy}
$$

## Constitutive equations

### Plane stress

Since the structure is not loaded lateral to the mid-plane ($\sigma_z = 0$), we have isotropic elastic material considering the Poisson effect:

$$
\begin{align}
\varepsilon_x &= \frac{1}{Et} (n_x - \nu n_y) \\
\varepsilon_y &= \frac{1}{Et} (n_y - \nu n_x) \\
\gamma_{xy} &= \frac{2(1 + \nu)}{Et} n_{xy} = \frac{1}{Gt} n_{xy}
\end{align}
$$

With a change in thickness determined from:

$$
\varepsilon_z = -\frac{\nu}{Et}(n_x + n_y)
$$
## Compatibility condition

The compatibility equation ensures that the local strain components are geometrically consistent, that is, you can integrate them to obtain a single continous displacement field $u, v$ (mixed partial derivatives must commute):
$$
\frac{\partial \varepsilon_x}{\partial y^2} + \frac{\partial \varepsilon_y}{\partial x^2} = \frac{\partial^2 \gamma_{xy}}{\partial x \partial y}
$$
## Airy stress function

We introduce a scalar function $\phi(x, y)$ such that:

$$
\begin{equation}
n_x = \frac{\partial^2 \phi}{\partial y^2}, \quad
n_y = \frac{\partial^2 \phi}{\partial x^2}, \quad
n_{xy} = - ( \frac{\partial^2 \phi}{\partial x \partial y} + p_x y + p_y x ),
\end{equation}
$$

which automatically satisfy the equilibrium equations for constant $p_x$ and $p_y$.

Physically, $\phi$ represents a **stress potential energy** per unit thickness of the plate, and satisfies the Airy stress function:

$$
\nabla^4 \phi = \Delta\Delta \phi = 
\frac{\partial^4 \phi}{\partial x^4} + 2 \frac{\partial^4 \phi}{\partial x^2 \partial y^2} + \frac{\partial^4 \phi}{\partial y^4} = 0
$$
