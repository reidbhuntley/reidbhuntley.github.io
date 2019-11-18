# MATH 240
### Wed. November 13th, 2019
---

Recall that knowing eigenvalues and their corresponding eigenvectors of $A$ gives us an idea of what happens to those vectors under repeated application of the transformation associated with $A$. _(They'll just be scaled by their corresponding eigenvalue each time.)_

What sort of effect does a matrix $A$ with _no real eigenvalues_ have if it is "applied repeatedly" to a point $x_0$ in $\R^n$? ($x_0,\ Ax_0,\ A^2x_0,\ A^3x_0,\ ...$)

_Note._ For convenience we will only consider $2\times 2$ matrices.

We can essentially represent each of these transformations as a scaling and rotating of $x_0$ by constant values.

---
__The Factor Theorem__ -- Any polynomial of degree $n$ with complex coefficients has $n$ complex roots (counting multiplicities).
$Q(\lambda)=k_1\lambda^n+k_2\lambda^{n-1}...+k_n\lambda^0=(\lambda-\lambda_1)(\lambda-\lambda_2)...(\lambda-\lambda_n)$

A $2\times 2$ matrix $A$ will _always_ have eigenvalues if you consider it as a matrix over the complex numbers. We can treat $A$ as a transformation from $\cnums^2$ to $\cnums^2$.

---
__Ex.__
$$
\begin{aligned}
    A&=\begin{pmatrix}
        0&-1\\1&0
    \end{pmatrix}\\
    \text{det}(A-\lambda I)&=\begin{vmatrix}
        -\lambda&-1\\1&-\lambda
    \end{vmatrix}\\
    &=\lambda^2+1=0\\
    \lambda&=i,-i
\end{aligned}
$$$$
\begin{pmatrix}
    0&-1\\1&0
\end{pmatrix}\begin{pmatrix}
    1\\-i
\end{pmatrix}=\begin{pmatrix}
    i\\1
\end{pmatrix}=i\begin{pmatrix}
    1\\-i
\end{pmatrix}
$$ Thus $v_1=\begin{pmatrix}
    1\\-i
\end{pmatrix}$ is an eigenvector that corresponds to $\lambda=i$.$$
\begin{pmatrix}
    0&-1\\1&0
\end{pmatrix}\begin{pmatrix}
    1\\i
\end{pmatrix}=\begin{pmatrix}
    -i\\1
\end{pmatrix}=-i\begin{pmatrix}
    1\\i
\end{pmatrix}
$$ Thus $v_2=\begin{pmatrix}
    1\\i
\end{pmatrix}$ is an eigenvector that corresponds to $\lambda=-i$.

---
__Ex.__
$$
\begin{aligned}
    A&=\begin{pmatrix}
        .5&-.6\\.75&1.1
    \end{pmatrix}\\
    \text{det}(A-\lambda I)&=\lambda^2-1.6\lambda+1\\
    \lambda&=\frac{1.6\pm \sqrt{(1.6)^2-4}}{2}\\
    &=.8\pm.6i
\end{aligned}
$$

Now we look at $(A-\lambda I)x=0$ and split each row into its own equation.
$$
\begin{gathered}
    &(-.3+.6i)x_1-.6x_2=0\\
    &.75x_1+(.3+.6i)x_2=0
\end{gathered}
$$$$
\begin{aligned}
    .75x_1&=-(.3+.6i)x_2\\
    x_1&=(-.4-.8i)x_2
\end{aligned}
$$
One of these will be a free variable. We can choose $x_2=5$ to find our eigenvectors:
$$
\begin{aligned}
    v_1&=\begin{pmatrix}
        -2-4i\\5
    \end{pmatrix}\text{(for $\lambda=.8-.6i$)}\\
    v_2&=\begin{pmatrix}
        -2+4i\\5
    \end{pmatrix}\text{(for $\lambda=.8+.6i$)}
\end{aligned}
$$ If you know that a vector $v$ is an eigenvector for a complex eigenvalue $\lambda$, then the conjugate of $v$ is an eigenvector for the conjugate of $\lambda$. (The conjugate is obtained by $\text{Re}(x)-\text{Im}(x)$)