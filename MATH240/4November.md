# MATH 240
### Mon. November 4th, 2019
---

$P_{C\leftarrow B}=(P_{B\leftarrow C})^{-1}$

---

# Eigenspace

Recall that $\lambda$ is an eigenvalue of a $n\times n$ matrix $A$ if $Ax=\lambda x$ for some $x$ in $\R^n$.

Note that this means $(A-\lambda I)x=0$ has non-trivial solutions.
The null space of $A-\lambda I$ is _precisely_ the collection of $x$ for which $(A-\lambda I)x=0$.

__Definition.__ The __eigenspace__ of $A$ corresponding to the eigenvalue of $\lambda$ of $A$ is the null space of $A-\lambda I$.

---
__Ex.__ Find a basis for the eigenspace corresponding to $\lambda =2$ for $A= \begin{pmatrix}
    4&-1&6\\2&1&6\\2&-1&8
\end{pmatrix}$.

$$
\begin{aligned}
    A-2I&=\begin{pmatrix}
        4&-1&6\\2&1&6\\2&-1&8
    \end{pmatrix}-\begin{pmatrix}
        2&0&0\\0&2&0\\0&0&2
    \end{pmatrix}\\
    &=\begin{pmatrix}
        2&-1&6\\2&-1&6\\2&-1&6
    \end{pmatrix}
\end{aligned}
$$

$$
\begin{aligned}
    &\begin{pmatrix}
        2&-1&6&0\\2&-1&6&0\\2&-1&6&0
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        2&-1&6&0\\0&0&0&0\\0&0&0&0
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        1&-\frac{1}{2}&3&0\\0&0&0&0\\0&0&0&0
    \end{pmatrix}\\
    \begin{pmatrix}
        x_1\\x_2\\x_3
    \end{pmatrix}&=x_2\begin{pmatrix}
        \frac{1}{2}\\1\\0
    \end{pmatrix}+x_3\begin{pmatrix}
        -3\\0\\1
    \end{pmatrix}
\end{aligned}
$$

Thus $\{\begin{pmatrix}
    \frac{1}{2}\\1\\0
\end{pmatrix},\begin{pmatrix}
    -3\\0\\1
\end{pmatrix}\}$ is a basis for the required eigenspace.

---
# Calculating Eigenvalues

Observation:
$(A-\lambda I)x=0$ has _non-trivial_ solutions if $\text{det}(A-\lambda I)=0$. This comes from the Invertible Matrix Theorem. (Recall that eigenvectors are _nonzero_ by definition, so if there are only trivial solutions then $A$ has no eigenvalues.)

__Definition:__ The equations $\text{det}(A-\lambda I)=0$ is called the __characteristic equation__ (for $A$).

__Theorem:__ A scalar $\lambda$ is an eigenvalue if and only if $\lambda$ satisfies the characteristic equation $\text{det}(A-\lambda I)=0$.

---
__Ex.__ Find the eigenvalues of $\begin{pmatrix}
    3&5&7\\0&2&9\\0&0&1
\end{pmatrix}$ by finding the zeroes of the characteristic equation.

$$
\begin{aligned}
    A-\lambda I&=\begin{pmatrix}
        3&5&7\\0&2&9\\0&0&1
    \end{pmatrix}-\begin{pmatrix}
        \lambda&0&0\\0&\lambda&0\\0&0&\lambda
    \end{pmatrix}\\
    &=\begin{pmatrix}
        3-\lambda&5&7\\0&2-\lambda&9\\0&0&1-\lambda
    \end{pmatrix}
\end{aligned}
$$

$A-\lambda I$ in this case is a triangular matrix, so its determinant is just the product of the entries on its diagonal.

$$
\begin{aligned}
    det(A-\lambda I)&=(3-\lambda)(2-\lambda)(1-\lambda)=0\\
    \lambda&=3,\ 2,\ 1
\end{aligned}
$$

The eigenvalues of $A$ are $3$, $2$, and $1$.
From this example we can infer that the eigenvalues of _any_ triangular matrix are the entries on its diagonal.

---
# Characteristic Polynomials

Observation:
The characteristic equation is _always_ a polynomial. This is why it is also called the characteristic polynomial.

If some characteristic polynomial has degree 3, does it have an eigenvalue?
_Yes_, because eigenvalues occur at the real roots of their characteristic polynomial, and all polynomials of odd degrees have at least one real root by the Intermediate Value Theorem. _(Note that polynomials of even degrees may not have any real roots.)_

__Definition.__ The __(_algebraic_) multiplicity__ of an eigenvalue $\lambda$ is its multiplicity as a root of the characteristic polynomial.
For instance, the characteristic polynomial $(\lambda -2)^2(\lambda -3)$ has two eigenvalues -- 2, which has a multiplicity of 2, and 3, which has a multiplicity of 1.

---
__Ex.__ Find the eigenvalues and their multiplicities from the characteristic polynomial $\lambda^6-4\lambda^5-12\lambda^4$.

$$
\begin{aligned}
    \lambda^6-4\lambda^5-12\lambda^4&=\lambda^4(\lambda^2-4\lambda-12)\\
    &=\lambda^4(\lambda-6)(\lambda+2)\\
    &=0
\end{aligned}
$$

The eigenvalues are 0 (with multiplicity 4), 6 (with multiplicity 1), and -2 (with multiplicity 1).