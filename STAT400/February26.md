# STAT 400
## Wed. February 26th, 2020
---

# Continuous Random Variables

We call a random variable $X$ a __continuous__ random variable if it satisfies these two properties:
* $X$ can be any value on an entire _interval_ (like $[0,1]$ or $(-\infin,\infin)$)
* For any $a$, $P(X=a)=0.$ (This is like taking an integral of a function over an empty interval -- the result will always be 0 regardless of the function.)

Instead of studying cases of $P(X=0)$, we instead focus on $P(a\le X\le b)$. Using "$\le$" and "$<$" is equivalent for continuous random variables, unlike the discrete case.

---
__Ex.__ Consider a chance wheel. Let $X$ be the angle that the arrow is pointing to after the wheel is spun. In this case, $X$ can take any value on the interval $[0,2\pi)$, so it's continuous.

You can see how it's pointless to ask what the probability is that $X$ lands _exactly_ on a specific angle, since it'll always be 0. Instead, we can calculate expressions like: $$
\begin{aligned}
    P(0\le X\le \pi)&=\frac{1}{2}=\frac{\pi}{2\pi}\\
    P(a\pi \le X\le b\pi)&=\frac{(b-a)\pi}{2\pi}=\frac{b-a}{2}\\
    P(a\pi \le X)=P(a\pi \le X \le 2\pi)&=\frac{2-a}{2}
\end{aligned}
$$

---
# Probability Density Function
We can add together the probabilities of $X$ being in consecutive intervals to get the probability of $X$ being in the union of the two intervals: $$
P(a_1\le X\le a_2)+P(a_2\le X\le a_3)=P(a_1\le X\le a_3).
$$ Integrals also have this property as well, so it could be useful to find a way to represent our probabilities using them.

We're looking for a function $f$ such that, for any $a\le b$, $$
P(a\le X\le b)=\int^{b}_{a}f(x)dx.
$$ We call $f$ the __probability density function__ _(pdf)_, __probability distribution__, or __density curve__ of $X$. This turns out to be the analogue of the probability mass function for continuous random variables.

Most of the continuous distributions we'll study don't really have easy-to-explain motivations behind them, but we can still start with a pdf function and derive all other properties from there (expected value, variance, cdf).

---
__Ex.__ Going back to our chance wheel example, $P(a_1\le X\le a_2)=\frac{a_2-a_1}{2\pi}$ for $0< a_1< a_2< 2\pi$.  
In this case, the probability density function $f(x)$ for $X$ should be $$
f(x)=\begin{cases}
    \frac{1}{2\pi}&x\in[0,2\pi)\\
    0&\text{otherwise}
\end{cases}
$$

---
## PDF Remarks
1. $f(x)\ge 0$ for all $x$.
2. $\int_{-\infin}^{\infin}f(x)dx=1.$
3. $P(X=a)\ne f(a)$, __don't mess this up!__
4. $P(a-\frac{1}{2}\Delta \le X\le a+\frac{1}{2}\Delta)\approx \Delta f(a)$

---
## Arbitrary PDFs
__Ex.__ Suppose the pdf of a random variable $X$ is $$
f(x)=\begin{cases}
    kx^2&0\le x\le 2\\
    0&\text{otherwise}
\end{cases}
$$
1. What is $k$? We know that the integral over all values of $f(x)$ has to equal $1$. $$
\begin{aligned}
    \int_{-\infin}^{\infin}f(x)dx&=\int_0^2 kx^2dx\\
    &=\frac{1}{3}kx^3\big|_0^2\\&=\frac{8}{3}k=1\\&\rightarrow k=\frac{3}{8}.
\end{aligned}
$$
2. Calculate $P(X\le 1)$. $$
\begin{aligned}
    P(X\le 1)&=\int_{-\infin}^1 f(x)dx\\
    &=\int_0^1 \frac{3}{8}x^2dx\\&
    =\frac{1}{8}x^3\big|_0^1=\frac{1}{8}.\\
\end{aligned}
$$

---
# Uniform Distribution
__Definition.__ A continuous random variable $X$ is said to be a __uniform distribution__ on an interval $[A,B]$ if its probability density function is $$
f(x;A,B)=\begin{cases}
    \frac{1}{B-A}&x\in[A,B]\\
    0&\text{otherwise}
\end{cases}
$$ Here, we say $X$ follows $\text{unif}(A,B)$. 

_(Note that our chance wheel example from before follows this distribution.)_

