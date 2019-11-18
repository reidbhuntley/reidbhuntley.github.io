# MATH 240
### Fri. November 15th, 2019
---

Given a vector $v$ in $\cnums^2$, we can define the real part of $v$ ($\text{Re}(v)$) and the imaginary part of $v$ ($\text{Im}(v)$).

---
__Theorem.__ Let $A$ be a $2\times 2$ matrix with real entries but no real eigenvalues, and let $\lambda$ be a (complex) eigenvalue of $A$. The other eigenvalue of $A$ will be the complex conjugate $\overline{\lambda}$ of $\lambda$.

__Proof__.
$$
\begin{aligned}
    Ax&=\lambda x\\
    A\overline{x}&=\overline{A}\overline{x}\\
    &=\overline{Ax}\\
    &=\overline{\lambda x}\\
    &=\overline{\lambda}\overline{x}
\end{aligned}
$$

---
__Theorem.__ Let $A$ be a real $2\times 2$ matrix with complex eigenvalues $a-bi\ (b\neq 0)$ and $v$ be an associated eigenvector in $\cnums^2$. Then $A=PCP^{-1}$ where $P=\begin{bmatrix}
    \text{Re}(v)&\text{Im}(v)
\end{bmatrix}$ and $C=\begin{pmatrix}
    a&-b\\b&a
\end{pmatrix}$.

We know $P$ in this case represents a change of basis; in the equation $Ax=PCP^{-1}(x)$, we first change basis by multiplying by $P^{-1}$, then undergo some transformation by multiplying by $C$, and finally change back into standard basis by multiplying by $P$.

What is the transformation that this matrix $C$ represents?

$$
\begin{aligned}
    C&=\begin{pmatrix}
        a&-b\\b&a
    \end{pmatrix}\\
    \text{det}(C-\lambda I)&=\begin{vmatrix}
        a-\lambda&-b\\b&a-\lambda
    \end{vmatrix}\\
    &=(\lambda -a)^2+b^2\\
    0&=(\lambda -a)^2+b^2\\
    \lambda&=a\pm bi\\
    r&=\mid\lambda\mid=\sqrt{a^2+b^2}\\
    C&=r\begin{pmatrix}
        \dfrac{a}{\sqrt{a^2+b^2}}&\dfrac{-b}{\sqrt{a^2+b^2}}\\\dfrac{b}{\sqrt{a^2+b^2}}&\dfrac{a}{\sqrt{a^2+b^2}}
    \end{pmatrix}\\
    &=r\begin{pmatrix}
        \cos{\theta}&-\sin{\theta}\\\sin{\theta}&\cos{\theta}
    \end{pmatrix}\\
    &=\begin{pmatrix}
        r&0\\0&r
    \end{pmatrix}\begin{pmatrix}
        \cos{\theta}&-\sin{\theta}\\\sin{\theta}&\cos{\theta}
    \end{pmatrix}
\end{aligned}
$$

Thus $C$ can always be represented as the product of a rotation transformation and a scaling transformation.

---
# Inner Products
1. $\R^n$ is a vector space.
2. You can compute distance between elements of $\R^n$.
3. $\R^n$ is an _inner product space_.

__Definition.__ An __inner product space__ over $\R$ is a vector space $V$ over $\R$ combined with an _inner product._ This is represented as a function $\langle \rangle:V\times V\rightarrow \R$ with the following properties:
$$
\begin{aligned}
    \langle x,y\rangle&=\langle y,x\rangle\\
    \langle u+v,w\rangle&=\langle u,w\rangle+\langle v,w\rangle\\
    c\langle u,v\rangle&=\langle cu,v\rangle=\langle u,cv\rangle\\
    \langle u,u\rangle&\geq0\\
    \langle u,u\rangle&=0 \text{ iff } u=0
\end{aligned}
$$

__Ex.__ The __dot product__ on $\R^n$ is an inner product: $\langle u,v\rangle=u^Tv$ for $u,v$ in $\R^n$.

__Ex.__ Let $C[0,1]$ be the space of continuous functions on $[0,1]$. Then $\int_0^1 fg$ is an inner product on $C[0,1]$.

# Norm
For __any__ inner product, there is an associated notion of a __norm__ (the magnitude of a vector): $\lVert v\rVert=\sqrt{\langle v,v\rangle}$.

For $\R^n$,
$$
\begin{aligned}
    \langle v,v\rangle&=v_1^2+...+v_n^2\\
    \lVert v\rVert&=\sqrt{v_1^2+...+v_n^2}
\end{aligned}
$$

With a norm, you also get a notion of distance: $\text{dis}(u,v)=\lVert u-v\rVert$.
For $\R^n$, this corresponds to the distance formula.

With an inner product, you also get a notion of what it means for two vectors to be __orthogonal__ to each other: $\langle u,v\rangle=0$. This is a very important property for vectors, which we will discuss later.
