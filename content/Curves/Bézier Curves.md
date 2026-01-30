**Bézier [[curves]]** is a parametric curve defined by a set of control points.

The general equation of a Bézier curve of degree $p$, with $n$ control points is:

$$
\mathbf{C}(t) = \sum_{i=1}^{n} B_{i,p}(t) \cdot \mathbf{P}_i, \qquad t \in [0,1]
$$

## Properties

Some generic properties:

- Points  are called control points. 
- The polynomial degree depends on the number of control points, such that $p = n - 1$.
- The polygon of control points is called the control polygon (or Bézier polygon).
- The first point $\mathbf{P}_1$ and last point $\mathbf{P}_n$ are interpolated, meaning the curve passes through them.
-  Some curves cannot be represented exactly, such as circles or an offset curve to a Bézier curve.
- A Bézier curve can be split at any point into two sub Bézier curves.

Some **advantages** include:

- Shape functions independent of $\mathbf{P}_i$.
- Parametric curve description.
- Computationally efficient.
- 3D curves possible.
- Few oscillations.

Whereas some **disadvantages**:

- Global influence of control points.
- Polynomial degree $p$ not independent.
- Not all curves are representable.
- $C^0$ continuity if glued together.
## Bernstein Polynomials

The **Bernstein polynomials** are the basis functions for Bézier curves. For a given control point $\mathbf{P}_i$​, the associated Bernstein basis function $B_{i,p}(t)$ is:
$$
B_{i,p}(t) = \binom{i-1}{p} \cdot t^{i-1} \cdot (1 - t)^{p-i+1} \qquad i \in [1,2,\dots,n]
$$
The **binomial coefficient** counts the number of ways to choose $i$ elements from a set of $p$ elements, and determines the weight of each control point at any given $t$, ensuring that the contribution of each  is weighted properly based on its position on the control sequence.
$$
\binom{n}{k} = \frac{n!}{k! \cdot (n-k)!}
$$
The Bernstein polynomials are constructed such that they satisfy two important properties:
1. **Non-negativity**: $B_{i,p}(t) \geq 0$ for all $t \in [0, 1]$.
2. **Sum to 1**: The sum of all Bernstein polynomials at any $t$ equals 1:
$$
\sum_{i=0}^{p} B_{i,p}(t) = 1
$$
## De Casteljau's Algorithm

De Casteljau's algorithm is a geometric method used to evaluate and compute points on a Bézier curve.


