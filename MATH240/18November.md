# MATH 240
### Mon. November 18th, 2019
---

# Norm _(cont.)_
We said before that defining an inner product $\langle u,v\rangle$ gives us a __norm__ $\lVert v\rVert=\sqrt{\langle v,v\rangle}$ -- a notion of magnitude.

For $\R^n$, if the dot product $u^Tv$ is used as the inner product, then $\lVert v\rVert=\sqrt{x_1^2+x_2^2+...+x_n^2}$, our common notion of Euclidean distance from the origin.

We can also extend this to find the distance from _any_ other vector (not just the origin) by computing $\lVert u - v \rVert$.

However, when dealing with abstract vector spaces like $C[0,1]$, we also get these notions of magnitude and distance -- how "big" a function is and how "far" apart two functions are -- even if it's not intuitive at first.

By using $\int_0^1fg$ as the inner product of two functions in $C[0,1]$, the distance between them is now $\sqrt{\int_0^1(f-g)^2}$. Now that we have a notion of distance between two functions, we can treat these functions as vectors and perform calculus on them -- this is called __functional analysis__.

---
# Orthogonality
__Definition.__ Two vectors $u,v$ are __orthogonal__ if $\langle u,v\rangle = 0$. (You can visualize this as them being _perpendicular_ to each other in the plane that contains them and the origin.)

For example, if you think of the standard basis of $\R^n$, $$\{\begin{pmatrix}
    1\\0\\0\\...
\end{pmatrix},\begin{pmatrix}
    0\\1\\0\\...
\end{pmatrix},...\}$$ you can see that any two vectors in this set will be orthogonal to each other.

Also, every vector is orthogonal to the zero vector.

---
# Orthogonal Complement
__Definition.__ Let $W$ be a subspace of $V$. A vector $x$ in $V$ is said to be orthogonal to $W$ if $x$ is orthogonal to every $w$ in $W$. The collection of all vectors orthogonal to $W$ is denoted by $W^\perp$, which is called the __orthogonal complement__ of $W$.

If $V=W$, then $W^\perp$ contains only the zero vector.

__Theorem.__ Let $A$ be an $m\times n$ matrix. The orthogonal complement of $\text{Row}(A)$ is $\text{Nul}(A)$, and the orthogonal complement of $\text{Col}(A)$ is $\text{Nul}(A^T)$.

---
__Theorem.__ If $W$ is spanned by $\{w_1,...,w_k\}$, and $x$ is orthogonal to $w_1,...,w_k$, then $x$ is in $W^\perp$.

__Ex.__ If $V=\R^3$ and $W=\text{span}\{\begin{pmatrix}
    1\\0\\0
\end{pmatrix},\begin{pmatrix}
    0\\1\\0
\end{pmatrix}\}$, then $\begin{pmatrix}
    0\\0\\3
\end{pmatrix}$ is in $W^\perp$ because it is orthogonal to both of those vectors.

---
## Orthogonal Set
__Definition.__ A set of vectors $\{u_1,...,u_p\}$ is said to be orthogonal if each distinct pair of vectors $u_i,u_j$ in the set are orthogonal to each other (and $u_i\neq0$.)

---
## Orthogonal Basis
__Theorem.__ If $S=\{u_1,...,u_p\}$ is an orthogonal set of vectors, then $S$ is a basis for $\text{span}(S)$ _(i.e. $u_1,...,u_p$ are linearly independent)_.

__Definition.__ An __orthogonal basis__ for a subspace $W$ of $\R^n$ is a basis for $W$ that is also an orthogonal set.

It turns out that it is easier to calculate the coordinates of points in an orthogonal basis than those in a non-orthogonal basis.

__Theorem.__ Let $\{u_1,...,u_n\}$ be an orthogonal basis for a subspace $W$ of $\R^n$. For each $y$ in $W$, the weights in the linear combination $y=c_1u_1+...+c_nu_n$ are given by $c_j=\dfrac{y\cdot u_j}{u_j \cdot u_j}$.
