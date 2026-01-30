[[Theory of Plates]]

## Principle of Virtual Work

Starting from the Principle of Virtual Work (PVW), the special case of a 2-dimensional plane stress/strain structure is considered by splitting the integrals into an integral over the thickness and into one over the mid-surface:

$$
-\delta \Pi = -(\delta U - \delta W) = 
\int_{t}{\int_{A}{\sigma_{ij} \, \delta \varepsilon_{ij} \, \text{d}A} \, \text{d}t} - 
\int_{t}{\int_{A}{b_i \, \delta u_i \, \text{d}A} \, \text{d}t} - 
\int_{t}{\int_{E}{g_i \, \delta u_i \, \text{d} \Gamma} \, \text{d}t} = 0
$$

As the stresses are constant through the thickness, the integration over $t$ can be done in advance:

$$
-\delta \Pi = 
\int_{A}{\mathbf{n} \, \delta \boldsymbol\varepsilon \text{d}A} - 
\int_{A}{\mathbf{q}^T \, \delta \mathbf{u} \, \text{d}A} -
\int_{E}{\mathbf{p}^T \, \delta \mathbf{u} \, \text{d}E}
$$

## Constitutive Equations

### Plane stress

$$
\mathbf{D} = \frac{E}{1 - \nu^2}
$$

### Plane strain

$$
\mathbf{D} = \frac{E}{(1 + \nu)(1 - 2\nu)}
$$

## B-Matrix

$$
\boldsymbol\varepsilon = \mathbf{B} \mathbf{u}
$$
## Assembly

$$
\mathbf{K} = t \int_{A}{\mathbf{B}^T \mathbf{D} \mathbf{B} \, \text{d}A}
$$

$$
\mathbf{f} = \int_{A}{\mathbf{N}^T \mathbf{q} \, \text{d}A} + \int_{E}{\mathbf{N}^T \mathbf{p} \, \text{d}E}
$$

