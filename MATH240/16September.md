# MATH 240
### Mon. September 16th, 2019
---

## Rotation Matrix
$$
\begin{pmatrix}
    \cos\theta&-\sin\theta\\
    \sin\theta&\cos\theta
\end{pmatrix}
$$
Rotates a vector by $\theta$ degrees _counter-clockwise_.

## Projection Matrices
$$
\begin{pmatrix}
    1&0&0\\0&0&0\\0&0&1
\end{pmatrix}
$$
Projects a vector onto the $x$-$z$ plane (the $y$ component becomes 0).

---
# Linear Transformations

The point of showing these matrices is that there are ways to think about multiplying vectors by matrices outside the context of linear systems of equations. _(These matrices aren't always in row-reduced form.)_

These can be thought of as __functions__ _(for every input there is one output)_ with special properties.

$$
\begin{aligned}
    T: \ &\R^n \rightarrow \R^m\\
    T(x+y)&=T(x)+T(y)\\
    T(cx)&=cT(x)\\
    T(0)&=0
\end{aligned}
$$
(This third property shows that the function has a __fixed origin__, and is a result of the first property.)

We call any function with these properties a __linear transformation__, even if it's not a matrix.

For all $r$ in $\R$, $T_r(x) = rx$ is a linear transformation.
If $0<r<1$, then $T_r$ is called a __contraction__.
If $r>1$, then $T_r$ is called a __dialation__.

---
If $A$ is a $m\times n$ matrix, then $T(x)=Ax$ is a linear transformation from $\R^n$ to $\R^m$.
