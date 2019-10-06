# MATH 240
### Fri. October 4th, 2019
---

# Triangular Matrices
__Definition.__ A matrix is __upper triangular__ if everything _below_ the main diagonal is 0. (Entries on and above the main diagonal may or may not be zeroes). 

Similarly, a matrix is __lower triangular__ if everything _above_ the main diagonal is 0. (Entries on and below the main diagonal may or may not be zeroes).

## Determinant of Triangular Matrices
Let $A$ be a triangular matrix.
$$
\text{det}A=a_{11}a_{22}...a_{nn}=\prod_{i=1}^na_{ii}.
$$ This is the same computation used to find the determinant of a diagonal matrix.

---
# Simplifying Determinant Computations

__Theorem.__ Let $A$ be a square matrix.
1. If a multiple of one row of $A$ is added to another row to form a matrix $B$, then $\text{det}B=\text{det}A$.
2. If two rows of $A$ are interchanged to produce $B$, then $\text{det}B=-\text{det}A$.
3. If one row of $A$ is multiplied by $k$ to produce $B$, then $\text{det}B=k\ \text{det}A$

By row-reducing a matrix into an upper triangular matrix and keeping these rules in mind, we can find its determinant much more quickly.

__Ex.__
$$
\begin{aligned}
    A&=\begin{pmatrix}
        1&-4&-2\\-2&8&9\\-1&7&0
    \end{pmatrix}\\
    \text{det}A&=\begin{vmatrix}
        1&-4&-2\\-2&8&9\\-1&7&0
    \end{vmatrix}\\
    &=\begin{vmatrix}
        1&-4&-2\\0&0&5\\-1&7&0
    \end{vmatrix}\\
    &=-\begin{vmatrix}
        1&-4&-2\\-1&7&0\\0&0&5
    \end{vmatrix}\\
    &=-\begin{vmatrix}
        1&-4&-2\\0&3&-2\\0&0&5
    \end{vmatrix}\\
    &=-(1)(3)(5)\\
    &=-15.
\end{aligned}
$$

$$
\begin{aligned}
    B&=\begin{pmatrix}
        1&-4&-2\\-1&7&0\\-2&8&9
    \end{pmatrix}\\
    \text{det}B&=\begin{vmatrix}
        1&-4&-2\\-1&7&0\\-2&8&9
    \end{vmatrix}\\
    &=-\begin{vmatrix}
        1&-4&-2\\-2&8&9\\-1&7&0
    \end{vmatrix}\\
    &=-\text{det}A\\
    &=-(-15)\\
    &=15.
\end{aligned}
$$

---
# More Theorems Related to the Determinant

__Theorem.__ Let $A$ be a square matrix.
1. $A$ is invertible if and only if $\text{det}A\neq 0$.
2. $\text{det}A^T=\text{det}A$.
3. $\text{det}AB=\text{det}A\ \text{det}B$.

---
# Rotation Matrices
$$
\begin{aligned}
    A&=\begin{pmatrix}
        \cos{\theta}&-\sin{\theta}\\
        \sin{\theta}&\cos{\theta}
    \end{pmatrix}\\
    B&=\begin{pmatrix}
        \cos{\psi}&-\sin{\psi}\\
        \sin{\psi}&\cos{\psi}
    \end{pmatrix}\\
    AB&=\begin{pmatrix}
        \cos{\theta}\cos{\psi}-\sin{\theta}\sin{\psi}&
        -\cos{\theta}\sin{\psi}-\sin{\theta}\cos{\psi}\\
        \sin{\theta}\cos{\psi}+\cos{\theta}\sin{\psi}&
        -\sin{\theta}\sin{\psi}+\cos{\theta}\cos{\psi}
    \end{pmatrix}\\
    &=\begin{pmatrix}
        \cos{(\theta+\psi)}&
        -\sin{(\theta+\psi)}\\
        \sin{(\theta+\psi)}&
        \cos{(\theta+\psi)}
    \end{pmatrix}
\end{aligned}
$$ This result maxes sense because multiplying the matrices is essentially combining the two rotations, which produces a new rotation matrix of the two angles added together.
$$
\begin{aligned}
    \text{det}A&=\cos^2{\theta}+\sin^2{\theta}=1\\
    \text{det}B&=\cos^2{\psi}+\sin^2{\psi}=1\\
    \text{det}AB&=\text{det}A\ \text{det}B=1.
\end{aligned}
$$
