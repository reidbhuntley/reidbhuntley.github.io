# MATH 240
### Wed. October 2nd, 2019
---

# Determinants

Let $A=\begin{pmatrix}
    a&b\\b&c
\end{pmatrix}$ be a $2\times 2$ matrix. If $ad=bc\neq 0$, then $A$ is invertible. Further, if $ad-bc=0$, then $A$ is _not_ invertible.

This means that there is one number associated with each $2\times 2$ matrix that determines whether it is invertible or not. This number turns out to exist for any $n\times n$ matrix as well.

For any $n\times n$ square matrix $A$, let $A_{ij}$ denote the $n-1\times n-1$ submatrix of $A$ obtained by removing the $i$th row and the $j$th column of $A$.

__Ex.__
$$
\begin{aligned}
    A&=\begin{pmatrix}
        4&1&3&7\\
        2&2&1&4\\
        3&2&1&3\\
        4&4&5&7
    \end{pmatrix}\\
    A_{12}&=\begin{pmatrix}
        2&1&4\\
        3&1&3\\
        4&5&7
    \end{pmatrix}
\end{aligned}
$$

For $n>2$, the __determinant__ of an $n\times n$ matrix $A$ whose entries are denoted as $a_{ij}$ is given by
$$
\text{det}A=a_{11}\text{det}A_{11}-a_{12}\text{det}A_{12}+...+(-1)^{n+1}a_{1n}\text{det}A_{1n},
$$ or, more compactly,
$$
\text{det}A=\sum_{j=1}^n \ (-1)^{1+j} \ a_{1j} \ \text{det}A_{1j}.
$$

---
## Solving for the Determinant

__Ex.__ $$A=\begin{pmatrix}
        1&5&0\\2&4&-1\\0&-2&0
    \end{pmatrix}$$

$$
\begin{aligned}
    \text{det}A&=(-1)^2 \ a_{11} \ \text{det}A_{11}+(-1)^3 \ a_{12} \ \text{det}A_{12}+(-1)^4 \ a_{13} \ \text{det}A_{13}\\
    &=1 \ \text{det}\begin{pmatrix}
        4&-1\\-2&0
    \end{pmatrix}-5 \ \text{det}\begin{pmatrix}
        2&-1\\0&0
    \end{pmatrix}+0 \ \text{det}\begin{pmatrix}
        2&4\\0&-2
    \end{pmatrix}\\
    &=1(0-2)-5(0-0)+0\\
    &=-2.
\end{aligned}
$$

---
## Cofactors

Given an $n\times n$ matrix $A$, let $C_{ij}=(-1)^{i+j} \ \text{det}A_{ij}$. The determinant of $A$ now becomes
$$
\text{det}A=a_{11}C_{11}+a_{12}C_{12}+...+a_{1n}C_{1n}.
$$ These $C$-matrices are known as __cofactors__ of $A$.

---
__Theorem__: The determinant of a $n\times n$ matrix $A$ can be computed by a cofactor expansion
$$
\text{det}A=a_{j1}C_{j1}+a_{j2}C_{j2}+...+a_{jn}C_{jn}
$$
or
$$
\text{det}A=a_{1j}C_{1j}+a_{2j}C_{2j}+...+a_{nj}C_{nj}.
$$

This means the determinant can be computed across _any_ row or column, rather than just the first row as shown previously. Because of this, we can speed up the expensive computation required to find the determinant by computing across a row or column with many zeroes.

__Ex.__ We can more quickly find the determinant of the matrix from the previous example by computing along the _third row_ instead of the first. $$A=\begin{pmatrix}
        1&5&0\\2&4&-1\\0&-2&0
    \end{pmatrix}$$

$$
\begin{aligned}
    \text{det}A&=(-1)^4 \ a_{31} \ \text{det}A_{31}+(-1)^5 \ a_{32} \ \text{det}A_{32}+(-1)^6 \ a_{33} \ \text{det}A_{33}\\
    &=0 \ \text{det}\begin{pmatrix}
        5&0\\4&-1
    \end{pmatrix}+2 \ \text{det}\begin{pmatrix}
        1&0\\2&-1
    \end{pmatrix}+0 \ \text{det}\begin{pmatrix}
        1&5\\2&4
    \end{pmatrix}\\
    &=0+2(-1-0)+0\\
    &=-2.
\end{aligned}
$$

---
## Determinant of Diagonal Matrices

__Definition.__ A _diagonal matrix_ is a matrix where all of the non-diagonal entries are zero.

For a diagonal matrix $A$, the determinant of $A$ is the product of its diagonal entries.

__Ex.__
$$
\begin{aligned}
    A&=\begin{pmatrix}
        1&0&0&0&0\\0&2&0&0&0\\0&0&3&0&0\\0&0&0&4&0\\0&0&0&0&5
    \end{pmatrix}\\
    \text{det}A&=(1)(2)(3)(4)(5)\\
    &=120.
\end{aligned}
$$