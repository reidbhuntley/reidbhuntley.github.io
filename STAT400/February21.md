# STAT 400
## Fri. February 21st, 2020
---

# Hypergeometric Distribution
 You have a box of $N$ balls. $M$ of them are red ($R$), and the rest ($N-M$) are blue ($B$). If you pick $n$ balls from the box without replacing any, let $X$ be the number of _red_ balls picked.

In this case, we say $X$ follows a __hypergeometric distribution__ -- $X$ follows $\text{hypergeometric}(n,M,N)$.

Note that the probability of choosing a red ball _changes_ as different types of balls are removed from the box. This is the property that distinguishes this type of distribution.

__Ex.__ Suppose $N=20$, $M=12$ (so $N-M=8$), and $n=5$. Find the probability mass function of $X$.

Possible values of $X$: $0,1,2,...5$.
$$
\begin{aligned}
    p(0)=P(X=0)&=\frac{8 \choose 5}{20\choose 5}\\
    p(1)=P(X=1)&=\frac{ {12 \choose 1}\cdot {8 \choose 4} }{20 \choose 5}\\
    p(2)=P(X=2)&=\frac{ {12 \choose 2}\cdot {8 \choose 3} }{20 \choose 5}\\
    p(3)=P(X=3)&=\frac{ {12 \choose 3}\cdot {8 \choose 2} }{20 \choose 5}\\
    ...
\end{aligned}
$$

---
In the general case, values of $X$ have to satisfy these constraints for $p(k)$ to be nonzero: 
a) $0\le k \le n$
b) $k\le M$
c) $0\le n-k \le N-M$

These can be combined into one constraint: $$\text{Max}\{0,\ n-N+M\}\le k \le \text{Min}\{n,\ M\}.$$

For any $k$ satisfying this constraint, $$
p(k)=P(X=k)=\frac{ {M \choose k}{N-M \choose n-k} }{N \choose n}
$$

Here, $p$ is the probability mass function for the hypergeometric distribution. It is usually represented by the notation $h(k;n,M,n)$.

---
## Expected Value and Variance
Let $X$ follow $\text{hypergeometric}(n,N,M)$. Then $$
E(X)=n\cdot \frac{M}{N}
$$ and $$
V(X)=(\frac{N-n}{N-1})\cdot n\cdot \frac{M}{N}\cdot (1-\frac{M}{N}). 
$$

Note that if we let $p=\frac{M}{N}$, then $E(X)=np$ and $V(X)=np(1-p)\cdot (\frac{N-n}{N-1})$. 
$E(X)$ here is exactly the same as that of the binomial distribution, and $V(X)$ is the same as well except for the introduction of the rightmost term. 
If $N$ is much larger than $n$ ($N>>n$), then that rightmost term will be very close to $1$. This reflects the fact that when $N>>n$ you can _approximate_ the pmf of a hypergeometric distribution by using a binomial distribution table, since the chance of success will be barely affected by previous trials in this case.

---
# Negative Binomial Distribution
We repeat an experiment until we have $r$ successes. For each experiment, we have the same probability of success $p=P(\{S\})$. Let $X$ be the number of failures before the $r$th success. We say $X$ follows a __negative binomial distribution__ -- $X$ follows $\text{NB}(r,p)$.

__Ex.__ Suppose $r=3$ and $p=\frac{1}{3}$.
Possible values of $X$: $0,1,2,...$, any natural number

If $X=5$, then we know eight trials were performed, and that the last one has to have been a success. Thus, $P(X=5)$ should be the probability of three successes and five failures occurring, multiplied by the number of ways that two successes can occur within the first seven trials.$$
P(X=5)={7\choose 2}(\frac{1}{3})^3(1-\frac{1}{3})^5.
$$

---
In general if $X$ foloows $\text{NB}(r,p)$, then $$
p(k)=P(X=k)={k+r-1\choose r-1}\cdot p^r(1-p)^{k-r}.
$$

---
## Expected Value and Variance
Let $X$ follow $\text{NB}(r,p).$ Then $$
E(X)=\frac{r(1-p)}{p}
$$ and $$
V(X)=\frac{r(1-p)}{p^2}.
$$