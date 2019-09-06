# MATH 240
### Fri. September 6th, 2019
---

# Matrix Product
Given a vector $x$ and a matrix $A$, we want to define their product $Ax$. _(This operation can be used to represent things like rotations in video games.)_

$$
\begin{gathered}
    A=\begin{pmatrix}
        3&2&1\\4&5&6\\1&4&3
    \end{pmatrix}, \ x=\begin{pmatrix}
        1\\2\\3
    \end{pmatrix}\\
    Ax=\begin{pmatrix}
        3&2&1\\4&5&6\\1&4&3
    \end{pmatrix}
    \begin{pmatrix}
        1\\2\\3
    \end{pmatrix}
\end{gathered}
$$
Rotate each row of the matrix so it becomes a column, then multiply that column element-wise with the vector and add the results.
$$
\begin{aligned}
    Ax&=\begin{pmatrix}
        3(1) + 2(2) + 1(3)\\
        4(1) + 5(2) + 6(3)\\
        1(1) + 4(2) + 3(3)
    \end{pmatrix}\\
    &=\begin{pmatrix}
        3+4+3\\4+10+18\\1+8+9
    \end{pmatrix}\\
    &=\begin{pmatrix}
        10\\32\\18
    \end{pmatrix}
\end{aligned}
$$
The number of __columns__ in the matrix must be the same as the number of __rows__ in the vector for this operation to be defined.

If $A$ is a $n$ by $m$ matrix with columns $a_1... a_n$ and $x$ is a column vector with length $m$, then
$$
Ax=x_1a_1+...+x_na_n=b,
$$

whose solution set is the same as the solution set of the equations whose augmented matrix is $\begin{bmatrix}
    a_1...a_n,b
\end{bmatrix}$.

---
__Ex.__ Let $A=\begin{pmatrix}
    1&3&4\\-4&2&-6\\-3&-2&-7
\end{pmatrix}$.

Can we choose $b$ in $\R^3$ in an arbitrary manner and still have $Ax=b$ be consistent? (This is __logically equivalent__ to the question, _"Do the columns of $A$ span $\R^3$?"_)

$$
\begin{aligned}
    b=&\begin{pmatrix}
        b_1\\b_2\\b_3
    \end{pmatrix}\\
    \text{Augmented matrix: }&\begin{pmatrix}
        1&3&4&b_1\\-4&2&-6&b_2\\-3&-2&-7&b_3
    \end{pmatrix}\\
    =&\begin{pmatrix}
        1&3&4&b_1\\0&14&10&b_2+4b_1\\0&7&5&b_3+3b_1
    \end{pmatrix}\\
    =&\begin{pmatrix}
        1&3&4&b_1\\0&14&10&b_2+4b_1\\0&0&0&b_3+3b_1-\frac{1}{2}(b_2+4b_1)
    \end{pmatrix}
\end{aligned}
$$

Based on the bottom row, we can see that for some choices of $b$, this system will be inconsistent; therefore the columns of $A$ do __not__ span $\R^3$.