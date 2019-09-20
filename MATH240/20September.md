# MATH 240
### Fri. September 20th, 2019
---

# Matrix Operations

## Addition
Matrices of the same dimentions can be added together element-wise.

## Scaling
Multiplying a matrix by a scalar multiplies every element of the matrix by that scalar.

## Multiplication
For two matrices $A,B$, for $AB$ to be defined, the number of _columns_ in $A$ must be the same as the number of _rows_ in $B$.

If $A$ is $m\times n$ and $B$ is $n\times p$, then $AB$ will be $m\times p$.

If you lay the $i$th _row_ of $A$ over the $j$th _column_ of $B$, multiply element-wise, and add the results together, you get element $i,j$ of $AB$.

__Ex.__
$$
\begin{aligned}
    A&=\begin{pmatrix}
        2&3\\1&-5
    \end{pmatrix}\\
    B&=\begin{pmatrix}
        4&3&6\\1&-2&3
    \end{pmatrix}\\ 
    \\
    AB&=\begin{pmatrix}
        2(4)+3(1)&2(3)+3(-2)&2(6)+3(3)\\
        1(4)+(-5)(1)&1(3)+(-5)(-2)&1(6)+(-5)(3)
    \end{pmatrix}\\
    &=\begin{pmatrix}
        11&0&21\\-1&13&-9
    \end{pmatrix}
\end{aligned}
$$

## Transpose
For a matrix $A$, its transpose $A^T$ is the matrix whose _columns_ are the _rows_ of $A$.

__Ex.__
$$
\begin{aligned}
    A&=\begin{pmatrix}
        a&b\\c&d
    \end{pmatrix}\\
    A^T&=\begin{pmatrix}
        a&c\\b&d
    \end{pmatrix}
\end{aligned}
$$

# Properties of Matrix Operations
If $A,B,C$ are matrices, $r,s$ are scalars, and $I_m$ is an identity matrix:
$$
\begin{aligned}
    A+B&=B+A\\
    (A+B)+C&=A+(B+C)\\
    A+0&=A\\
    r(A+B)&=rA+rB\\
    (r+s)A&=rA+sA\\
    (rs)A&=r(sA)\\
    \\
    A(BC)&=(AB)C\\
    A(B+C)&=AB+AC\\
    (B+C)A&=BA+CA\\
    r(AB)&=(rA)B=A(rB)\\
    I_mA&=A=AI_m\\
    \\
    (A^T)^T&=A\\
    (A+B)^T&=A^T+B^T\\
    (AB)^T&=B^TA^T.
\end{aligned}
$$

Note that $AB=BA$ is __not necessarily true!__ (Matrix multiplication is __not commutative__.)

# Identity Matrices
An identity matrix $I_m$ is a $m\times m$ matrix with $1$s along the diagonal and $0$s everywhere else.

__Ex.__
$$
I_4=\begin{pmatrix}
    1&0&0&0\\0&1&0&0\\0&0&1&0\\0&0&0&1
\end{pmatrix}
$$

This acts as an analogue to $1$ for matrices -- it is the __multiplicative identity__.