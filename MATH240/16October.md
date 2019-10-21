# MATH 240
### Wed. October 16th, 2019
---
# Kernel
__Definition.__ Let $T:V\rightarrow W$ be a linear transformation. Then the __kernel__ of $T$ is given by
$$
\text{ker}(T)=\{v\mid T(v)=0, \ v \ \text{in} \ V\}.
$$ $\text{ker}(T)$ is a subspace of $V$; the proof of this is identical to the proof we used to show that $\text{Nul}A$ is a subspace.

# Range
The __range__ of $T$ is given by
$$
\text{ran}(T)=\{w\mid T(v)=w\ \text{for some} \ v \ \text{in} \ V\}.
$$
$\text{ran}(T)$ is a subspace of $W$. __Proof:__
* $T(0_V)=0_W$
    - Thus $0_W$ is in $\text{ran}(T)$.
* Take $u,v$ in $\text{ran}(T)$.
    - Now there are $u',v'$ in $V$ such that $T(u')=u$ and $T(v')=v$.
    - $u+v=T(u')+T(v')$
    - $u+v=T(u'+v')$
    - Thus $u+v$ is also in $\text{ran}(T)$.
* Let $c$ be any scalar.
    - $cu=cT(u')$
    - $cu=T(cu')$
    - Thus $cu$ is also in $\text{ran}(T)$.
* Thus $\text{ran}(T)$ is a subspace of $W$.

---
__Ex.__ $$\begin{gathered}
    T:C^\infin(\R)\rightarrow C^\infin(\R), \ T(f)=\dfrac{df}{dx}\\
    \text{ker}(T)=\{\text{constant functions in }C^\infin(\R)\}
\end{gathered}$$ The kernal space of $T$ here is the set of all functions whose derivatives are zero, which is just the set of constant functions in the space.

---
__Ex.__
$$\begin{gathered}
    T:C[0,1]\rightarrow \R, \ T(f)=\int_0^1f(x)dx\\
    \text{ran}(T)=\R
\end{gathered}$$ Take $c$ to be in $\R$. Consider the continuous function $f(x)=c$ for all $x$ in $[0,1]$: $$T(f)=\int_0^1f(x)dx=c.$$ Therefore the range of this transformation is $\R$.

---
## Null Space, Kernel, and Linear Independence
The linear transformation (mapping) $T:\R^n\rightarrow \R^m$ is one-to-one if and only if the columns of $A$, the standard matrix of $T$, are linearly independent, which is true if and only if $\text{Nul}A=\{0\}$.

Let $T:V\rightarrow W$ be a linear transformation. $T$ is one-to-one if and only if $\text{ker}(T)=\{0\}$.

An indexed set of vectors $\{v_1,...,v_p\}$ is said to be linearly independent if and only if $c_1v_1+...+c_pv_p=0$ is only true if $c_1=...=c_p=0$. _(Note that this is the same as our previous definition of linear independence, but applies to __any__ kind of vector, not just those in $\R^n$.)_

---
## Collections and Linear Independence

__Definition.__ A collection of vectors $u$ from $V$ is linearly independent if and only if __any__ _(every)_ finite subcollection of $u$ is linearly independent.

__Ex.__ $u=\{0,1,t,t^2,...,t^n,...\}$. _(infinitely sized collection of vectors)_
The subcollection $\{0,t\}$ is not linearly independent, so $u$ is not linearly independent either.

__Ex.__ $u=\{1,t,1-t\}$.
$1(1)-1(t)+1(1-t)=0$; therefore $u$ is not linearly independent.

---
# Basis
__Definition.__ $B$ is called a _basis_ for $V$ if both are true:
* $B$ is linearly independent.
* $\text{span}B=V$.

__Ex.__ The basis of $\R^n$ is $e_1,e_2,...,e_n$.

_Every vector space has a basis,_ but they are sometimes hard to find and represent for infinite-dimensional vector spaces.