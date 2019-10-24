# MATH 240
### Wed. October 23rd, 2019
---

__Theorem.__ If a vector space has a basis of $n$ vectors, then any collection of $p$ vectors, where $p>n$, is going to be linearly dependent.
_(We get this theorem "for free" because of the isomorphism between $V$ and $\R^n$ that we previously showed exists.)_

---
__Theorem.__ If a vector space has a basis of $n$ vectors, then any other basis of that vector space will also have $n$ vectors.

__Proof.__ Let $V$ be a vector space, and let $B$ be a basis for $V$ with $n$ vectors. Let $B'$ be another basis for $V$.
* If $B'$ had _more_ than $n$ vectors, then $B'$ would be linearly dependent; however, since it is a basis it must be linearly independent. Thus $B'$ has _at most_ $n$ elements.
* If $B'$ had _less_ than $n$ vectors, then we couldn't write down the elements of $B$ as a linear combination of elements of $B'$; however, since it is a basis this must be true. Thus $B'$ has _at least_ $n$ elements.

Thus $B'$ has _exactly_ $n$ elements.

This theorem indicates that the number of elements in a basis is _invariant_ for a vector space -- it's the same for every basis of that vector space.

---
# Dimension

__Definition.__ If $V$ is spanned by a finite set, we say that $V$ is _finite dimensional_, and the _dimension_ of $V$, or $\text{dim}V$, is the number of vectors in a basis of $V$. The dimension of $\{0\}$ is defined to be $0$.
If $V$ is spanned by an infinite set, we say that $V$ is _infinite dimensional_.

---
__Ex.__ Let $M_{2\times 2}$ be the space of $2\times 2$ matrices over $\R$ (that is, the $2\times 2$ matrices whose entries are real numbers). $M_{2\times 2}$ is a vector space over the real numbers. What is $\text{dim}M_{2\times 2}$?

If we can find a basis for $M_{2\times 2}$, then all we have to do is count the number of vectors in that basis to determine $\text{dim}M_{2\times 2}$. $$
\begin{gathered}
    \begin{pmatrix}
        a&b\\c&d
    \end{pmatrix}=a\begin{pmatrix}
        1&0\\0&0
    \end{pmatrix}+b\begin{pmatrix}
        0&1\\0&0
    \end{pmatrix}+c\begin{pmatrix}
        0&0\\1&0
    \end{pmatrix}+d\begin{pmatrix}
        0&0\\0&1
    \end{pmatrix}\\
    B=\{\begin{pmatrix}
        1&0\\0&0
    \end{pmatrix},\begin{pmatrix}
        0&1\\0&0
    \end{pmatrix},\begin{pmatrix}
        0&0\\1&0
    \end{pmatrix},\begin{pmatrix}
        0&0\\0&1
    \end{pmatrix}
    \}\\
    \text{Span}B=M_{2\times 2}\\
\end{gathered}
$$
$B$ spans $M_{2\times 2}$ and is linearly independent, so $B$ is a basis for $M_{2\times 2}$.
$B$ contains four elements, thus $\text{dim}M_{2\times 2}=4$.

---
## Subspaces of a finite dimensional vector space
__Theorem.__ Let $H$ be a subspace of a finite dimensional vector space $V$. Any linearly independent set in $H$ can be _expanded_ if needed to be a basis of $H$. _(You can keep adding linearly independent vectors to the set to eventually get a vector of $H$.)_ Also, $H$ is finite dimensional and $\text{dim}H\leq \text{dim}V$.
