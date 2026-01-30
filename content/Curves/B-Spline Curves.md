B-Spline [[curves]] are parametric curves defined by a linear combination of *control points* and corresponding *basis functions*. These basis functions, called B-Splines (short for Basis-Splines) determine how each control point influences the shape of the curve over a defined *parametric space*. 

The general equation for a B-Spline curve is:
$$
\mathbf{C}(\xi) = \sum_{i=1}^{n}{N_{i,p}(\xi) \, \mathbf{P}_i}
$$
Where:
- $\mathbf{C}(\xi)$ is the position of the point on the B-Spline curve at parameter value $\xi \in [0, 1]$,
- $N_{i,p}$ are the basis functions of polynomial degree $p$ at each control point,
- $P_i$ are the control points that define the curve, with $i \in [1, 2, \dots, n]$, where $n$ is the total number of control points.

The parametric space is divided into intervals and the B-Splines are defined as piecewise polynomials on those intervals, with certain continuity requirements between those intervals. 

The following advantages are obtained over Bézier curves, which are a B-Spline defined over a single knot interval:

- Independent polynomial degree $p$, since the number of intervals is arbitrary.
- Local influence of control points.
- Higher continuity between subcurves.
## Knot Vector

The parametric space is defined by the so called knot vector, which is a set of parametric coordinates $\xi_i$ in non-descending order that divide the parametric space into sections:
$$
\Xi = [\xi_1, \xi_2, \dots, \xi_m] \qquad m = n + p + 1
$$
If a knot value appears more than once, it is called a *multiple knot*. A B-Spline basis function is:

- $C^{\infty}$ continous inside a knot span,
- $C^{p-1}$ continous at a single knot,
- $C^{p-k}$ continous at a knot of multiplicity $k$.

If the first and last knot have the multiplicity $k=p+1$, we call it an **open knot** (clamped). In these cases, the first and last control point are interpolated and the curve is tangential to the control polygon at the start and end of the curve.

*Note*: Open knot vectors are standard in CAD applications and therefore always assumed.
## Basis Functions: Cox-de Boor Recursion Formula

Based on the knot vector and the polynomial degree, B-Spline basis functions are computed by the **Cox-de Boor** recursion formula. 

Beginning with $p=0$:
$$
N_{i,0}(\xi) =
\begin{cases}
1 & \text{if } \xi_i \leq \xi \leq \xi_{i+1} \\
0 & \text{otherwise}
\end{cases}
$$
And for $p \geq 1$, it is:
$$
N_{i,p}(\xi) = \frac{\xi - \xi_i}{\xi_{i+p} - \xi_i} N_{i,p-1}(\xi) + \frac{\xi_{i+p+1} - \xi}{\xi_{i+p+1} - \xi_{i+1}} N_{i+1,p-1}(\xi)
$$
From this formulation, some important **properties** of B-Spline basis functions can be deduced:

- Local support, i.e. a basis function $N_{i,p}(\xi)$ is non-zero only in the interval $[\xi_i, \xi_{i+p+1}]$ (assuming an open knot vector).
- Partition of unity, i.e. $\sum_{i=1}^{n}{N_{i,p}(\xi) = 1}$.
- Non-negativity, i.e. $N_{i,p}(\xi) \geq 1$.
- Linear independence, i.e. $\sum_{i=1}^{n}{\alpha_i N_{i,p}(\xi) = 0} \qquad \alpha_j = 0, j = 1, 2, \dots, n$.
## Properties

For recap, important properties of B-Spline curves are:

- Convex hull property: the curve is contained inside the convex hull of the control polygon. 
- In general, the control points are not interpolated.
- The control points have an influence on maximum $p+1$ sections. This property is called **local support**.
- For open knot vectors, the first and last control points are interpolated and the curve is tangential to the control polygon at the start and the end of the curve.
- The curve is $C^{\infty}$ continous between two knots and $C^{p-k}$ continous at a knot of multiplicity $k$.
- Affine transformations of the B-Spline curve are performed by transforming the control points correspondingly.
- A Bézier curve is a B-Spline curve with only one know interval.