# STAT 400
## Mon. February 17th, 2020
---

# Variance and Standard Deviation
We use the concept of variance to measure of the _deviation_ of a random variable $X$ from its expected value $\mu$.

__Definition.__ Let $X$ be a discrete random variable with probability mass function $p(x)$ and expected value $\mu$. The __variance__ of $X$, denoted by $V(X)$ or sometimes $\text{Var}(X)$ (or $\sigma_X^2$ or $\sigma^2$) is $$
V(X)=\sum_{y\in D}(y-\mu)^2\cdot p(y)=E((x-\mu)^2).
$$
We define the __standard deviation__ (SD) of $X$ as $\sigma_X=\sqrt{\sigma_X^2}=\sqrt{V(X)}.$

---
__Ex.__ $X$ follows $\text{Bernoulli}(\alpha)$. Calculate $V(X)$. $$
\begin{aligned}
    E(X)&=\alpha\\
    V(X)&=E((x-2)^2)\\
    &=(0-\alpha)^2\cdot (1-\alpha)+(1-\alpha)^2\cdot (\alpha)\\
    &=\alpha^2(1-\alpha)+\alpha(1-\alpha)^2\\
    &=\alpha(1-\alpha)(\alpha+(1-\alpha))\\
    &=\alpha(1-\alpha).
\end{aligned}
$$

---
__Ex.__ $X$ follows $\text{Geo}(p)$. Calculate $V(X)$. $$
\begin{aligned}
    E(X)&=\frac{1}{p}\\
    V(X)&=\sum_{k=1}^\infin (k-\frac{1}{p})^2 \cdot (1-p)^{k-1}p\\
    &=\sum_{k=1}^\infin (k^2-\frac{2k}{p}+\frac{1}{p^2}) \cdot (1-p)^{k-1}p\\
    &=(\sum_{k=1}^\infin \frac{1}{p^2}(1-p)^{k-1}p) - (\sum_{k=1}^\infin \frac{2k}{p}(1-p)^{k-1}p) + (\sum_{k=1}^\infin k^2(1-p)^{k-1}p)\\
    &=\frac{1}{p^2}(\sum_{k=1}^\infin (1-p)^{k-1}p) - \frac{2}{p}(\sum_{k=1}^\infin k(1-p)^{k-1}p) + p(\sum_{k=1}^\infin k^2(1-p)^{k-1})\\
    &=\frac{1}{p^2}(1)-\frac{2}{p}(E(X))+p\sum_{k=1}^\infin k^2(1-p)^{k-1}\\
    &=\frac{1}{p^2}-\frac{2}{p^2}+p\sum_{k=1}^\infin \frac{d}{dp} (k(1-p)^{k})\\
    &=\frac{-1}{p^2}+p \frac{d}{dp} (\sum_{k=1}^\infin k(1-p)^{k})\\
    &=\frac{-1}{p^2}+p \frac{d}{dp} ((1-p)\sum_{k=1}^\infin k(1-p)^{k-1})\\
    &=\frac{-1}{p^2}+p \frac{d}{dp} ((1-p)E(X))\\
    &=\frac{-1}{p^2}+p \frac{d}{dp} (\frac{1}{p}-1)\\
    &=-(\frac{1}{p^2}+\frac{1}{p}).
\end{aligned}
$$

---

__Proposition.__ $V(X)=E(x^2)-[E(X)]^2.$ $$
\begin{aligned}
    V(X)&=E[(x-\mu)^2]\\
    &=E(x^2-2\mu x+\mu^2)\\
    &=E(x^2)-E(2\mu x)+\mu^2\\
    &=E(x^2)-2\mu E(x)+\mu^2\\
    &=E(x^2)-2\mu^2 + \mu^2\\
    &=E(x^2)-\mu^2\\
    &=E(x^2)-[E(X)]^2.
\end{aligned}
$$ We can use this fact to simplify the calculation of $V(X)$.

---
# Variance on Linear Functions
In general, given any function $h$, what does $V(h(X))$ look like? $$
V(h(X))=\sum_{y\in D}(h(y)-\mu_{h(X)})^2\cdot p(y).
$$ This doesn't tell us much for the general case, since calculating $\mu_{h(X)}$ is not trivial.  
However, when $h$ is a _linear function_ (that is, $h(x)=ax+b$), then $$
h(y)-\mu_{ax+b}=ay+b-(a\mu_{X}+b)=a(y-\mu_X)
$$ and $$
\begin{aligned}
    V(h(X))&=V(ax+b)\\
    &=\sum_{y\in D} a^2(y-\mu_X)^2 \cdot p(y)\\
    &=a^2\sum_{y\in D} (y-\mu_X)^2 \cdot p(y)\\
    &=a^2V(X).
\end{aligned}
$$

Thus, $$V(ax+b)=\sigma_{ax+b}^2=a^2\sigma_{X}^2.$$