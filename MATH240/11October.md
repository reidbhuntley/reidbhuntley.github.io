# MATH 240
### Fri. October 11th, 2019
---

# Subspaces
__Definition.__ Let $V$ be a vector space and let $H\sube V$ ($H$ is a _subset_ of $V$). We say that $H$ is a subspace of $V$ if all of the following are true:
1. The zero vector 0 is in $H$.
2. If $u,v$ are in $H$, then $u+v$ is in $H$. _(Closure under addition)_
3. If $c$ is any scalar and $u$ is any vector in $H$, then $cu$ is in $H$. _(Closure under scalar multiplication)_

$H=\{0\}$ (the set only containing the zero vector) is always a subset of any vector space $V$, and $V$ is always a subset of itself.

---
Is $\R^2$ a subspace of $\R^3$? __No,__ because elements of $\R^2$ are in the form $\begin{pmatrix}
    a\\b
\end{pmatrix}$, and elements of $\R^3$ are in the form $\begin{pmatrix}
    c\\d\\e
\end{pmatrix}$, which cannot be equal to each other; therefore $\R^2$ is not even a subset of $\R^3$, let alone a subspace. _However_, you can find subspaces within $\R^3$ that _resemble_ $\R^2$.

---
__Ex.__ Verify that $$H=\{\begin{pmatrix}
    s\\t\\0
\end{pmatrix}\mid \ s,t \in \R\}$$ is a subspace of $\R^3$.
1. Note $H$ is a subset of $\R^3$.
2. When $s=t=0$, we get the zero vector $\begin{pmatrix}
    0\\0\\0
\end{pmatrix}$ in $H$.
3. Let $u=\begin{pmatrix}
    s_1\\t_1\\0
\end{pmatrix},\ v=\begin{pmatrix}
    s_2\\t_2\\0
\end{pmatrix}$ be in $H$. $$
    u+v=\begin{pmatrix}
        s_1+s_2\\t_1+t_2\\0
    \end{pmatrix}
$$ so $u+v$ is in $H$.
4. Let $c$ be any real number. $$cu=c\begin{pmatrix}
    s_1\\t_1\\0
\end{pmatrix}=\begin{pmatrix}
    cs_1\\ct_1\\0
\end{pmatrix}
$$ so $cu$ is in $H$.

Thus $H$ is a subspace of $\R^3$.

---
Recall that $C^\infin(\R)$ is the set of infinitely differentiable functions on the reals.
Is $P$, the collection of all polynomials, a subspace of $C^\infin(\R)$?
1. Any polynomial can be differentiated as many times as you want, so $P$ is a subset of $C^\infin(\R)$.
2. $f(x)=0$ for all $x$ is a polynomial, so $0$ is in $P$.
3. The sum of two polynomials is also a polynomial, so $P$ is closed under addition.
4. The product of a scalar and any polynomial is also a polynomial, so $P$ is closed under scalar multiplication.

Thus $P$ is a subspace of $C^\infin(\R)$.

---
# Generating Subspaces
Recall our example from before of $H=\{\begin{pmatrix}
    s\\t\\0
\end{pmatrix}\mid \ s,t \in \R\}$ being a subspace of $\R^3$.
$$\begin{aligned}
    H&=\{s\begin{pmatrix}
        1\\0\\0
    \end{pmatrix}+t\begin{pmatrix}
        0\\1\\0
    \end{pmatrix}\mid \ s,t \in \R\}\\
    &=\text{span}\{e_1,e_2\}.
\end{aligned}$$

The _span_ of a set of vectors in $V$ will always be a _subspace_ of $V$.

---
__Ex.__ Let $H$ be the set of all vectors of the form $$\begin{pmatrix}
    a-3b\\b-a\\a\\b
\end{pmatrix}
$$ Show that $H$ is a subspace of $\R^4$.

$$\begin{pmatrix}
    a-3b\\b-a\\a\\b
\end{pmatrix}=a\begin{pmatrix}
    1\\-1\\1\\0
\end{pmatrix}+b\begin{pmatrix}
    -3\\1\\0\\1
\end{pmatrix}
$$$$
    H=\text{span}\{\begin{pmatrix}
        1\\-1\\1\\0
    \end{pmatrix},\begin{pmatrix}
        -3\\1\\0\\1
    \end{pmatrix}\}
$$
Since the span of a collection of vectors from $\R^4$ is a subspace of $\R^4$, then $H$ is a subspace of $\R^4$.