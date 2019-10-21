# MATH 240
### Fri. October 18th, 2019
---
# Spanning Set Theorem

Consider the set of vectors $S=\{\begin{pmatrix}
    0\\1
\end{pmatrix},\begin{pmatrix}
    1\\0
\end{pmatrix},\begin{pmatrix}
    2\\3
\end{pmatrix},\begin{pmatrix}
    4\\7
\end{pmatrix}\}$.

What is the span of $S$? $\text{Span}(S)=\R^2$.

Is $S$ a basis? _No_, because it is a linearly dependent set -- the vectors are in 
$\R^2$ but there are four of them, and $4>2$.

Is $\{\begin{pmatrix}
    0\\1
\end{pmatrix},\begin{pmatrix}
    2\\3
\end{pmatrix}\}$ ($S$ with two vectors removed) a basis? _Yes_, because it is linearly independent and spans the entire space of $\R^2$.

__Theorem.__
1. Let $S=\{v_1,...,v_p\}$ be a set of vectors in $V$ and let $H=\text{Span}(S)$. If one of the vectors in $S$, say $v_k$, is a linear combination of the remaining vectors in $S$, then the set formed by removing $v_k$ from $S$ also spans $H$.
2. If $H\neq \{0\}$, then some subset of $S$ is a basis for $H$.

_(Note that the basis produced by this method will be different depending on which vectors you remove.)_

---
# Bases for $\text{Nul}A, \text{Col}A$
For a matrix $A$, a basis for $\text{Nul}A$ is formed from the solution set of $Ax=0$, and a basis for $\text{Col}A$ is formed from pivot columns of $A$.

__Ex.__
$$
\begin{aligned}
    A&=\begin{pmatrix}
        -3&6&-1&1&-7\\1&-2&2&3&-1\\2&-4&5&8&-4
    \end{pmatrix}\\
    &\rightarrow \begin{pmatrix}
        1&-2&0&-1&3\\0&0&1&2&-2\\0&0&0&0&0
    \end{pmatrix}\\
    \text{Basis for Col}A&=\{\begin{pmatrix}
        1\\0\\0
    \end{pmatrix},\begin{pmatrix}
        0\\1\\0
    \end{pmatrix}\}\\
    \\
    &x_2,\ x_4,\ x_5\ \text{are free}\\
    x_1&=2x_2+x_4-3x_5\\
    x_3&=-2x_4+2x_5\\
    \begin{pmatrix}
        x_1\\x_2\\x_3\\x_4\\x_5
    \end{pmatrix}&=x_2\begin{pmatrix}
        2\\1\\0\\0\\0
    \end{pmatrix}+x_4\begin{pmatrix}
        1\\0\\-2\\1\\0
    \end{pmatrix}+x_5\begin{pmatrix}
        -3\\0\\2\\0\\1
    \end{pmatrix}\\
    \text{Basis for Nul}A&=\{\begin{pmatrix}
        2\\1\\0\\0\\0
    \end{pmatrix},\begin{pmatrix}
        1\\0\\-2\\1\\0
    \end{pmatrix},\begin{pmatrix}
        -3\\0\\2\\0\\1
    \end{pmatrix}\}
\end{aligned}
$$

---
# Coordinates
## _Why_ should we care about bases?
__Theorem.__ Let $B=\{b_1,...,b_n\}$ be a basis for the vector space $V$. Given any $x$ in $V$, there are _unique_ $c_1,...,c_n$ such that $x=c_1b_1+...+c_nb_n$.

This means that once a basis is found for a vector space, we can _uniquely identify_ every vector in that space by the list of scalars $c_1,...,c_n$ associated with that vector. We call these the __coordinates__ of $x$ in $B$, denoted by $[x]_B$.

__Ex.__ Let $B=\{\begin{pmatrix}
    1\\3
\end{pmatrix},\begin{pmatrix}
    4\\0
\end{pmatrix}\}$, and let $[x]_B=\begin{pmatrix}
    7\\11
\end{pmatrix}$.
$$x=7\begin{pmatrix}
    1\\3
\end{pmatrix}+11\begin{pmatrix}
    4\\0
\end{pmatrix}=\begin{pmatrix}
    51\\21
\end{pmatrix}$$