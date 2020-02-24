# STAT 400
## Mon. February 24th, 2020
---

# Poisson Distribution

__Definition.__ A discrete random variable $X$ follows the __Poisson distribution__ with parameter $\mu$ ($\mu >0$) if its probabilty mass function is $$
P(X=k)=p(k;\mu)=\frac{\mu^k}{k!}e^{-\mu}
$$ for $k=0,1,2...$

The cumulative distribution function for $X$ has no closed form; you should use a Poisson table to calculate it.

---

__Observation.__ Recall that the Taylor series expansion of $e^\mu$ is $$
e^\mu=1+\mu +\frac{\mu^2}{2!}+\frac{\mu^3}{3!}+...=\sum_{k=0}^\infty \frac{\mu^k}{k!}
$$ Using this fact, we see that the sum of all possible values of $p(k;\mu)$ is $$
\sum_{k=0}^\infty p(k;\mu) =\sum_{k=0}^\infty \frac{\mu^k}{k!}e^{-\mu}=e^\mu e^{-\mu}=1,
$$ which is what we'd expect for a useful distribution.

---

__Proposition.__ Suppose $X$ follows $\text{bin}(n,p)$. As $n\rightarrow \infin$, $p\rightarrow 0$, and $np\rightarrow \mu$, then $X$ converges towards the Poisson distribution $\text{Pois}(\mu)$.

(_Rule of thumb:_ When $n>50$ and $np<5$, we can use the above proposition to approximate $\text{Pois}(\mu)$ with $\text{bin}(n,p)$ and vice-versa.)


The Poisson distribution can be used to model the number of random visits/arrivals that will occur in a fixed period of time.

__Ex.__ 100 people pass by a store in 10 minutes. The probability that any one enters the store is 0.02. If $X$ is the number of people that entered, then $X$ follows $\text{bin}(100,0.02)$.
Following our rule of thumb, we can approximate the probability mass function of $X$ with $\text{Pois}(\mu)=\text{Pois}(np)=\text{Pois}(2)$.

---
## Expected Value and Variance
Suppose $X$ follows $\text{Pois}(\mu)$. Then $E(X)=\mu$ and $V(X)=\mu$. This interesting property is another reason we study the Poisson distribution.

---
## Sum of Poisson Distributions
Suppose a collection of random variables $X_i$ all follow $\text{Pois}(\mu_i)$. Think of them as representing the number of visits that occur in a _sequence_ of time periods -- they are independent.

If we sum all $X_i$ to produce a new random variable $Y$, then $Y$ also follows $\text{Pois}(\mu)$, where $\mu$ is the sum of all $\mu_i$. (Binomial distributions also have this property.)

---
# Poisson Process

Suppose $X_1$ follows $\text{Pois}(t_1\mu)$ and represents the number of visits from time 0 to time $t_1$, and $X_2$ follows $\text{Pois}(t_2\mu)$ and represents the number of visits from time $t_1$ to time $t_1+t_2$. _(Note that $t_1$ and $t_2$ are durations of time, not points in time.)_

Then $X$, the number of visits from time 0 to time $t_1+t_2$, is simply $X_1+X_2$ and follows $\text{Pois}((t_1+t_2)\mu)$, from the sum property described above.

---

__Definition.__ Given parameter $\mu$, suppose visits occur at times $T_1\le T_2\le T_3\le ...$
Let $X(s,t)$ be the number of visits from time $s$ to time $t$, with $0< s < t$. In other words, $X(s,t)=N\{i: T_i\in [s,t]\}$.

If $X(s,t)$ follows $\text{Pois}((t-s)\mu)$, then we call the collection of $\{X(s,t):0< s< t\}$ a __Poisson process.__ Here, $\mu$ is the parameter of the Poisson process, also called the __rate__ of the process.

---
## Properties
From the observations we've made before, we see that $X(0,t_1)+X(t_1,\ t_1+t_2)=X(0,\ t_1+t_2)$; the sum of visits of two consecutive intervals of time is the same as visits made over the union of those intervals, which makes sense intuitively. This can also be expanded to sum over any number of intervals.

---
# Expected Value and Variance of Sums of Discrete Random Variables

If $X_1,X_2,...X_n$ are arbitrary discrete random variables, then $$E(X_1+X_2+...+X_n)=E(X_1)+E(X_2)+...+E(X_n)$$ since $E$ is linear.

In addition, if these variables are all _independent_ and _identically distributed_, then $$
V(X_1+X_2+...+X_n)=nV(X_1).
$$