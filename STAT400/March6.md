# STAT 400
## Fri. March 6th, 2020
---

## Standard Deviation Ranges on Normal Distributions

Suppose $X$ follows $N(\mu, \sigma^2)$. What is the probability that $X$ is within 1 standard deviation of its mean?

We want to find $P(\mu-\sigma\le X\le \mu+\sigma)$. We can do this by _standardizing_ our $X$ to produce a new RV $Z$ that follows the standard normal distribution $N(0,1)$.

$$
    \begin{aligned}
        &P(\mu-\sigma\le X\le \mu+\sigma)
        \\&=P(\frac{\mu-\sigma-\mu}{\sigma}\le \frac{X-\mu}{\sigma}\le \frac{\mu+\sigma-\mu}{\sigma})\\&=P(-1\le Z\le 1)\\&=\Phi(1)-\Phi(-1)\\&\approx0.6826.
    \end{aligned}
$$ Since $Z$ follows $N(0,1)$, we can use a standard normal distribution table to calculate $\Phi(1)$ and $\Phi(-1)$ and get our final value of $0.6826$. Interestingly, this result holds true for _all_ values of $\mu$ and $\sigma^2$.

---
## Percentiles of $N(\mu,\sigma^2)$

__Proposition.__ Let $\eta(p)$ be the $(100p)$th percentile for $N(0,1)$ (i.e. $P(Z\le \eta(p))=p$). Suppose $X$ follows $N(\mu,\sigma^2)$. Then $$P(X\le \mu+\sigma\eta(p))=p.$$ This is yet another way to relate the standard normal distribution to nonstandard normal distributions.