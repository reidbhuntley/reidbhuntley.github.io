# MATH 240
### Wed. September 11th, 2019
---

# Homogeneous Systems of Equations (cont.)
$$
A=\begin{pmatrix}
    3&5&-4&0\\
    -3&-2&4&0\\
    6&1&8&0
\end{pmatrix} \rightarrow \begin{pmatrix}
    1&0&-\frac{4}{3}&0\\
    0&1&0&0\\
    0&0&0&0
\end{pmatrix}
$$

The solution set of the homogeneous system of equations is equivalent to
$$
\text{Span}\{\begin{pmatrix}
    \frac{4}{3}\\0\\1
\end{pmatrix}\},
$$
i.e. it can be represented as $
c\begin{pmatrix}
    \frac{4}{3}\\0\\1
\end{pmatrix},
$ where $c$ is a scalar.

---
## Connecting to the Non-Homogeneous Case

If $
b=\begin{pmatrix}
    7\\-1\\-4
\end{pmatrix},
$ then find the solution to $Ax=b.$

$$
\begin{pmatrix}
    3&5&-4&7\\
    -3&-2&4&-1\\
    6&1&8&-4
\end{pmatrix} \rightarrow \begin{pmatrix}
    1&0&-\frac{4}{3}&-1\\
    0&1&0&2\\
    0&0&0&0
\end{pmatrix}
$$
$$
\begin{cases}
    x_1-\frac{4}{3}x_3=-1\\
    x_2=2\\
    x_3\text{ is free}
\end{cases} \rightarrow \begin{pmatrix}
    -1\\2\\0
\end{pmatrix} + x_3\begin{pmatrix}
    \frac{4}{3}\\0\\1
\end{pmatrix}
$$

The solution to the non-homogeneous system is just the solution to the homogeneous case plus some constant vector.

__Theorem:__ Suppose the equation $Ax=b$ is _consistent_ and $p$ is a solution. Then, the solution set of $Ax=b$ is the set of all vectors of the form $w=p+v_h$, where $v_h$ is _any_ solution of $Ax=0$.

---
# Linear Dependence/Independence

Let $S=\{v_1,...v_p\}$ be an indexed set of vectors. We say that $S$ is __linearly independent__ if $x_1v_1+...+x_pv_p=0$ implies that $x_1,...x_p=0$. _(i.e. the homogeneous system formed by using this set of vectors as columns only has the trivial solution.)_

If there is a solution where not all of the $x_i$ are zero, then $S$ is __linearly dependent.__

Linearly independent vectors span the entire space _(always consistent)_ and span it __uniquely__ _(so there's only one possible solution for each point)_, which makes them useful for labelling points in space.

---
### __Ex.__
$$
v_1=\begin{pmatrix}
    1\\2\\3
\end{pmatrix}, \ 
v_2=\begin{pmatrix}
    4\\5\\6
\end{pmatrix}, \ 
v_3=\begin{pmatrix}
    2\\1\\0
\end{pmatrix}
$$
Is $\{v_1,v_2,v_3\}$ linearly independent?
$$
x_1v_1+x_2v_2+x_3v_3=0
$$$$
\begin{pmatrix}
    1&4&2&0\\
    2&5&1&0\\
    3&6&0&0
\end{pmatrix}\rightarrow \begin{pmatrix}
    1&4&2&0\\
    0&-3&-3&0\\
    0&-6&-6&0
\end{pmatrix}\rightarrow \begin{pmatrix}
    1&4&2&0\\
    0&-3&-3&0\\
    0&0&0&0
\end{pmatrix}
$$
We can see that we have a free variable from the bottom row. Therefore $\{v_1,v_2,v_3\}$ is __linearly dependent__.
$$
\begin{pmatrix}
    1&4&2&0\\
    0&-3&-3&0\\
    0&0&0&0
\end{pmatrix}\rightarrow \begin{pmatrix}
    1&4&2&0\\
    0&1&1&0\\
    0&0&0&0
\end{pmatrix}\rightarrow \begin{pmatrix}
    1&0&-2&0\\
    0&1&1&0\\
    0&0&0&0
\end{pmatrix}
$$$$
\begin{cases}
    x_1=2x_3\\
    x_2=-x_3\\
    x_3\text{ is free}
\end{cases}\rightarrow x_3\begin{pmatrix}
    2\\-1\\1
\end{pmatrix}
$$$$
2v_1-1v_2+1v_3=0.
$$