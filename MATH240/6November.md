# MATH 240
### Wed. November 6th, 2019
---

We're concerned with calculating eigenvalues.
Which matrices have the _same_ eigenvalues?

---
# Similar Matrices

__Definition.__ Two $n\times n$ matrices $A$ and $B$ are __similar__ if there is some invertible matrix $P$ such that $A=PBP^{-1}$.

If $A$ is similar to $B$, then $B$ is similar to $A$.
$$
\begin{aligned}
    A&=PBP^{-1}\\
    P^{-1}AP&=P^{-1}PBP^{-1}P\\
    P^{-1}AP&=B\\
    P^{-1}A(P^{-1})^{-1}&=B
\end{aligned}
$$

---
__Theorem.__ If $A$ and $B$ are similar matrices, then $A$ and $B$ have the same characteristic equation, and thus have the same eigenvalues _(with the same multiplicities)_.

__Proof.__
We need to show that $\text{det}(A-\lambda I)=\text{det}(B-\lambda I)$, as this would mean they have the same characteristic equation.
$$
\begin{aligned}
    A&=PBP^{-1}\\
    A-\lambda I&=PBP^{-1} - \lambda I\\
    &=PBP^{-1} - \lambda (PP^{-1})\\
    &=PBP^{-1} - P(\lambda I)P^{-1}\\
    &=P(B-\lambda I)P^{-1}\\
    \text{det}(A-\lambda I)&=\text{det}(P(B-\lambda I)P^{-1})\\
    &=\text{det}(P)\ \text{det}(B-\lambda I)\ \text{det}(P^{-1})\\
    &=\text{det}(P)\ \text{det}(P^{-1})\ \text{det}(B-\lambda I)\\
    &=\text{det}(PP^{-1})\ \text{det}(B-\lambda I)\\
    &=\text{det}(I)\ \text{det}(B-\lambda I)\\
    &=\text{det}(B-\lambda I).
\end{aligned}
$$ QED.

_Note:_ Just because $A$ and $B$ have the same eigenvalues doesn't mean they have the same eigenvectors.

---
# Matrix Powers
$A^k$ is the result of multiplying a square matrix $A$ by itself $k$ times. This turns out to have many useful applications, so we want a way of computing it for large values of $k$ that's quicker than doing manual matrix multiplication.

If $D$ is a diagonal matrix, then $D^k$ is the matrix formed by raising the entries on the diagonal of $D$ to the $k$th power. This is a lot easier to compute naively than powers of non-diagonal matrices.

---
# Diagonalizable Matrices
__Definition.__ A matrix $A$ is said to be __diagonalizable__ if $A$ is similar to a diagonal matrix.

$$
\begin{aligned}
    A&=PDP^{-1}\\\\
    A^2&=(PDP^{-1})(PDP^{-1})\\
    &=PD(P^{-1}P)DP^{-1}\\
    &=PDDP^{-1}\\
    &=PD^2P^{-1}\\\\
    A^3&=A^2A\\
    &=(PD^2P^{-1})(PDP^{-1})\\
    &=PD^2(P^{-1}P)DP^{-1}\\
    &=PD^3P^{-1}\\
    ...
\end{aligned}
$$ By induction, $A^k=PD^kP^{-1}$, where $A$ is a diagonalizable matrix and $D$ is the diagonal matrix it's similar to.

---
__Theorem:__ An $n\times n$ matrix $A$ is diagonalizable if and only if $A$ has $n$ linearly independent _eigenvectors_.

__Theorem:__ An $n\times n$ matrix with $n$ _distinct_ eigenvalues is diagonalizable. _(This is from another theorem stating that eigenvectors that correspond to distinct eigenvalues are linearly independent.)_

In order to determine if $A$ is diagonalizable, we can find the eigenvalues of $A$ by solving $\text{det}(A-\lambda I)=0$ for $\lambda$, then determining whether or not they are distinct. If they are, then $A$ is definitely diagonalizable. Otherwise, we have to find eigenvectors for each eigenvalue and see if they are linearly independent. In this way, determining if a matrix is diagonalizable is now a completely algorithmic process.

---
__Ex.__ Is this matrix diagonalizable?
$$
\begin{pmatrix}
    5&0&3&4\\0&7&2&1\\0&0&0&1\\0&0&0&4
\end{pmatrix}
$$ _Yes_, because its eigenvalues are just the entries on its diagonal, which there are four of, and they are all distinct.

_(Note that this matrix is non-invertible -- non-invertible matrices can be diagonalizable.)_