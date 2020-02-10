# STAT 400
## Fri. February 7th, 2019
---

# Independence (cont.)
To recap: two events $A$ and $B$ are independent if and only if $P(A\mid B)=P(A)$, and dependent otherwise.

__Important__: Just because two events are dependent does _not_ mean that one event was caused by the other; that is to say, dependence is not the same as _causality_. In statistics, we only study the _correlation_ between events.

---
## Properties of Independence
1. Independence is _symmetric_: $P(A\mid B)=P(A)\leftrightarrow P(B\mid A)=P(B)$.
2. If $A$ and $B$ are independent, then $A'$ and $B$ are also independent:
    $$\begin{aligned}
        P(A'\mid B)&=\frac{P(B\cap A')}{P(B)}\\&=\frac{P(B)-P(B\cap A)}{P(B)}
        \\&=1-\frac{P(B\cap A)}{P(B)}\\&=1-P(A\mid B)\\&=1-P(A)=P(A').
    \end{aligned}$$
3. $A$ and $B$ are independent if and only if $P(A\cap B)=P(A)\cdot P(B)$.

---
__Ex.__ Toss a coin ten times.
$$\begin{aligned}
    A&=\{\text{first 9 tosses are all H}\}\\
    B&=\{\text{10th toss is T}\}\\
    C&=\{\text{at least one T within the first 9 tosses}\}
\end{aligned}$$

Intuitively:
* $A$ and $B$ are independent: they care about different tosses
* $A$ and $C$ are _dependent_: $C=A'$, so they are disjoint and disjoint events are always dependent
* $B$ and $C$ are independent: they also care about different tosses

---
## Independence of more than two events
__Definition.__ Given events $A_1,A_2...A_n$, we say they are __mutually independent__ if, for every $k=2,3,...n$ and every subset of indices $i_1,i_2...i_k$, $$P(A_{i_1}\cap A_{i_2}\cap A_{i_3}...\cap A_{i_k})=P(A_{i_1})\cdot P(A_{i_2})...P(A_{i_k}).$$

For instance, if we want to determine if $A_1, A_2, A_3$ are mutually independent, then all of the following equations must hold:
* $k=2$: 3 equations
    - $P(A_1\cap A_2)=P(A_1)\cdot P(A_2)$
    - $P(A_1\cap A_3)=P(A_1)\cdot P(A_3)$
    - $P(A_2\cap A_3)=P(A_2)\cdot P(A_3)$
* $k=3$: 1 equation
    - $P(A_1\cap A_2\cap A_3)=P(A_1)\cdot P(A_2)\cdot P(A_3)$

The number of equations needed to check grows exponentially, so you probably won't be asked to check more than three events.

---
__Ex.__ Roll a die twice. $$\begin{aligned}
    A_1&=\{\text{first roll is 3}\}\\
    A_2&=\{\text{second roll is 4}\}\\
    A_3&=\{\text{sum of the two rolls is 7}\}
\end{aligned}$$ Are these events mutually independent?

* $k=2$:
    - $\frac{1}{36}=P(A_1\cap A_2)=P(A_1)\cdot P(A_2)=\frac{1}{6}\cdot \frac{1}{6}$
    - $\frac{1}{36}=P(A_1\cap A_3)=P(A_1)\cdot P(A_3)=\frac{1}{6}\cdot \frac{1}{6}$
    - $\frac{1}{36}=P(A_2\cap A_3)=P(A_2)\cdot P(A_3)=\frac{1}{6}\cdot \frac{1}{6}$
* $k=3$:
    - $\frac{1}{36}=P(A_1\cap A_2\cap A_3)\ne P(A_1)\cdot P(A_2)\cdot P(A_3)=\frac{1}{6}\cdot \frac{1}{6}\cdot \frac{1}{6}$

Because all of the $k=2$ cases are true, we call these events __pairwise independent__. However, the $k=3$ case is false, so they are not mutually independent.

---
# Random Variables

We have already studied the probability of random outcomes occurring quantitatively, but we also want to be able to quantitatively study the outcomes themselves. Often these already have a numerical value associated with them (like a die roll), but sometimes they don't (like a coin flip). In these cases we can create our own mapping to numerical values, for instance: $\{H,T\}\rightarrow \{1,0\}.$

__Definition.__ Given a sample space of some experiment, a __random variable__ is a rule that associates a _value_ with each outcome in $S$; that is, a random variable $X$ is a mapping from $S$ to $\R$. $$X: S \rightarrow \R.$$
