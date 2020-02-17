# STAT 400
## Wed. February 12th, 2020
---

# Parameters (cont.)
## Bernoulli Distribution
__Ex.__ For a Bernoulli random variable, introducing a parameter $\alpha$ gives us the _Bernoulli distribution_: $$p(x;\alpha)=\begin{cases}
    \alpha & x=1\\1-\alpha & x=0
\end{cases}$$ To say that a random variable $x$ follows this distribution, we write $x\rightarrow\text{Bernoulli}(\alpha).$ For example, if $x$ is the number of heads that occur from a coin toss, then $x\rightarrow \text{Bernoulli}(0.5).$

---
## Geometric Distribution
__Ex.__ Geometric distribution with parameter $p$:
Suppose we're testing the battery life of batteries. Let $p=P(\{S\})$. $x$ is the number of tests we must do before finding a battery with acceptable battery life (an $S$). Then: $$\begin{aligned}
    p(1)&=P(x=1)=p\\
    p(2)&=P(x=2)=(1-p)p\\
    p(3)&=P(x=3)=(1-p)^2p\\
    p(k)&=P(x=k)=(1-p)^{k-1}p
\end{aligned}$$ In general, $p(k;p)=\begin{cases}
    (1-p)^{k-1}p & k=1,2,3...\\
    0 & \text{otherwise}
\end{cases}$
We say that this $x$ follows a geometric distribution with parameter $p$: $x\rightarrow \text{Geo}(p).$

---
# Cumulative Distribution Function (cdf)
__Definition.__ The __cumulative distribution function__ _(cdf)_ $F(x)$ of a discrete random variable $x$ with probability mass function $p(x)$ is defined for every $x$ by $$F(x)=P(X\le x)=\sum_{y:\ y\le x}p(y).$$

__Ex.__ Converting a cdf to a geometric distribution with $p$: In general, $$\begin{aligned}
    F(x)&=\sum_{y:\ y\le x}p(y;p)\\&=\sum_{y=1}^{\lfloor x\rfloor}p(y;p)\\&=\sum_{y=1}^{\lfloor x\rfloor}(1-p)^{y-1}p.
\end{aligned}$$
Now we can apply the formula for the sum of a geometric series, which is: $$\sum_{y=0}^k a^y=\frac{1-a^{k+1}}{1-a}\text{ if } 0<a<1.$$
$$\begin{aligned}
    F(x)&=p\sum_{y=1}^{\lfloor x\rfloor}(1-p)^{y-1}\\&=p\sum_{y=0}^{\lfloor x\rfloor - 1}(1-p)^y\\&=p\cdot \frac{1-(1-p)^{\lfloor x\rfloor}}{1-(1-p)}\\&=1-(1-p)^{\lfloor x\rfloor}
\end{aligned}$$