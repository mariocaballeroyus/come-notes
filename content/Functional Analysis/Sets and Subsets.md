**Definition** (`set`). A set is any well-defined collection of objects, mainly numbers, vectors of functions, and which are called members.

A set is usually denoted by a capital leter. If the object $x$ is a member of $A$ we write
$$
x \in A
$$
**Definition** (`subset`). If $A$ and $B$ are two sets, we say that $A$ is a subset of $B$ if each element of $A$ is an element of $B$. This is denoted by 
$$
A \subset B
$$
We say that $A$ is a proper subset of $B$ is $A$ is indeed a subset of $B$ and, furthermore, also contains elements that do not belong to $A$. If not, we write 
$$
A \subseteq B
$$
**Definition** (`open ball`). Given $x_0 \in \mathbb{R}$ and $r > 0$, then $B(x_0,r) := \{ x \in \mathbb{R} : |x-x_0| < r \}$ is the open ball in $\mathbb{R}$ with radius $r$ and center $x_0$. 

**Definition** (`open set`). A set $E \subset \mathbb{R}$ is said to be open if it contains an open ball in $\mathbb{R}$ about each of its points. 
A set set $E \subset \mathbb{R}$ is said to be closed if its complement is open.

**Definition** (`closure`). The closure $\bar{E}$ of a set $E$ is the smallest closed set containing $E$.

**Definition** (`bounded set`). A set $E \subset \mathbb{R}$ is said to be bounded if it has both an upper and lower bound. Thus, a set $A$ is said to be bounded if there exists a positive number $M$ s.th.
$$
|x| \leq M \qquad \text{for all } x \in A
$$
**Definition** (`compactness`). A set $X \subset \mathbb{R}$ is said to be compact if and only it is closed and bounded.

***`Next`***: [[Spaces and Subspaces]]