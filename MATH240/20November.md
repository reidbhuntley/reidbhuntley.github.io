# MATH 240
### Wed. November 20th, 2019
---

Recall that if $S=\{u_1,...,u_p\}$ is an orthogonal set of non-zero vectors, then $S$ is linearly independent and forms a basis for the subspace spanned by $S$.

__Theorem.__ Let $\{u_1,...,u_p\}$ be an orthogonal basis for a subspace $W$. For each $y$ in $W$, the weights in the linear combination $y=c_1u_1+...+c_pu_p$ are given by $c_j=\dfrac{y\cdot u_j}{u_j \cdot u_j}$ for $j=1,...,p$.

This theorem lets us change basis without requiring any row reduction computations, as long as that basis is an orthogonal basis.

# Orthogonal Projection

Consider a non-zero $u$ in $\R^n$. We want to write $y=\hat{y}+z$ where $\hat{y}=\alpha u$ for some scalar $\alpha$, and where $z$ is orthogonal to $u$ (that is, $z\cdot u=0$).

$$
\begin{aligned}
    z&=y-\hat{y}\\
    &=y-\alpha u\\
    z\cdot u&=(y-\alpha u)\cdot u\\
    0&=(y-\alpha u)\cdot u\\
    0&=y\cdot u-(\alpha u)\cdot u\\
    0&=y\cdot u-\alpha(u\cdot u)\\
    \alpha&=\dfrac{y\cdot u}{u\cdot u}\\\\
    \hat{y}&=\dfrac{y\cdot u}{u\cdot u}u.
\end{aligned}
$$

The vector $\hat{y}$ is called the __orthogonal projection__ of $y$ _onto_ $u$, and the vector $z$ is called the __component__ of $y$ _orthogonal to_ $u$.

We can think of this as projecting $y$ onto $L$, where $L$ is the subspace spanned by the vector $u$, so sometimes $\hat{y}$ is denoted by $\text{proj}_L y$.

Essentially, $\hat{y}$ is the point in $L$ that is _closest_ to $y$, so this is where this notion of "projection" comes from. (Think of $\hat{y}$ as the "shadow" of $y$ onto the "wall" $L$.)
In this way, you can also think of $z$ as the shortest path between $y$ and $L$.

---
__Ex.__ Take $y=\begin{pmatrix}
    7\\6
\end{pmatrix}$, $u=\begin{pmatrix}
    4\\2
\end{pmatrix}$.

$$
\begin{gathered}
    \alpha=\dfrac{y\cdot u}{u\cdot u}=\frac{40}{20}=2\\
    \hat{y}=\alpha u=2\begin{pmatrix}
        4\\2
    \end{pmatrix}=\begin{pmatrix}
        8\\4
    \end{pmatrix}\\
    z=y-\hat{y}=\begin{pmatrix}
        -1\\2
    \end{pmatrix}
\end{gathered}
$$

---
# The Orthogonal Decomposition Theorem
__Theorem.__ Let $W$ be a subspace of $\R^n$. Then each $y$ in $\R^n$ can be written _uniquely_ in the form $$y=\hat{y}+z,$$ where $\hat{y}$ is in $W$ and $z$ is in $W^\perp$.

In fact, if $\{u_1,...,u_p\}$ is _any_ orthogonal basis of $W$, then $$\text{proj}_W y=\hat{y}=\dfrac{y\cdot u_1}{u_1\cdot u_1}u_1+...+\dfrac{y\cdot u_p}{u_p\cdot u_p}u_p$$ and $z=y-\hat{y}$.

---
__Ex.__ Let $u_1=\begin{pmatrix}
    2\\5\\-1
\end{pmatrix}$, $u_2=\begin{pmatrix}
    -2\\1\\1
\end{pmatrix}$, $y=\begin{pmatrix}
    1\\2\\3
\end{pmatrix}$.

$u_1\cdot u_2=0$, so $u_1$ and $u_2$ are orthogonal to each other, and as a result $W=\{u_1,u_2\}$ is an orthogonal basis for $\text{span}(W)$.

$$
\begin{aligned}
    \text{proj}_W y=\hat{y}&=\frac{y\cdot u_1}{u_1\cdot u_1}u_1+\frac{y\cdot u_2}{u_2\cdot u_2}u_2\\
    &=\frac{9}{30}\begin{pmatrix}
        2\\5\\-1
    \end{pmatrix}+\frac{3}{6}\begin{pmatrix}
        -2\\1\\1
    \end{pmatrix}\\
    &=\begin{pmatrix}
        -\frac{2}{5}\\2\\\frac{1}{5}
    \end{pmatrix}
\end{aligned}
$$$$
\begin{aligned}
    z&=y-\hat{y}\\
    &=\begin{pmatrix}
        1\\2\\3
    \end{pmatrix}-\begin{pmatrix}
        -\frac{2}{5}\\2\\\frac{1}{5}
    \end{pmatrix}\\
    &=\begin{pmatrix}
        \frac{7}{5}\\0\\\frac{14}{5}
    \end{pmatrix}
\end{aligned}
$$

---
# Orthonormal Set

__Definition.__ A collection of orthogonal vectors $\{u_1,...,u_p\}$ is said to be __orthonormal__ if each $u_i$ in the collection is a unit vector (that is, $\lVert u_i \rVert=1$).

__Theorem.__ If $\{u_1,...,u_p\}$ is an orthonormal basis for a subspace $W$ of $\R^n$, then $$\text{proj}_W y=(y\cdot u_1)u_1+...+(y\cdot u_n)u_n$$ (since all the denominators $u_i\cdot u_i$ from the previous equation are now equal to $1$).

Similarly, if $u=[u_1 ... u_p]$, then $\text{proj}_W y=uu^Ty$ for all $y$ in $\R^n$ (based on the definition of the dot product).
