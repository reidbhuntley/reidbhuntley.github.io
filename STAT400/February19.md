# STAT 400
## Wed. February 19th, 2020
---

# Binomial Probability Distribution

Suppose we repeat an experiment $n$ times ("$n$ trials"). The experiment produces two possible outcomes: success and failure, or $\{S,F\}$. The outcomes of each trial are independent. Denote $P(S)=p$, which is the same for all trials.  

Let $X$ be the number of successes among the $n$ trials. Then we call these $n$ trials a __binomial experiment__ and $X$ a __binomial random variable__ ($X$ follows $\text{bin}(n,p)$ with parameters $n,p$).

---
__Ex.__ $X$ follows $\text{bin}(4,p)$. Find the probability mass function for $X$.

Possible values of $X$: 0, 1, 2, 3, 4.

$p(0)=P(X=0)=(1-p)^4$
$p(1)=P(X=1)={4\choose{1}}\cdot p(1-p)^3 = 4p(1-p)^3$
*We multiply by 4 above because there's four possible ways to choose one success out of the four trial: $4\choose{1}$.*
$p(2)=P(X=2)={4\choose{2}}\cdot p^2(1-p)^2=6p^2(1-p)^2$
$p(3)=P(X=3)={4\choose{3}}\cdot p^3(1-p)^1=4p^3(1-p)$
$p(4)=P(X=4)={4\choose{4}}\cdot p^4=p^4$

---
In general, if $X$ follows $\text{bin}(n,p)$, then $$
P(X=k)={n\choose k}\cdot p^k(1-p)^{n-k}.
$$

__Theorem.__ If $X$ follows $\text{bin}(n,p)$, then the probability mass function for $X$ is $$
b(k;n,p)=\begin{cases}
    {n\choose k}\cdot p^k(1-p)^{n-k} & 0\le k\le n\\
    0 & \text{otherwise}
\end{cases}
$$

The cumulative distribution function for $X$ is $$
B(x;n,p)=\sum_{y=0}^{[x]} b(y;n,p) \text{ for } x>0.
$$
Note that there is _no closed form_ for this cdf -- the easiest way to calculate it is to just work out each value of $b$ by hand and sum them. However, you can use a __binomial table__ to simplify the calculations.

---
## Expected Value and Variance

__Theorem.__ If $X$ follows $\text{bin}(n,p)$, then $$
E(X)=np
$$ and $$
V(X)=np(1-p).
$$

---
## Properties
Now that we understand the binomial distribution, we can draw some conclusions about its properties and how it relates to the Bernoulli distribution:
1. $\text{Bernoulli}(p)=\text{bin}(1,p).$
2. Suppose we performed a sequence of independent experiments $X_i$ that follow $\text{Bernoulli}(p)$, where $X_i$ denotes the success or failure of the $i$th experiment. Then a new random variable formed by summing these outcomes follows $\text{bin}(n,p)$.
3. Suppose $X_1$ follows $\text{bin}(n_1,p)$ and $X_2$ follows $\text{bin}(n_2,p)$. Then $Y=X_1 + X_2$ follows $\text{bin}(n_1+n_2,p)$.
