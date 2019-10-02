# MATH 240
### Mon. September 30th, 2019
---

# Section 2.3 -- Invertible Matrix Theorem
Let $A$ be a $n\times n$ (__square__) matrix. The following are equivalent (TFAE):

1. $A$ is invertible.
2. $A$ is row equivalent to the identity matrix.
3. $A$ has $n$ pivot positions.
4. The equation $Ax=0$ has only the trivial solution.
5. The columns of $A$ are linearly independent.
6. The linear transformation $x \rightarrow Ax$ is one-to-one.
7. The equation $Ax=b$ has at least one solution for each $b$ in $\R^n$.
8. The columns of $A$ span $\R^n$.
9. The linear transformation $x \rightarrow Ax$ maps $\R^n$ onto $\R^n$.
10. There is an $n\times n$ matrix $C$ such that $CA=I$.
11. There is an $n\times n$ matrix $D$ such that $AD=I$.
12. $A^T$ is an invertible matrix.

_Remember_ -- the fact that these statements are equivalent means that if one of the is true, all of them are true, and if one of them is false, all of them are false.

---
# Application
---
1. Suppose that $A$ and $B$ are square matrices, and $AB=I$.
Now we know that $A$ is invertible and $A^{-1}=B$, and that $B$ is invertible and $B^{-1}=A$.

---
2.
$$A=\begin{pmatrix}
    1&0&0\\0&1&1\\1&1&1
\end{pmatrix}.$$ Is $A$ invertible?
$$\begin{pmatrix}
    1&0&0\\0&1&1\\1&1&1
\end{pmatrix}\rightarrow \begin{pmatrix}
    1&0&0\\0&1&1\\0&0&0
\end{pmatrix}$$
No, because it only has two pivot positions.

---
3.
$$A=\begin{pmatrix}
    1&0&-2\\3&1&-2\\-5&-1&9
\end{pmatrix}.$$ Is $A$ invertible?
$$\begin{pmatrix}
    1&0&-2\\3&1&-2\\-5&-1&9
\end{pmatrix} \rightarrow \begin{pmatrix}
    1&0&-2\\0&1&4\\0&-1&-1
\end{pmatrix} \rightarrow \begin{pmatrix}
    1&0&-2\\0&1&4\\0&0&3
\end{pmatrix}
$$
Yes, because it has three pivot positions.

---
# Invertible Functions
__Definition.__
Let $T: \R^n \rightarrow \R^n$ be a linear transformation. $T$ is invertible if there is some linear transformation $S: \R^n \rightarrow \R^n$ such that $T(S(x))=x$ and $S(T(x))=x$. We usually denote $S$ by $T^{-1}$.

__Theorem.__
Let $T: \R^n \rightarrow \R^n$ be a linear transformation, and let $A$ be the standard matrix for $T$. $T$ is invertible if and only if $A$ is invertible.

---
## True or False:
Let $T$ be a linear transformation from $\R^n$ to $\R^n$.
1. $T$ can be one-to-one but not onto.
    - _False_. Let $A$ be the standard matrix for $T$. If $T$ is one-to-one, then $T$ is also onto by the 6th and 9th entry in the Invertible Matrix Theorem.
2. $T$ can be onto but not one-to-one.
    - _False_. Similarly, if $T$ onto, then $T$ is also one-to-one by the same theorem.

Note that these are only false because we know $T$ is from $\R^n$ to $\R^n$, i.e. its standard matrix is __square__.
