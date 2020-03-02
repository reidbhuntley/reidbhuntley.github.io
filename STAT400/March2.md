# STAT 400
## Mon. March 2nd, 2020
---

# (Continuous) Cumulative Distribution Function
The cumulative distribution function for a continuous random variable $X$ with pdf $f(x)$ is $$
F(x)=P(X\le x)=\int_{-\infin}^x f(y)dy.
$$

__Ex.__ $X$ follows $\text{unif}(A,B)$. Find the cdf of $X$.$$
\begin{aligned}
    f(x)&=\begin{cases}
        \frac{1}{B-A} & x\in[A,B]\\
        0 & \text{otherwise}
    \end{cases}\\\\
    F(x)&=\begin{cases}
        0 & x\le A\\
        \int_{-\infin}^x f(y)dy=\int_A^x f(y)dy=\frac{X-A}{B-A} & A\le X\le B\\
        \int_{-\infin}^x f(y)dy=\int_A^B f(y)dy = 1 & x\ge B
    \end{cases}
\end{aligned}
$$

---
## Properties
1. $F(x)$ is the total area under $f(y)$ to the left of $x$.
2. Since $f(y)\ge 0$, we know $F(x)$ is non-decreasing.
3. $0\le F(x)\le 1$.

__Proposition.__ Given the pdf $f(x)$ and the cdf $F(x)$ of a continuous RV $X$, then: $$
\begin{aligned}
    &P(X>a)=1-P(X\le a)=1-F(a)\\
    &P(a\le X\le b)=P(X\le b)-P(X\le a)=F(b)-F(a)\\
\end{aligned}
$$ Remember that since we're dealing with continuous functions now, the edge cases of $X=a$ and $X=b$ don't affect the cdf like they do for discrete variables.

__Proposition.__ From the fundamental theorem of calculus, we have $$
f(x)=\frac{d}{dx}F(x).
$$ Thus you can calculate a pdf given a cdf and vice-versa.

---
# Percentiles of a Continuous Distribution
In some cases we want to solve the inverse problem of finding the cdf $F(x)$ -- that is, given $p$, we want to find $a$ such that $P(X\le a)=F(a)=p$.

__Definition.__ Given $0\le p\le 1$, the $(100p)$th percentile of $X$, denoted as $\eta(p)$, satisfies $$
p=F(\eta(p))=\int_{-\infin}^{\eta(p)}f(x)dx.
$$

---
__Ex.__ The pdf of $X$ is $$
f(x)=\begin{cases}
    \frac{1}{8}+\frac{3}{8}x & 0\le x\le 2\\
    0 &\text{otherwise}
\end{cases}
$$ and its cdf is $$
F(X)=\begin{cases}
    0&x\le 0\\
    \frac{x}{8}+\frac{3}{16}x^2&0\le x\le 2\\
    1&x>2
\end{cases}
$$

Given $p=\frac{1}{16}$ find $\eta(p)$. $$
\begin{aligned}
    F(\eta(p))&=\frac{1}{16}\\
    \frac{\eta(p)}{8}+\frac{3}{16}\eta(p)^2&=\frac{1}{16}\\
    \eta(p)&=-1\text{ or }\frac{1}{3}\\
    \eta(p)&=\frac{1}{3}.
\end{aligned}
$$

---
# Median
__Definition.__ For $p=0.5$, we call $\eta(0.5)$ the __median__, denoted by $\tilde{\mu}$. By definition, $F(\tilde{\mu})=0.5$.

__Remark.__ $\mu=\tilde{\mu}$ when the pdf being studied is _symmetric_; i.e. $f(\tilde{\mu}+x)=f(\tilde{\mu}-x)$ for all $x$.  
For instance, if $X$ follows $\text{unif}(A,B)$, $\tilde{\mu}=\mu=\frac{A+B}{2}.$

---
# Expected Value
__Definition.__ The expected value of a continuous random variable $X$ with pdf $f(x)$ is $$
\mu=\mu_X=E(X)=\int_{-\infin}^{\infin}xf(x)dx.
$$

__Ex.__ $X$ follows $\text{unif}(A,B)$. $$
\begin{aligned}
    E(X)&=\int_A^Bx\cdot \frac{1}{B-A}dx\\
    &=\frac{1}{B-A}\cdot \frac{B^2-A^2}{2}\\
    &=\frac{(B+A)(B-A)}{2(B-A)}\\
    &=\frac{B+A}{2}.
\end{aligned}
$$ This result is in line with our remark about the median of random variables with symmetric pdfs.

---
__Proposition.__ If $X$ is a continuous RV with pdf $f(x)$, then the expected value of $h(X)$ is $$
\mu_{h(X)}=E(h(X))=\int_{-\infin}^{\infin}h(x)f(x)dx.
$$

__Ex.__ $X$ follows $\text{unif}(A,B)$. Find $E(X^2)$.
$$
\begin{aligned}
    E(X^2)&=\int_{-\infin}^{\infin}x^2f(x)dx\\
    &=\int_A^Bx^2\cdot\frac{1}{B-A}dx\\
    &=\frac{1}{B-A}\cdot \frac{B^3-A^3}{3}\\
    B^3-A^3&=(B-A)(B^2+BA+A^2)\\
    \rightarrow E(X^2)&=\frac{1}{3}(B^2+BA+A^2).
\end{aligned}
$$

---
# Variance and Standard Deviation
__Definition.__ The variance of a continuous random variable $X$ with pdf $f(x)$ and expected value $\mu$ is $$
\sigma_X^2=V(X)=\int_{-\infin}^{\infin}(x-\mu)^2f(x)dx=E((X-\mu)^2).
$$
The standard deviation (SD) of $X$ is $\sigma_X=\sqrt{V(X)}$.

__Proposition.__ $V(X)=E(X^2)-[E(X)]^2$, exactly the same property as with discrete RVs.

__Ex.__ $X$ follows $\text{unif}(A,B)$. $$
V(X)=\frac{1}{3}(B^2+BA+A^2)-(\frac{B+A}{2})^2=\frac{1}{12}(A-B)^2.
$$