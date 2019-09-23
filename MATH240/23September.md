# MATH 240
### Mon. September 23rd, 2019
---

# Matrix Inverse
* We'll be looking at __square matrices__ only in these cases
* Reminder that for matrices $A$, $B$, $AB$ does not necessarily equal $BA$

For a matrix $A$, the its inverse $A^{-1}$ should have the following property: $
A^{-1}A=AA^{-1}=I_n.
$

---
__Ex.__ Determine if
$$
\begin{aligned}
    A&=\begin{pmatrix}
        2&5\\-3&-7
    \end{pmatrix},\\
    B&=\begin{pmatrix}
        -7&5\\3&2
    \end{pmatrix}
\end{aligned}
$$ are inverses of each other.

$$
\begin{aligned}
    AB&=\begin{pmatrix}
        2&5\\-3&-7
    \end{pmatrix}\begin{pmatrix}
        -7&5\\3&2
    \end{pmatrix}\\
    &=\begin{pmatrix}
        1&0\\0&1
    \end{pmatrix}\\
    &=I_2.
\end{aligned}
$$

Therefore, $B=A^{-1}$ and $A=B^{-1}$.

---
## Application
If we had the equation $5x=1$, we would solve it by multiplying both sides by $\frac{1}{5}$, the multiplicative inverse of 5. We can use an analogous operation to solve systems of linear equations.

Suppose that $A$ is an invertible matrix. Then the equation $Ax=b$ has a unique solution given by $x=A^{-1}b$. We can prove this using properties of matrix multiplication:

$$
\begin{aligned}
    Ax&=b\\
    A^{-1}(Ax)&=A^{-1}b\\
    (A^{-1}A)x&=A^{-1}b\\
    I_nx&=A^{-1}b\\
    x&=A^{-1}b.
\end{aligned}
$$

---
##  Finding the Inverse of 2x2 Matrices
In the case of a 2x2 matrix $
A=\begin{pmatrix}
    a&b\\c&d
\end{pmatrix}
$, if $ad-bc\neq 0$, then $A$ has an inverse, which is given by
$$
A^{-1}=\frac{1}{ad-bc}\begin{pmatrix}
    d&-b\\-c&a
\end{pmatrix}.
$$

__Ex.__ Is $
    \begin{pmatrix}
        5&3\\4&8
    \end{pmatrix}
$ invertible? $
(5)(8)-(3)(4)=28\neq 0,
$ so it _is_ invertible.


---
## Finding the Inverse of Larger Matrices

You can also find the inverse of a matrix by putting an identity matrix to the right of it and row-reducing the left matrix into the identity matrix. Afterwards, the right matrix will be the inverse of the original left matrix.

(__Any invertible matrix will be row-equivalent to the identity matrix.__ If you _can't_ row-reduce a matrix into the identity matrix, then it's non-invertible.)

__Ex.__ Find the inverse of $A$.
$$
\begin{aligned}
    A=&\begin{pmatrix}
        0&1&2\\1&0&3\\4&-3&8
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        0&1&2&1&0&0\\1&0&3&0&1&0\\4&-3&8&0&0&1
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        1&0&3&0&1&0\\0&1&2&1&0&0\\4&-3&8&0&0&1
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        1&0&3&0&1&0\\0&1&2&1&0&0\\0&-3&-4&0&-4&1
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        1&0&3&0&1&0\\0&1&2&1&0&0\\0&0&2&3&-4&1
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        1&0&3&0&1&0\\0&1&2&1&0&0\\0&0&1&\frac{3}{2}&-2&\frac{1}{2}
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        1&0&3&0&1&0\\0&1&0&-2&4&-1\\0&0&1&\frac{3}{2}&-2&\frac{1}{2}
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        1&0&0&-\frac{9}{2}&7&-\frac{3}{2}\\0&1&0&-2&4&-1\\0&0&1&\frac{3}{2}&-2&\frac{1}{2}
    \end{pmatrix}
\end{aligned}
$$

Now that the left side is $I_3$, the right side must be $A^{-1}$, so
$$
A^{-1}=\begin{pmatrix}
    -\frac{9}{2}&7&-\frac{3}{2}\\-2&4&-1\\\frac{3}{2}&-2&\frac{1}{2}
\end{pmatrix}.
$$
