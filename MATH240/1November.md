# MATH 240
### Fri. November 1st, 2019
---

# Change of Basis Review
Let $B=\{b_1,...,b_n\}$ and $C=\{c_1,...c_n\}$ be bases of a vector space $V$. Then there is a unique $n\times n$ matrix $P_{C\leftarrow B}$ such that $[x]_C=P_{C\leftarrow B}[x]_B$.

The columns of $P_{C\leftarrow B}$ are the $C$-coordinate vectors of the vectors in the basis $B$, i.e. $P_{C\leftarrow B}=\begin{bmatrix}
    [b_1]_C,...,[b_n]_C
\end{bmatrix}$.

---
__Ex.__ Let $b_1=\begin{pmatrix}
    -9\\1
\end{pmatrix},\ b_2=\begin{pmatrix}
    -5\\1
\end{pmatrix},\ c_1=\begin{pmatrix}
    1\\-4
\end{pmatrix},\ c_2=\begin{pmatrix}
    3\\-5
\end{pmatrix}$.

$B=\{b_1,b_2\},\ C=\{c_1,c_2\}$ form bases of $\R^2$. Find the change of basis matrix $P_{C\leftarrow B}$.

$$
\begin{aligned}
    \begin{bmatrix}
        c_1&c_2
    \end{bmatrix}[b_1]_C&=b_1\\
    \begin{bmatrix}
        c_1&c_2
    \end{bmatrix}[b_2]_C&=b_2\\
\end{aligned}
$$ The operations to reduce $\begin{bmatrix}
    c_1&c_2
\end{bmatrix}$ to the identity will be the same for both equations. Therefore to simplify computations we can place $\begin{bmatrix}
    b_1&b_2
\end{bmatrix}$ to the right of it, reduce it to the identity, and then whatever ends up on the right will be $P_{C\leftarrow B}$ _(similar to the technique we used before to find the inverse of a matrix)_.

---
# Eigenvalues and Eigenvectors
Given an $n\times n$ matrix $A$, what points will remained __fixed__ under the transformation $x\rightarrow Ax$?

This question is significant because the result of applying the transformation to that point any number of times will be easily computable.

__Definition.__ Let $A$ be an $n\times n$ matrix. A scalar $\lambda$ is called an __eigenvalue__ of $A$ if there is a _non-trivial_ (non-zero) solution $x$ of $Ax=\lambda x$. Such a vector $x$ is called an __eigenvector__ of $\lambda$.

---
__Ex.__
If $x$ is an eigenvector of $A$ with an eigenvalue of $2$, then $Ax=2x$.
$A^2(x)=A(Ax)=A(2x)=2A(x)=4x$.
$A^3(x)=A(A(Ax))=A(4x)=4A(x)=8x.$
$A^n(x)=2^nx$.
This point moves _away_ from the origin in a straight line under repeated multiplication with $A$.

If $x$ is an eigenvector of $A$ with an eigenvalue of $\frac{1}{2}$, then $Ax=\frac{1}{2}x$.
$A^2(x)=A(Ax)=A(\frac{1}{2}x)=\frac{1}{2}A(x)=\frac{1}{4}x$.
$A^3(x)=A(A(Ax))=A(\frac{1}{4}x)=\frac{1}{4}A(x)=\frac{1}{8}x.$
$A^n(x)=2^{-n}x$.
This point moves _towards_ the origin in a straight line under repeated multiplication with $A$.

---
__Ex.__
Let $A=\begin{pmatrix}
    1&6\\5&2
\end{pmatrix}$, $u=\begin{pmatrix}
    6\\-5
\end{pmatrix}$, and $v=\begin{pmatrix}
    3\\-2
\end{pmatrix}$. Are either $u$ or $v$ eigenvectors of $A$?

$$
\begin{aligned}
    Au&=\begin{pmatrix}
        -24\\20
    \end{pmatrix}\\
    &=-4\begin{pmatrix}
        6\\-5
    \end{pmatrix}\\
    &=-4u\\
    &=\lambda u\\
    \\
    Av&=\begin{pmatrix}
        -9\\11
    \end{pmatrix}\\
    &\neq \lambda v
\end{aligned}
$$
$u$ is an eigenvector of $A$ with an eigenvalue $-4$ because $Au=-4u$.
$v$ is _not_ an eigenvector of $A$ because there is no scalar $\lambda$ such that $Av=\lambda v$.

---
__Ex.__
Show that $7$ is an eigenvalue of $\begin{pmatrix}
    1&6\\5&2
\end{pmatrix}$.

$$
\begin{aligned}
    Ax&=7x\\
    Ax-7x&=0\\
    (A-7I)x&=0\\
    \begin{pmatrix}
        -6&6\\5&-5    
    \end{pmatrix}x&=0
\end{aligned}
$$