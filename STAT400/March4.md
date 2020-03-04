# STAT 400
## Wed. March 4th, 2020
---

# Normal (Gaussian) Distribution

__Definition.__ A continuous random variable $X$ is said to follow a __normal distribution__ with parameter $\mu$ and $\sigma^2$, where $\sigma > 0$, if its pdf is $$
f(x;\mu,\sigma)=\frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}=\frac{1}{\sqrt{2\pi\sigma^2}} \text{exp}(-\frac{(x-\mu)^2}{2\sigma^2})
.$$ In this case, we write $X$ follows $N(\mu,\sigma^2)$.

---
Additionally, $E(X)=\mu$ and $V(X)=\sigma^2$. We can prove this ourselves:

$$
\begin{aligned}
    E(X)&=\int_{-\infin}^{\infin}x\cdot \frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx\\
    y&=\frac{x-\mu}{\sigma}\\
    E(X)&=\int_{-\infin}^{\infin}\frac{1}{\sqrt{2\pi}}(y\sigma + \mu)e^{-\frac{y^2}{2}}dy\\
    &=\frac{\sigma}{\sqrt{2\pi}}\int_{-\infin}^{\infin}ye^{-\frac{y^2}{2}}dy+\frac{\mu}{\sqrt{2\pi}}\int_{-\infin}^{\infin}e^{-\frac{y^2}{2}}dy\\
    &=\frac{\sigma
    }{\sqrt{2\pi}}\cdot 0+\frac{\mu}{\sqrt{2\pi}}\cdot \sqrt{2\pi}\\
    &=\mu
\end{aligned}
$$ We know that the left integral is 0 because it's an odd function, and the right integral is $\sqrt{2\pi}$ because it's the _Gaussian integral_ (look this up on your own). $V(X)$ can be calculated in a similar way.

---
# Standard Normal Distribution ($N(0,1)$)

Note what happens to the pdf of the normal distribution as the parameters change. Changing $\mu$ simply shifts the function left and right, while lowering $\sigma$ causes the function to "bunch up" around $\mu$ and raising it causes it to "spread out".

Because of this, we can just focus on the simplest case of parameters ($\mu=0,\ \sigma^2=1$) and still understand the entire family of normal distributions. $N(0,1)$ is thus called the __standard normal distirbution__.

We use $Z$ to denote an RV of standard normal distribution ($Z$ follows $N(0,1)$). The pdf of $Z$ is $f(x;0,1)=\frac{1}{\sqrt{2\pi}}e^{-\frac{x^2}{2}}$. This function is called the __standard normal curve__.

---
## Properties of $N(0,1)$
1. The inflection points of $f(x;0,1)$ are at $1$ and $-1$. (These are the points where $f''(x)=0$)
2. The cdf of $Z$, denoted as $\Phi(x)=P(Z\le x)$, is $$
\int_{-\infin}^x \frac{1}{\sqrt{2\pi}}e^{-\frac{y^2}{2}}dy.
$$ There is no closed form for $\Phi$, so we need to use a _standard normal table_ to calculate it.

---
## Important Percentiles of $N(0,1)$
The $(100p)$th percentile of $N(0,1)$ is $\eta(p)$, which satisfies $\Phi(\eta(p))=P(Z\le \eta(p))$. Here's a table of important values of $\eta(p)$: $$
\begin{aligned}
    p &\mid&0.9&\mid&0.95&\mid&0.975&\mid&0.99&\mid&0.995&\mid&0.999 \\
    \eta(p) &\mid&1.28&\mid&1.645&\mid&1.96&\mid&2.33&\mid&2.58&\mid&3.08
\end{aligned}
$$

## Critical Values of $Z$ ($Z_\alpha$)
Given $0<\alpha<1$, we set $Z_\alpha$ to the value satisfying $P(Z\ge Z_\alpha)=1-\Phi(Z_\alpha)=\alpha.$ _(This is essentially the same concept as percentiles, but with a different notation.)_

$$\begin{aligned}
    \alpha &\mid&0.1&\mid&0.05&\mid&0.025&\mid&0.01&\mid&0.005&\mid&0.001 \\
    Z_\alpha &\mid&1.28&\mid&1.645&\mid&1.96&\mid&2.33&\mid&2.58&\mid&3.08
\end{aligned}$$

---
# Nonstandard Normal Distributions
__Proposition.__ Let $X$ follow $N(\mu,\sigma^2)$. Then $Z=\frac{x-\mu}{\sigma}$ follows $N(0,1)$, which we can prove by performing the same change of variable we used to calculate $E(X).$

Thus, $$P(a\le X\le b)=P(\frac{a-\mu}{\sigma^2}\le Z\le \frac{b-\mu}{\sigma^2})=\Phi(\frac{b-\mu}{\sigma^2})-\Phi(\frac{a-\mu}{\sigma^2}).$$

Similarly, $$
P(a\le X)=P(\frac{a-\mu}{\sigma^2}\le Z)=1-\Phi(\frac{a-\mu}{\sigma^2})
$$ and $$
P(X\le b)=P(Z\le \frac{b-\mu}{\sigma^2})=\Phi(\frac{b-\mu}{\sigma^2}).
$$