# STAT 400
## Wed. March 11th, 2020
---

# Exponential Distribution and Poisson Process cont.
__Ex.__ Suppose $0=T_1\le T_2\le T_3\le...$ are the arrival times of the $i$th bus ($i=1,2,3...$), and $T_{i+1}-T_i$ follows $\text{exp}(\alpha)$ for all $i$.

1. What is the probability that the first bus arrives after a time $t$?
$$
P(T_1> t)=1-P(T_1\le t)=1-(1-e^{-\alpha t})=e^{-\alpha t}.
$$
2. If you arrive at the bus stop at time 0, what is the expected waiting time to get on a bus?
$$
E(T_1)=\frac{1}{\alpha}.
$$
3. Suppose you've already waited for $t_0$ minutes. What is the probability that you'll need to wait at least another $t$ minutes?
$$
\begin{aligned}
    P(T_1\ge t+t_0\mid T_1>t_0)&=\frac{P(\{T_1\ge t+t_0\}\cap \{T_1\ge t_0\})}{P(T_1\ge t_0)}\\
    &=\frac{P(T_1\ge t+t_0)}{P(T_1\ge t_0)}\\
    &=\frac{e^{-\alpha(t+t_0)}}{e^{-\alpha t_0}}\\
    &=e^{-\alpha t}=P(T_1\ge t).
\end{aligned}
$$ We're able to get rid of the intersect here because $P(T_1\ge t+t_0)$ is a _subset_ of $P(T_1\ge t_0)$ -- the left will always be true when the right is _(but not the other way around)_.

Note the fact that the value of $t_0$ is irrelevant to our final result. This is called the __memoryless property of $\text{exp}(\alpha)$__ -- what has happened in the past will not affect the future results for this distribution. In other words, $$
P(X\ge t+t_0 \mid X\ge t_0)=P(X\ge t)
$$  for any $t_0>0$ when $X$ follows $\text{exp}(\alpha)$.

---
# Gamma Distribution
Consider the same scenario as the last section. Suppose you arrive at the bus stop at $t_0$. What's the probability that you midd the $n$th bus?  
In other words, what is $P(T_n\le t_0)$? To answer this, we need to introduce a new distribution.

## Gamma Function
__Definition.__ The Gamma function $\Gamma(\alpha)$ is defined for $\alpha>0$ as $$
\Gamma(\alpha)=\int_0^{\infin} x^{\alpha - 1}e^{-x}dx
.$$

## Properties of the Gamma Function

1. When $\alpha=n$ and $n$ is a positive integer, then $\Gamma(\alpha)=(n-1)!$.
2. $\Gamma(\alpha)=(\alpha-1)\cdot \Gamma(\alpha-1)$ for all $\alpha>1$.
3. $\Gamma(\frac{1}{2})=\sqrt{\pi}.$

---
## Gamma Distribution Definition
__Definition.__ We say a continuous RV $X$ follows the Gamma distribution with parameters $\alpha>0,\ \beta >0$ if its pdf is $$
f(x;\alpha,\beta)=\begin{cases}
    \frac{1}{\beta^\alpha \Gamma(\alpha)}x^{\alpha-1}e^{-\frac{x}{\beta}} & x\ge 0\\
    0 & \text{otherwise}
\end{cases}
$$ In this case, we say $X$ follows $\Gamma(\alpha,\beta)$.

In the special case when $\beta=1$, we call $\text{Gamma}(\alpha,1)$ the __standard Gamma distribution__.

---
## Nonstandard Gamma Distributions
__Proposition.__ If $X$ follows $\text{Gamma}(\alpha,\beta)$, then $\frac{X}{\beta}$ follows $\text{Gamma}(\alpha,1)$.

__Proof.__
$$
\begin{aligned}
    P(\frac{X}{\beta}\le x)&=P(X\le \beta x)\\
    &=\int_0^{\beta x}\frac{1}{\beta^\alpha\Gamma(\alpha)}y^{\alpha-1}e^{-\frac{y}{\beta}}dy\\
    &=\int_0^{x}\frac{1}{\beta^\alpha\Gamma(\alpha)}(\beta z)^{\alpha-1}e^{-z}\beta dz\\
    &=\int_0^{x}\frac{1}{\Gamma(\alpha)}z^{\alpha-1}e^{-z} dz\\
    &=P(Z\le x),
\end{aligned}
$$ where $Z$ follows $\text{Gamma}(\alpha,1)$, so therefore $\frac{X}{\beta}=Z.$

---
_After this he calculated the expected value and variance for the Gamma distribution but I wasn't fast enough to type it; please look it up in the textbook._

---
## CDF
When $Z$ follows $\text{Gamma}(\alpha, 1)$, $$
P(Z\le x)=F(x;\alpha)=\int_0^x \frac{y^{\alpha -1}e^{-y}}{\Gamma(\alpha)}dy.
$$ This equation has no closed form; $F(x;\alpha)$ is called the __incomplete Gamma function__, and there is a table for it in the textbook.

When $X$ follows $\text{Gamma}(\alpha, \beta)$, $$
P(X\le x)=P(X\le \frac{x}{\beta})=F(\frac{x}{\beta};\alpha),
$$ where $F$ is again the incomplete Gamma function.