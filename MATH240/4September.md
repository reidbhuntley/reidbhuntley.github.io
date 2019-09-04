# MATH 240
### Wed. September 4th, 2019
---

# 1.3: Vectors
* __Column vector__ -- a matrix with one column, e.g. $
\begin{pmatrix}
    3\\5\\7
\end{pmatrix}
$
* Can be thought of as a point in space
* Represents a single solution, e.g. $\begin{pmatrix}
    3\\5\\7
\end{pmatrix} \rightarrow \begin{cases}
    x_1=3\\x_2=5\\x_3=7
\end{cases}$

## Adding vectors
* Matrices can be added together:
    - Matrices must have the same dimensions
    - Add corresponding elements together
$$
\begin{pmatrix}
    2&3\\5&7
\end{pmatrix} + \begin{pmatrix}
    5&3\\7&8
\end{pmatrix} = \begin{pmatrix}
    7&6\\12&15
\end{pmatrix}
$$
* Vectors are a subset of matrices so they can be added too:
$$
\begin{pmatrix}
    2\\3
\end{pmatrix} + \begin{pmatrix}
    3\\7
\end{pmatrix} = \begin{pmatrix}
    5\\10
\end{pmatrix}
$$

## Scaling vectors
* Can multiply every element of a vector by a constant:
$$
5\begin{pmatrix}
    3\\5
\end{pmatrix} = \begin{pmatrix}
    15\\25
\end{pmatrix}
$$
* Negative scalars will also flip the direction of the vector

---
## Span
$$
    \text{Span}\{v_1, v_2\}=\{c_1v_1+c_2v_2 \text{ ($c_1, c_2$ are scalars)}\}
$$
* The __span__ of a set of vectors is the set of all possible __linear combinations__ of those vectors.
* Size the of span is infinite unless $v_1=v_2...=v_n=0$
* If one vector is a linear combination of other vectors in the set, then removing it from the set won't change the span at all.

---
## Properties of $\ \R^n$

For all $u,v,w$ in $\R^n$, and $c,d$ in $\R$:
$$
\begin{aligned}
    u+v&=v+u\\
    (u+v)+w&=u+(v+w)\\
    u+0=0+u&=u\\
    u+(-u)&=0\\
    c(u+v)&=cu+cv\\
    (c+d)u&=cu+du\\
    (cd)u&=c(du)\\
    1u&=u
\end{aligned}
$$

$$
ux_1+vx_2=w\text{ has a solution iff } w \text{ is in Span}\{u,v\}.
$$

---
###__Example.__
Is $\begin{pmatrix}
    1\\3
\end{pmatrix}$ in the span of $\begin{pmatrix}
    1\\1
\end{pmatrix}$ and $\begin{pmatrix}
    2\\2
\end{pmatrix}$?
$$
\begin{gathered}
    \begin{pmatrix}
        1\\1
    \end{pmatrix}x_1+\begin{pmatrix}
        2\\2
    \end{pmatrix}x_2=\begin{pmatrix}
        1\\3
    \end{pmatrix}\\
    \begin{pmatrix}
        1&2&1\\1&2&3
    \end{pmatrix} \rightarrow \begin{pmatrix}
        1&2&1\\0&0&2
    \end{pmatrix}
\end{gathered}
$$
The system has no solution; therefore $\begin{pmatrix}
    1\\3
\end{pmatrix}$ is _not_ in the span.