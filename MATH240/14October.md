# MATH 240
### Mon. October 14th, 2019
---
## Identifying Subspaces
Let $H$ be a subset of a vector space $V$. We have two main methods of determining if $H$ is a subspace of $V$:
* __Method I:__
    - Determine that $0$ is in $H$
    - Determine that if $u,v$ are in $H$, then $u+v$ is also in $H$ _(closed under addition)_
    - Determine that if $u$ is in $H$ and $c$ is any scalar, then $cu$ is also in $H$ _(closed under scalar multiplication)_
* __Method II:__
    - Find a set of vectors in $V$ that span $H$.
    - "__Theorem.__ The span of any collection of vectors from $V$ is a subspace of $V$."

---
# Null and Column Spaces
There are some "natural" subspaces that are worth examining:

Let $A$ be an $m\times n$ matrix. Recall that $x\rightarrow Ax$ is a linear transformation from $\R^n$ to $\R^m$.

# Null Space
__Claim__ $\text{Nul}A=\{x:Ax=0\mid x\ \text{in} \ \R^n\}$ (the _null space_ of $A$) is a subspace of $\R^n$:
1. $A0=0$, so $0$ is in $\text{Nul}A$.
2. If $u,v$ are in $\text{Nul}A$, then $u+v$ is also in $\text{Nul}A$.
    - $Au=0$
    - $Av=0$
    - $A(u+v)=Au+Av=0+0=0$
3. If $u$ is in $\text{Nul}A$ and $c$ is any scalar, then $cu$ is also in $\text{Nul}A$.
    - $Au=0$
    - $A(cu)=c(Au)=c(0)=0$

Thus $\text{Nul}A$ _is_ a subspace of $\R^n$.

$x\rightarrow Ax$ is one-to-one iff $Ax=0$ has only the trivial solution. This is equivalent to $\text{Nul}A$ containing only the zero vector.

# Column Space
__Claim__ $\text{Col}A=\text{span}\{a_1,...,a_n\}$ where $A=[a_1,...,a_n]$ (the _column space_ of $A$) is a subspace of $\R^m$:
* $a_1,...,a_n$ are all vectors in $\R^m$, thus $\text{Col}A=\text{span}\{a_1,...,a_n\}$ is a subspace of $\R^m$ by the previously stated theorem.

If $v$ is in $\R^m$, then how would we determine if there is some $x$ in $\R^m$ such that $Ax=v$?
We'd determine if $v$ is in the span of the columns of $A$, which is equivalent to $v$ being in $\text{Col}A$. Thus $\text{Col}A$ can be thought of as the _image_ of $\R^m$ under the mapping $x\rightarrow Ax$.

---
__Ex.__ Find a spanning set for $\text{Nul}A$ where $$A=\begin{pmatrix}
    -3&6&-1&1&-7\\
    1&-2&2&3&-1\\
    2&-4&5&8&-4
\end{pmatrix}$$ This is equivalent to solving $Ax=0$.
$$
\begin{aligned}
    &\rightarrow \begin{pmatrix}
        -3&6&-1&1&-7&0\\
        1&-2&2&3&-1&0\\
        2&-4&5&8&-4&0
    \end{pmatrix}\\
    &\rightarrow \begin{pmatrix}
        1&-2&2&3&-1&0\\
        -3&6&-1&1&-7&0\\
        2&-4&5&8&-4&0
    \end{pmatrix}\\
    &\rightarrow \begin{pmatrix}
        1&-2&2&3&-1&0\\
        0&0&5&10&-10&0\\
        0&0&1&2&-2&0
    \end{pmatrix}\\
    &\rightarrow \begin{pmatrix}
        1&-2&2&3&-1&0\\
        0&0&1&2&-2&0\\
        0&0&0&0&0&0
    \end{pmatrix}\\
    &\rightarrow \begin{pmatrix}
        1&-2&0&-1&3&0\\
        0&0&1&2&-2&0\\
        0&0&0&0&0&0
    \end{pmatrix}\\\\
    \begin{pmatrix}
        x_1\\x_2\\x_3\\x_4\\x_5
    \end{pmatrix}&=\begin{pmatrix}
        2x_2+x_4-3x_5\\x_2\\-2x_4+2x_5\\x_4\\x_5
    \end{pmatrix}\\
    &=x_2\begin{pmatrix}
        2\\1\\0\\0\\0
    \end{pmatrix}+x_4\begin{pmatrix}
        1\\0\\-2\\1\\0
    \end{pmatrix}+x_5\begin{pmatrix}
        -3\\0\\2\\0\\1
    \end{pmatrix}
\end{aligned}
$$
Thus the null space is spanned by these three vectors.

---
__Ex.__ Let $T:\R^3\rightarrow \R^3$ be $$T\begin{pmatrix}
    x\\y\\z
\end{pmatrix}=\begin{pmatrix}
    x\\y\\0
\end{pmatrix}$$

The _null space_ of the standard matrix of $T$ is $$\{\begin{pmatrix}
    0\\0\\z
\end{pmatrix} \mid z \ \text{in} \ \R\}
$$

The _column space_ of the standard matrix of $T$ is the entire $xy$ plane.