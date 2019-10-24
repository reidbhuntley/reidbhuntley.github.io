# MATH 240
### Mon. October 21st, 2019
---

# Unique Representation Theorem
__Theorem.__ Let $B=\{b_1,...,b_n\}$ be a basis for a vector space $V$. Then for each $x$ in $V$, there exists _unique_ $c_1,...,c_n$ such that $x=c_1b_1+...+c_nb_n$.

# Coordinates
__Definition.__ Suppose $B=\{b_1,...,b_n\}$ is a basis for $V$ and $x$ is in $V$. 
The __coordinates__ of $x$ relative to the basis $B$ (or the $B$-coordinates of $x$) are the weights $c_1,...,c_n$ such that $c_1b_1+...+c_nb_n=x$.
$$[x]_B=\begin{pmatrix}
    c_1\\...\\c_n
\end{pmatrix}
$$

---
## From $B$-Coordinates to Standard Basis Coordinates
__Ex.__ If $b_1=\begin{pmatrix}
    1\\0
\end{pmatrix},\ b_2=\begin{pmatrix}
    1\\2
\end{pmatrix},\ B=\{b_1,b_2\},$ and $[x]_B=\begin{pmatrix}
    -2\\3
\end{pmatrix}$, then find $x$. $$\begin{aligned}
    x&=c_1b_1+c_2b_2\\
    &=-2\begin{pmatrix}
        1\\0
    \end{pmatrix}+3\begin{pmatrix}
        1\\2
    \end{pmatrix}\\
    &=\begin{pmatrix}
        1\\6
    \end{pmatrix}.
\end{aligned}
$$

---
## From Standard Basis Coordinates to $B$-Coordinates
__Ex.__ If $b_1=\begin{pmatrix}
    2\\1
\end{pmatrix},\ b_2=\begin{pmatrix}
    -1\\1
\end{pmatrix},\ B=\{b_1,b_2\},$ and $x=\begin{pmatrix}
    4\\5
\end{pmatrix}$, then find $[x]_B$. $$\begin{aligned}
    x&=c_1b_1+c_2b_2\\
    \begin{pmatrix}
        4\\5
    \end{pmatrix}&=c_1\begin{pmatrix}
        2\\1
    \end{pmatrix}+c_2\begin{pmatrix}
        -1\\1
    \end{pmatrix}\\
    \begin{pmatrix}
        4\\5
    \end{pmatrix}&=\begin{pmatrix}
        2&-1\\1&1
    \end{pmatrix}\begin{pmatrix}
        c_1\\c_2
    \end{pmatrix}\\
    \rightarrow &\begin{pmatrix}
        2&-1&4\\1&1&5
    \end{pmatrix}\\
    \rightarrow &\begin{pmatrix}
        1&1&5\\2&-1&4
    \end{pmatrix}\\
    \rightarrow &\begin{pmatrix}
        1&1&5\\0&-3&-6
    \end{pmatrix}\\
    \rightarrow &\begin{pmatrix}
        1&1&5\\0&1&2
    \end{pmatrix}\\
    \rightarrow &\begin{pmatrix}
        1&0&3\\0&1&2
    \end{pmatrix}\\
    [x]_B&=\begin{pmatrix}
        c_1\\c_2
    \end{pmatrix}\\
    &=\begin{pmatrix}
        3\\2
    \end{pmatrix}.
\end{aligned}
$$

__Theorem.__ Let $P_B=\begin{bmatrix}
    b_1&...&b_n
\end{bmatrix}$. Now $x=P_B[x]_B$.
The columns of $P_B$ are linearly independent since they form a basis, so by the Invertible Matrix Theorem, $P_B$ is invertible. This means that $[x]_B=P_B^{-1}x$.

---
# Isomorphism
Let $B=\{b_1,...,b_n\}$ be a basis for $V$. Assigning coordinates to $V$ gives a linear transformation from $V$ to $\R^n$ that is one-to-one and onto. This means that $V$ and $\R^n$ are _isomorphic_ -- they look different, but can be represented by the same mathematical object.

---
__Ex.__ Let $P_5$ be the set of all polynomials of degree five or less.
$\{1,t,t^2,t^3,t^4,t^5\}$ is a basis for $P_5$. This means any polynomial of degree five or less $P$ takes the form $P(x)=a_5x^5+a_4x^4+a_3x^3+a_2x^2+a_1x^1+a_0$.

If $T$ is the transformation that assigns coordinates from $P_5$ to $\R^6$, then $$T(P(x))=\begin{pmatrix}
    a_5\\a_4\\a_3\\a_2\\a_1\\a_0
\end{pmatrix}
$$
Thus $P_5$ is _isomorphic_ to $\R^6$. This means we can perform computations like adding two polynomials in $P_5$ by adding their corresponding vectors in $\R^6$.

---
__Ex.__ $B=\{\sin{t},\ \cos{t}\}$ is the basis of a subspace inside of $C^\infin(\R)$. _($\sin{t}$ and $\cos{t}$ are linearly independent functions.)_ Since $B$ only contains two vectors, functions within this subspace can be represented as vectors in $\R^2$.