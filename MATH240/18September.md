# MATH 240
### Wed. September 18th, 2019
---

# Linear Transformations (cont.)

$e_i$ is defined as the column vector where the $i$th element is 1 and all others are 0.
Ex. $e_2$ in $\R^3$ is $\begin{pmatrix}
    0\\1\\0
\end{pmatrix}$.

---
## Theorem.

$$
\begin{aligned}
    x&=\begin{pmatrix}
        x_1\\x_2\\...\\x_n
    \end{pmatrix}\\
    &=\begin{pmatrix}
        x_1\\0\\...\\0
    \end{pmatrix}+\begin{pmatrix}
        0\\x_2\\...\\0
    \end{pmatrix}+...+\begin{pmatrix}
        0\\0\\...\\x_n
    \end{pmatrix}\\
    &=x_1e_1+x_2e_2+...+x_ne_n\\
    \\
    T(x)&=T(x_1e_1+x_2e_2+...+x_ne_n)\\
    &=T(x_1e_1)+T(x_2e_2)+...+T(x_ne_n)\\
    &=x_1T(e_1)+x_2T(e_2)+...+x_nT(e_n)\\
    &=\begin{bmatrix}
        T(e_1)&T(e_2)&...&T(e_n)
    \end{bmatrix}\begin{pmatrix}
        x_1\\x_2\\...\\x_n
    \end{pmatrix}\\
    &=Ax.
\end{aligned}
$$
The matrix $A$ in this case is called the __standard matrix__ for $T$.

This theorem tells us that all we don't have to know what happens to every possible input vector to describe the linear transformation; we just have to know what happens to the $e_i$ vectors.

---
__Ex.__ For some linear transformation $T$, the following are true:
$$
\begin{aligned}
    T\begin{pmatrix}
        1\\0\\0
    \end{pmatrix}&=\begin{pmatrix}
        0\\0\\1
    \end{pmatrix}\\
    T\begin{pmatrix}
        0\\1\\0
    \end{pmatrix}&=\begin{pmatrix}
        1\\0\\0
    \end{pmatrix}\\
    T\begin{pmatrix}
        0\\0\\1
    \end{pmatrix}&=\begin{pmatrix}
        0\\1\\0
    \end{pmatrix}
\end{aligned}
$$
The standard matrix $A$ of this transformation $T$ is $\begin{bmatrix}
    T(e_1)&T(e_2)&T(e_3)
\end{bmatrix}$, which is just 
$$
\begin{pmatrix}
    0&1&0\\0&0&1\\1&0&0
\end{pmatrix}
$$
based on the assertions above.

---
# Onto Functions
A linear transformation $T: \R^n \rightarrow \R^m$ is __onto__ if, for any $b$ in $\R^m$, there is an $x$ in $\R^n$ such that $T(x)=b$.

__Ex.__ $T: \R^3 \rightarrow \R^2, \ T(x)=\begin{pmatrix}
    1&0&0\\0&1&0
\end{pmatrix}x.$ Is $T$ onto?
Yes, because this is equivalent to asking whether $Ax=b$ will always have a solution. $A$ has a pivot position in every row, so its columns span $\R^2$, so its associated function $T$ is onto.

---
# One-to-One Functions
A linear transformation $T: \R^n \rightarrow \R^m$ is __one-to-one__ if $T(v_1)=T(v_2)$ _implies_ that $v_1=v_2$ (i.e., its inverse will also be a function).

Using the linear transformation from the previous example, $$T\begin{pmatrix}
    1\\2\\3
\end{pmatrix}=\begin{pmatrix}
    1\\2
\end{pmatrix}$$ and $$T\begin{pmatrix}
    1\\2\\4
\end{pmatrix}=\begin{pmatrix}
    1\\2
\end{pmatrix},$$ but $$\begin{pmatrix}
    1\\2\\3
\end{pmatrix}\neq \begin{pmatrix}
    1\\2\\4
\end{pmatrix};$$ therefore, $T$ is _not_ one-to-one.

If $T(x)=0$ has only the trivial solution, then $T$ is one-to-one. __This is the same definition as linear independence for the column vectors of the standard matrix of T!__
