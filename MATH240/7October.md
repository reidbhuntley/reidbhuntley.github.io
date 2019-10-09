# MATH 240
### Mon. October 7th, 2019
---

# Applications of the Determinant
---

# Cramer's Rule
Given an $n\times n$ matrix $A$, by $A_{i}(b)$ we denote the matrix obtained by replacing the $i$th column of $A$ with $b$.

__Cramer's Rule:__ Let $A$ be an $n\times n$ _invertible_ matrix. For any $b$ in $\R^n$, the solution to $Ax=b$ is given by $$x_i=\dfrac{\text{det}A_i(b)}{\text{det}A}.$$

This is not very useful for calculations, but makes some theoretical proofs simpler.

__Proof.__ Consider $I_i(x)$.
$$
\begin{aligned}
    I_i(x)&=\begin{pmatrix}
        1&0&...&x_1&...&0\\
        0&1&...&x_2&...&0\\
        ...\\
        0&0&...&x_i&...&0\\
        ...\\
        0&0&...&x_n&...&1\\
    \end{pmatrix}\\
    \\
    \text{det}I_i(x)&=\begin{vmatrix}
        1&0&...&x_1&...&0\\
        0&1&...&x_2&...&0\\
        ...\\
        0&0&...&x_i&...&0\\
        ...\\
        0&0&...&x_n&...&1\\
    \end{vmatrix}\\
    &=x_i\begin{vmatrix}
        1&0&...&x_1&...&0\\
        0&1&...&x_2&...&0\\
        ...\\
        0&0&...&1&...&0\\
        ...\\
        0&0&...&x_n&...&1\\
    \end{vmatrix}\\
    &=x_i\begin{vmatrix}
        1&0&...&0&...&0\\
        0&1&...&0&...&0\\
        ...\\
        0&0&...&1&...&0\\
        ...\\
        0&0&...&0&...&1\\
    \end{vmatrix}\\
    &=x_i\ \text{det}I_n\\
    &=x_i\\
    \\
    AI_i(x)&=A\begin{bmatrix}
        e_1&e_2&...&x&e_{i+1}&...&e_n
    \end{bmatrix}\\
    &=\begin{bmatrix}
        Ae_1&Ae_2&...&Ax&Ae_{i+1}&...&Ae_n
    \end{bmatrix}\\
    &=\begin{bmatrix}
        Ae_1&Ae_2&...&b&Ae_{i+1}&...&Ae_n
    \end{bmatrix}\\
    &=A_i(b)\\
    \\
    \text{det}A_i(b)&=\text{det}AI_i(x)\\
    &=\text{det}A\ \text{det}I_i(x)\\
    &=x_i\text{det}A\\
    \\
    x_i&=\dfrac{\text{det}A_i(b)}{\text{det}A}.
\end{aligned}
$$

---
__Ex.__ Let $s$ be a parameter
$$
\begin{cases}
    3sx_1-2x_2=4\\-6x_1+sx_2=1
\end{cases}
$$
and assume that the system has a _unique_ solution.
$$
\begin{aligned}
    A&=\begin{pmatrix}
        3s&-2\\-6&s
    \end{pmatrix}\\
    \text{det}A&=3s^2-12\\
    &=3(s^2-4)\\
    &=3(s-2)(s+2)\\
    s&\neq 2,-2\\
    \\
    A_1(b)&=\begin{pmatrix}
        4&-2\\1&s
    \end{pmatrix}\\
    \text{det}A_1(b)&=4s+2\\
    \\
    A_2(b)&=\begin{pmatrix}
        3s&4\\-6&1
    \end{pmatrix}\\
    \text{det}A_2(b)&=3s+24\\
\end{aligned}
$$

By Cramer's Rule:
$$
\begin{aligned}
    x_1&=\dfrac{4s+2}{3(s-2)(s+2)}\\
    x_2&=\dfrac{3s+24}{3(s-2)(s+2)}
\end{aligned}
$$

---
Cramer's Rule also provides a formula to find the inverse of matrices. _(You really shouldn't use this for computations because it's harder than other methods we've learned.)_
$$
A^{-1}=\dfrac{1}{\text{det}A}\begin{pmatrix}
    C_11&C_21&...&C_n1\\
    C_12&C_22&...&C_n2\\
    ...\\
    C_1n&C_2n&...&Cnn
\end{pmatrix}
$$
where $C_ij$ are cofactors that were defined previously. (The matrix on the right here is called the _classical adjoint of $A$._)

---
# Geometric Applications
If $A$ is a $2\times 2$ matrix, the area of the parallelogram _determined_ by the columns of $A$ is $\mid\text{det}A\mid$. This also applies to the volume of parallelopipeds for $3\times 3$ matrices, and for higher-dimensional equivalents of parallelograms and volume for larger square matrices.

By _determined_ by the columns of $A$, we mean the parallelogram that has $(0,0)$ and each column of $A$ as vertices. The remaning vertices can be determined from this information.

---
Let $T: \R^2\rightarrow\R^2$ be a linear transformation determined by the matrix $A$. If $S$ is an _object_ in $\R^2$ with _finite area_, then the area of $T(S)$ is the product of $\mid\text{det}A\mid$ and the area of $S$. ($T(S)$ means applying $T$ to every point in $S$.)