# MATH 240
### Mon. September 9th, 2019
---

## Why work in the abstract?

Many different types of problems can be represented as __systems of linear equations__, and many operations can be represented as __linear transformations__. By working in the abstract, we only have to learn a small number of techniques to work with this wide variety of equivalent problems.

---

__Ex.__ Every _quadratic equation_ can be represented as $c_0+c_1x+c_2x^2$. The only thing that changes between them is the values of the coefficients, which can be represented as a vector $$\begin{pmatrix}
    c_1\\c_2\\c_3
\end{pmatrix}.$$ This implies that we can use linear algebra to answer questions about quadratic equations.

This idea can also be extended to polynomials of any degree. When working with cubics like $c_0+c_1x+c_2x^2+c_3x^3$, they can be represented by the vector $$\begin{pmatrix}
    c_0\\c_1\\c_2\\c_3
\end{pmatrix}.$$ If you wanted to represent only the quadratics within this vector space, you could use $$\text{Span}\{\begin{pmatrix}
    1\\0\\0\\0
\end{pmatrix},\begin{pmatrix}
    0\\1\\0\\0
\end{pmatrix},\begin{pmatrix}
    0\\0\\1\\0
\end{pmatrix}\}.$$
This set will only contain points where $c_3=0$, i.e. cubics where the coefficient of $x^3$ is 0, i.e. quadratics. This demonstrates how looking at span can be useful in a concrete sense.

---
_The question of whether $Ax=b$ has a solution is equivalent to a question regarding the span of the columns that make up $A$._

## Key theorem from Friday:  
Let $A$ be an $m \times n$ matrix. The following are equivalent:
* For each $b$ in $\R^n$, $Ax=b$ has a solution.
* Each $b$ in $\R^n$ is a linear combination of the columns of $A$.
* The columns of $A$ span $\R^n$.
* $A$ has a pivot position in every row.

---
A __homogeneous system of linear equations__ has the form $Ax=0.$ They are _always consistent_ (always have at least one solution), since the __trivial solution__ (where every variable equals 0) will always be a solution.

__Ex.__
$$
\begin{cases}
    3x_1+5x_2-4x_3=0\\
    -3x_1-2x_2+4x_3=0\\
    6x_1+x_2-8x_3=0
\end{cases}
$$
$$
\begin{aligned}
    &\begin{pmatrix}
        3&5&-4&0\\
        -3&-2&4&0\\
        6&1&-8&0
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        3&5&-4&0\\
        0&3&0&0\\
        0&-9&0&0
    \end{pmatrix}\\
    \rightarrow&\begin{pmatrix}
        3&5&-4&0\\
        0&3&0&0\\
        0&0&0&0
    \end{pmatrix}\\
\end{aligned}
$$
$$
\begin{aligned}
    3x_2=0\rightarrow x_2&=0\\
    3x_1+5(0)-4x_3=0\rightarrow x_1&=\frac{4}{3}x_3
\end{aligned}
$$
$$
=\begin{pmatrix}
    \frac{4}{3}x_3\\0\\x_3
\end{pmatrix}=x_3\begin{pmatrix}
    \frac{4}{3}\\0\\1
\end{pmatrix}=\text{Span}\{\begin{pmatrix}
    \frac{4}{3}\\0\\1
\end{pmatrix}\}.
$$