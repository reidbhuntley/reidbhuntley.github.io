# MATH 240
### Wed. October 9th, 2019
---

# Vector Spaces and Subspaces
__Definition.__ A _vector space_ is a non-empty set $V$ of objects called _vectors_ on which are defined two operations called _addition_ and _multiplication by scalars_ subject to ten axioms.

For all vectors $u,v$ and scalars $c,d$:
1. If $u,v$ are in $V$, then $u+v$ is also in $V$.
2. $u+v=v+u$.
3. $u+(v+w)=(u+v)+w$.
4. There is a zero vector $0$ in $V$ such that $u+0=u$.
5. For each $u$ in $V$, there is a vector $-u$ in $V$ such that $u+(-u)=0$.
6. If $u$ is in $V$ and $c$ is a scalar, $cu$ is also in $V$.
7. $c(u+v)=cu+cv$.
8. $(c+d)u=cu+du$.
9. $c(du)=(cd)u$.
10. $1u=u$.

_Note: The scalars we will be working with are almost always real numbers, but they could also be complex numbers._

_Also note that by this definition, the real numbers are considered to be a vector space, as are the complex numbers._

---
# Types of Vector Spaces
## Finite-Dimensional Vector Spaces
We mostly deal with __finite-dimensional vector spaces__ -- they look like $\R^n$, where $n$ is a positive nonzero integer. This means that the size of any basis in these vector spaces will be finite.

## Infinite-Dimensional Vector Spaces
There are also __infinite-dimensional vector spaces__ -- these can't be represented in an $\R^n$-form. For example, the set of all continuous functions on the interval $[0,1]$, denoted by $C[0,1]$, can be considered a vector space with infinite dimensions. It fulfills the ten axioms:
* $(f+g)(x)=f(x)+g(x)$
* $(cf)(x)=cf(x)$
* Every function that is a sum of two functions continuous on $[0,1]$ is also continuous on $[0,1]$.
* $f(x)=0$ acts as the zero vector.
* etc...

The set of all functions on $\R$ which are _infinitely differentiable_, denoted as $C^\infin(\R)$, is also an infinite-dimensional vector space.

A third example of an infinite-dimensional vector space is the set of all sequences that are absolutely convergent.
* Sequences can be added together element-wise to produce new sequences.
* If $(x_n),(y_n)$ are absolutely convergent, so is $(x_n+y_n)$.
    - $$
    \begin{aligned}
        &\sum_{n=1}^\infin|x_n+y_n|\\
        \leq&\sum_{n=1}^\infin|x_n|+|y_n|\\
        =&\sum_{n=1}^\infin|x_n|+\sum_{n=1}^\infin|y_n|
    \end{aligned}
    $$
    - $(x_n+y_n)$ is less than or equal to $(x_n)+(y_n)$ which are both convergent, therefore it is also convergent.
* etc...

## Applying Linear Transformations
The reason it's important to talk about linear transformations, even though so far we've just been able to look at matrices to do computations, is because _there is no good analogue to matrices when dealing with infinite-dimensional vector spaces._

For example, integration is a linear transformation: $$T:C[0,1]\rightarrow\R, \ T(f)=\int_0^1f(x)dx.$$
The derivative is also a linear transformation: $$T:C^\infin(\R)\rightarrow C^\infin(\R), \ T(f)=\frac{d}{dx}f(x).
$$

__Many important objects in math turn out to be vectors, and many important operations in math turn out to be linear transformations!__