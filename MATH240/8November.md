# MATH 240
### Fri. November 8th, 2019
---

# Diagonalization Theorem
An $n\times n$ matrix $A$ is diagonalizable if and only if $A$ has $n$ linearly independent eigenvectors.

In fact, $A=PDP^{-1}$ where $D$ is some diagonal matrix if and only if the columns of of $P$ are $n$ linearly independent eigenvectors of $A$. In this case the diagonal entries of $D$ are eigenvalues of $A$ that correspond to the eigenvectors in $P$.

---
__Ex.__ Is $A=\begin{pmatrix}
    5&-8&1\\0&0&7\\0&0&-2
\end{pmatrix}$ diagonalizable? If yes, express $A$ as $PDP^{-1}$ with $D$ diagonal.

$A$ is a triangular matrix, so its eigenvalues are $\lambda_1=5,\ \lambda_2=0,\ \lambda_3=-2$. Since $A$ is a $3\times 3$ matrix and it has $3$ distinct eigenvalues, we know it is diagonalizable.

Now all we have to do is calculate the eigenvectors of $A$ to construct $P$.

For $\lambda=5$:
$$
\begin{gathered}
    [A-5I\mid0]=\begin{pmatrix}
        0&-8&1&0\\0&-5&7&0\\0&0&-7&0
    \end{pmatrix}\\\\
    x_3=0,\ x_2=0,\ x_1 \text{ free}\\
    \text{Nul}(A-5I)=\text{span}\{\begin{pmatrix}
        1\\0\\0
    \end{pmatrix}\}
\end{gathered}
$$

For $\lambda=0$:
$$
\begin{gathered}
    [A\mid0]=\begin{pmatrix}
        5&-8&1&0\\0&0&7&0\\0&0&-2&0
    \end{pmatrix}\\\\
    x_3=0,\ x_2\text{ free},\ x_1=\frac{8}{5}x_2\\
    \text{Nul}(A)=\text{span}\{\begin{pmatrix}
        \frac{8}{5}\\1\\0
    \end{pmatrix}\}
\end{gathered}
$$

For $\lambda=-2$:
$$
\begin{gathered}
    [A+2I\mid0]=\begin{pmatrix}
        7&-8&1&0\\0&2&7&0\\0&0&0&0
    \end{pmatrix}\\\\
    x_3\text{ free},\ x_2=\frac{-7}{2}x_3,\ x_1=\frac{-29}{7}x_3\\
    \text{Nul}(A+2I)=\text{span}\{\begin{pmatrix}
        \frac{-29}{7}\\\frac{-7}{2}\\1
    \end{pmatrix}\}
\end{gathered}
$$

$$
\begin{aligned}
    \\
    P&=\begin{pmatrix}
        1&\frac{8}{5}&\frac{-29}{7}\\0&1&\frac{-7}{2}\\0&0&1
    \end{pmatrix}\\
    D&=\begin{pmatrix}
        5&0&0\\0&0&0\\0&0&-2
    \end{pmatrix}\\
    A&=PDP^{-1}.
\end{aligned}
$$

---
What happens if a matrix _doesn't_ have $n$ distinct eigenvalues?

__Theorem.__
Let $A$ be an $n\times n$ matrix whose distinct eigenvalues are $\lambda_1,...,\lambda_p$.
* For $1\leq k\leq p$, the dimension of the eigenspace for $\lambda_k$ is less than or equal to the multiplicity of $\lambda_k$.
* $A$ is diagonalizable iff if the _sum_ of the dimensions of the eigenspaces is $n$. This occurs iff either of the following occur:
    1. The characteristic polynomial factors completely into distinct linear factors. 
    _(This is the case we dealt with before; this is true because each value's eigenspace will have a multiplicity & dimension of $1$)_
    2. The dimension of the eigenspace for $\lambda_k$ equals the multiplicity of $\lambda_k$ in the characteristic polynomial.

* If $A$ is diagonalizable and $B_k$ is a bsais for the eigenspace corresponding to $\lambda_k$ for each $k$, then the total collection of vectors in the sets $B_1,...,B_p$ forms a basis for $\R^n$.

---
__Ex.__ Determine if $A=\begin{pmatrix}
    1&0\\1&1
\end{pmatrix}$ is diagonalizable.

$$
\begin{aligned}
    A&=\begin{pmatrix}
        1&0\\1&1
    \end{pmatrix}\\
    \text{det}(A-\lambda I)&=\begin{vmatrix}
        1-\lambda&0\\1&1-\lambda
    \end{vmatrix}\\
    &=(1-\lambda)^2=0\\
    \lambda&=1\\\\
    A-1I&=\begin{pmatrix}
        0&0\\1&0
    \end{pmatrix}\\
    \text{Nul}(A-1I)&=\text{span}\{\begin{pmatrix}
        0\\1
    \end{pmatrix}\}
\end{aligned}
$$ $A$ is __not__ diagonalizable, as $\lambda$ has multiplicity $2$ in the characteristic equation, but the dimension of its eigenspace is only $1$.
