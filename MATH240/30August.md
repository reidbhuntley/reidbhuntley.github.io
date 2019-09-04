# MATH 240
### Fri. August 30th, 2019
---

# Chap. 1.2
---

__Basic variable__ -- variables in a pivot column in reduced echelon form
__Free variable__ -- any non-basic variable

Find the general solution:
$$
\begin{aligned}
    \begin{pmatrix}
        1&6&2&-5&-2&-4\\
        0&0&2&-8&-1&3\\
        0&0&0&0&1&7
    \end{pmatrix}\\
    R_2 + R_3\rightarrow
    \begin{pmatrix}
        1&6&2&-5&-2&-4\\
        0&0&2&-8&0&10\\
        0&0&0&0&1&7
    \end{pmatrix}\\
    R_1 + 2R_3\rightarrow
    \begin{pmatrix}
        1&6&2&-5&0&10\\
        0&0&2&-8&0&10\\
        0&0&0&0&1&7
    \end{pmatrix}\\
    R_2 * \frac{1}{2}\rightarrow
    \begin{pmatrix}
        1&6&2&-5&0&10\\
        0&0&1&-4&0&5\\
        0&0&0&0&1&7
    \end{pmatrix}\\
    R_1 - 2R_2\rightarrow
    \begin{pmatrix}
        1&6&0&3&0&0\\
        0&0&1&-4&0&5\\
        0&0&0&0&1&7
    \end{pmatrix}
\end{aligned}
$$
$$
\begin{cases}
    x_1=-6x_2-3x_4\\
    x_2 \ \text{is free}\\
    x_3=5+4x_4\\
    x_4 \ \text{is free}\\
    x_5=7
\end{cases}
$$

---
A linear system is __consistent__ if and only if the rightmost column of the reduced echelon matrix is _not_ a pivot column.

__If consistent:__ There's only a unique solution if there's no free variables. _(Free variables imply infinite solutions)_

---
## True or false
1. "A matrix can be reduced to different reduced echelon forms." _(FALSE)_
2. "A matrix can be reduced to different echelon forms." _(TRUE)_
3. "Row reduction only applies to augmented matrices." _(FALSE)_
4. "Basic variables correspond to pivot columns in the augmented matrix." _(FALSE (only true for coefficient matrices))_
5. "If one row of the echelon form of an augmented matrix is $\begin{bmatrix}
    0&0&0&5&0
\end{bmatrix}$, then the solutions are consistent." _(FALSE (can't determine without knowing other rows))_
6. "Whenever a system has free variables, the solution set is infinite." _(FALSE (only true for consistent systems))_
7. "If two systems of linear equations have the same solution set, then the associated row reduced echelon forms of the augmented matrices are the same." _(FALSE)_