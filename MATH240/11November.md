# MATH 240
### Mon. November 11th, 2019
---

Recall that we can answer questions about vectors in an abstract vector space _(like whether they're linearly independent)_ by finding a basis for the space, moving the vectors into $\R^n$ using the basis, answering the question there, and then moving back into the abstract space.

Can we do the same for linear transformations?

---

# Relative Matrix for a Linear Transformation

Let $V,W$ be vector spaces.
Let $B=\{b_1,...,b_n\}$ be an ordered basis for $V$ and $C=\{c_1,...,c_m\}$ be an ordered basis for $W$.
Let $T: V \rightarrow W$ be a linear transformation.

We want to find some $m\times n$ matrix $M$ such that $[T(x)]_C=M[x]_B$. If we do this, then we can completely represent $T(x)$ as a transformation from $\R^n$ to $\R^m$ rather than as an abstract transformation.

Assume that $x=r_1b_1+...+r_nb_n$.
$$
\begin{aligned}
    [x]_B&=\begin{pmatrix}
        r_1\\...\\r_n
    \end{pmatrix}\\\\
    T(x)&=T(r_1b_1+...+r_nb_n)\\
    &=r_1T(b_1)+...+r_nT(b_n)\\\\
    [T(x)]_C&=r_1[T(b_1)]_C+...+r_n[T(b_n)]_C\\
    &=\begin{bmatrix}
        [T(b_1)]_C&...&[T(b_n)]_C
    \end{bmatrix}\begin{pmatrix}
        r_1\\...\\r_n
    \end{pmatrix}\\
    &=\begin{bmatrix}
        [T(b_1)]_C&...&[T(b_n)]_C
    \end{bmatrix}[x]_B
\end{aligned}
$$
$$M=\begin{bmatrix}
        [T(b_1)]_C&...&[T(b_n)]_C
    \end{bmatrix}.$$

We call $M$ the matrix for $T$ relative to the bases $B$ and $C$.

---

__Ex.__ Suppose that $B=\{b_1,b_2\}$ is an ordered basis for $V$, $C=\{c_1,c_2,c_3\}$ is an ordered basis for $W$, and $T:V\rightarrow W$ is a linear transformation.
$$
\begin{aligned}
    T(b_1)&=3c_1+2c_2+4c_3\\
    T(b_2)&=c_1+5c_2+3c_3
\end{aligned}
$$ Find a matrix $M$ for $T$ relative to $B$ and $C$.
$$
\begin{aligned}
    [T(b_1)]_C&=\begin{pmatrix}
        3\\2\\4
    \end{pmatrix}\\
    [T(b_2)]_C&=\begin{pmatrix}
        1\\5\\3
    \end{pmatrix}\\
    M&=\begin{pmatrix}
        3&1\\2&5\\4&3
    \end{pmatrix}
\end{aligned}
$$

You can see that once the bases $B$ and $C$ are fixed, we can find a unique matrix for any linear transformation between $V$ and $W$.

---
# B-Matrix

Now we're going to look at a __special case__: $V=W,\ B=C$.
In this case, we call $M$ the matrix for $T$ relative to $B$, or simply the $B$-matrix for $T$, and denote it $[T]_B$ (i.e. $[T(x)]_B=[T]_B[x]_B$).

---
__Ex.__ We can represent taking the derivative as a linear transformation.
$$\begin{gathered}
    T:P_3\rightarrow P_3\\T(a_0+a_1t+a_2t^2+a_3t^3)=0a_0+a_1+2a_2t+3a_3t^2
\end{gathered}$$
Find the $B$-matrix for $T$ where $B=\{1,t,t^2,t^3\}$.

$$
\begin{aligned}
    [T(1)]_B&=\begin{pmatrix}
        0\\0\\0\\0
    \end{pmatrix}\\
    [T(t)]_B&=\begin{pmatrix}
        1\\0\\0\\0
    \end{pmatrix}\\
    [T(t^2)]_B&=\begin{pmatrix}
        0\\2\\0\\0
    \end{pmatrix}\\
    [T(t^3)]_B&=\begin{pmatrix}
        0\\0\\3\\0
    \end{pmatrix}
\end{aligned}
$$$$
\begin{aligned}
    [T]_B&=\begin{bmatrix}
        [T(1)]_B&[T(t)]_B&[T(t^2)]_B&[T(t^3)]_B
    \end{bmatrix}\\
    &=\begin{pmatrix}
        0&1&0&0\\0&0&2&0\\0&0&0&3\\0&0&0&0
    \end{pmatrix}
\end{aligned}
$$

---

__Theorem.__ Suppose $A=PCP^{-1}$. If $B$ is a basis for $\R^n$ formed from the columns of $P$, then $C$ is the $B$-matrix for $x\rightarrow Ax$.

Recall that $\R^n$ has infinitely many bases -- we just tend to use the standard basis because it's computationally convenient. However, you may encounter data represented in a different basis. We can use $C$ in that case to change coordinates between different basis systems.
