# STAT 400
## Mon. March 9th, 2020
---

# Approximation of Binomial Distribution
__Proposition.__ Let $X$ follow $\text{bin}(n,p)$.  
If $np$ and $n(1-p)$ are large enough, then $X$ approximately follows a normal distribution $N(np,\ np(1-p))$.

In other words, if $Y$ follows $N(np,\ np(1-p))$, and $a$ is a positive integer, then $$
\begin{aligned}
    P(X\le a)&=B(a;n,p)\\
    &\approx P(Y\le a+0.5)\\
    &=P(Z\le \frac{a+0.5-np}{\sqrt{np(1-p)}})\\
    &=\Phi(\frac{a+0.5-np}{\sqrt{np(1-p)}}).
\end{aligned}
$$ _(The 0.5 in the equation is for continuity correction, since the binomial distribution is discrete but normal distributions are continuous.)

_Rule of thumb:_ If $np>10$ and $n(1-p)>10$, this approximation can be used.

---
__Ex.__ A fair coin is tossed 400 times. What is the probability that the number of heads is between 180 and 220?

Let $X$ be the number of heads; $X$ follows $\text{bin}(400, 0.5)$.
We want to find $P(180\le X\le 220)=P(X\le 220)-P(X\le 179).$

We don't want to have a binomial table that's hundreds of pages long for many values of $n$ all the way up to 400, so we can instead approximate this value with a standard normal table.

$$
\begin{aligned}
    P(X\le 220)-P(X\le 179)&\approx \Phi(\frac{220+0.5-200}{\sqrt{100}})-\Phi(\frac{179+0.5-200}{\sqrt{100}})\\
    &=\Phi(2.05)-\Phi(-2.05)\\
    &=0.96.
\end{aligned}
$$

---
# Exponential Distribution
__Definition.__ $X$ follows an __exponential distribution__ with parameter $\lambda > 0$ if its pdf is of the form $$
    f(x;\lambda)=\begin{cases}
        \lambda e^{-\lambda x} &x>0\\
        0&\text{otherwise}
    \end{cases}
$$ In this case, we say $X$ follows $\text{Exp}(\lambda)$.

## CDF
$$F(x;\lambda)=\begin{cases}
    1-e^{-\lambda x}&x>0\\
    0&\text{otherwise}
\end{cases}$$

## Expected Value
$$
\begin{aligned}
    E(X)&=\int_0^{\infin} x\lambda e^{-\lambda x}dx=\frac{1}{\lambda}\\
    E(X^2)&=\int_0^{\infin} x^2\lambda e^{-\lambda x}dx=\frac{2}{\lambda^2}
\end{aligned}
$$
## Variance
$$
V(X)=E(X^2)-[E(X)]^2=\frac{1}{\lambda^2}.
$$

---
## Relation to Poisson Process
We are interested in studying this distribution because of its relation to the Poisson process.

__Proposition.__ Suppose $X(s,t)$ is the number of arrivals between time $s$ and time $t$, and that $X$ is a Poisson process with parameter $\alpha$, i.e. $X(s,t)$ follows $\text{Pois}(\alpha(t-s))$.

Let $T_i$ be the time of the $i$th arrival. Then $T_{i+1}-T_i$ follows $\text{exp}(\alpha)$.  
_(Here, $T_{i+1}-T_i$ represents the duration of time between two consecutive arrivals.)_