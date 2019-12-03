# MATH 240
### Mon. November 25th, 2019
---

# QR Factorization
If $A$ is an $m\times n$ matrix with linearly independent columns, then $A$ can be factored as $QR$, where $Q$ is an $m\times n$ matrix whose columns form an orthonormal basis for $\text{Col}A$, and $R$ is an $n\times n$ upper triangular invertible matrix with positive entries on its diagonal.

__Ex.__ $A=\begin{pmatrix}
    1&0&0\\1&1&0\\1&1&1\\1&1&1
\end{pmatrix}$

---
_Step 1_: Use Gram-Schmidt to find an orthogonal basis for $\text{Col}A$. _(We already did this for this set of vectors last Friday.)_

$\text{Col}A=\text{span}\{v_1,v_2,v_3\}$ where $v_1=\begin{pmatrix}
    1\\1\\1\\1
\end{pmatrix},v_2=\begin{pmatrix}
    -3\\1\\1\\1
\end{pmatrix},v_3=\begin{pmatrix}
    0\\-\frac{2}{3}\\\frac{1}{3}\\\frac{1}{3}
\end{pmatrix}$

_Step 2_: Normalize these vectors and collect them into a matrix to form $Q$.

$$Q=\begin{pmatrix}
    \frac{1}{2}&-\frac{3}{\sqrt{12}}&0\\\frac{1}{2}&\frac{1}{\sqrt{12}}&-\frac{2}{\sqrt{6}}\\\frac{1}{2}&\frac{1}{\sqrt{12}}&\frac{1}{\sqrt{6}}\\ \frac{1}{2}&\frac{1}{\sqrt{12}}&\frac{1}{\sqrt{6}}
\end{pmatrix}$$

Because the columns of $Q$ are orthonormal, $Q^TQ=I$.
Thus $Q^TA=Q^T(QR)=(Q^TQ)R=R$.

_Step 3_: Calculate $Q^TA$.

$$
R=Q^TA=\begin{pmatrix}
    2&\frac{3}{2}&1\\0&\frac{3}{\sqrt{12}}&\frac{2}{\sqrt{12}}\\0&0&\frac{2}{\sqrt{6}}
\end{pmatrix}
$$

---

# Least Squares
__Idea.__ Given an _inconsistent_ system $Ax=b$ (i.e. no solutions), find $\hat{x}$ such that $A\hat{x}$ is as close to $b$ as possible.

In other words, we want to find the point $A\hat{x}$ in the column space of $A$ that is closest to $b$.

__Definition.__ If $A$ is an $m\times n$ matrix and $b$ is in $\R^m$, a __least squares solution__ of $Ax=b$ is an $\hat{x}$ in $\R^n$ such that $\lVert b-A\hat{x} \rVert \leq \lVert b-Ax \rVert$ for all $x$ in $\R^n$.

---
## Finding a solution to a least squares problem

Let $A$ be an $m\times n$ matrix.

_Q1_: What is the point in the column space of $A$ that is closest to $b$?
_A1_: The projection of $b$ onto $\text{Col}A$.

Take $\hat{b}=\text{proj}_A(b)$.

_Q2_: What space will the least squares solution $x$ be from?
_A2_: $\R^n$.

Now all we have to do is solve $Ax=\hat{b}$, which we know must be consistent since $\hat{b}$ is in $\text{Col}A$. (However, there may be infinitely many solutions.)

---

Note that any column of $A$ (say $a_j$) is orthogonal to the _component_ of $\hat{b}$ (which is $b-Ax$), so $a_j\cdot(b-Ax)=0$.

$a_j^T(b-Ax)=0$
$A^T(b-Ax)=0$