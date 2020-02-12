# STAT 400
## Mon. February 10th, 2020
---

# Random Variables (cont.)
We use random variables to assign numbers to outcomes. This is notated as $X(W)=x,\ W\in S,\ x\in \R$ where $X$ is the random variable and $S$ is a sample space.

## Types of Random Variables

__Definition.__ Any random variable whose only values are 0 or 1 is called a __Bernoulli random variable__.

__Definition.__ A __discrete random variable__ is one whose possible values are _countable_. (They can be listed in a finite or infinite sequence.) A __continuous random variable__ is a random variable whose possible values are all the numbers in an interval or a union of such intervals, and the probability of each _single_ value is 0 (that is, $P(x=c)=0$ for all $c$).

---

__Ex.__ Suppose we test a sequence of batteries until we reach one with an acceptable battery life. We denote acceptable battery life with $S$ and use $F$ otherwise. $$S=\{S,\ FS,\ FFS,\ FFFS...\}$$ We define a random variable $X$ to be the number of failures in an outcome. $$X(S)=0,\ X(FS)=1,\ X(FFS)=2...$$ We say that $X$ takes _countably_ infinitely many possible values -- thus it is discrete. This is different from, for example, a random variable that returns values over the interval of real numbers from 0 to 1, which contains _uncountably_ infinitely many possible values.

---
# Probability Distribution for Discrete Random Variables

Once we assign values to outcomes using random variables, the context of the problem doesn't matter any more.  
For example, when tossing a coin we can represent heads as 1 and tails as 0. Similarly, when performing an experiment we can represent success as 1 and failure as 0. We can now use the same expressions to represent both problems -- we've _abstracted_ the problems.

__Definition.__ The __probability distribution__ or __probability mass function__ (_pmf_) of a discrete random variable is defined for every number $x$ by $p(x)=P(X=x)=P(W\in S:X(W)=x).$

By employing random variables, our probability distribution $p$ is now simply function that maps a discrete set of numbers to $[0,1]$, so it's easier for us to reason about.

__Remark.__ By properties of probability, $$p(x)\ge 0$$ and $$\sum_{\text{all possible }x}p(x)=1.$$

---

__Ex.__ We have samples from five blood donors $a,b,c,d,e$. Only $a$ and $b$ have O+ type blood. We test samples randomly one after another until we find one of type O+. Let $X$ be the number of tests until we find an O+ type sample. What is the probability distribution $p(X)$ for this experiment? $$
\begin{aligned}
    p(1)&=P(X=1)=\frac{2}{5}=0.4\\
    p(2)&=P(X=2)=\frac{3}{5}\cdot \frac{2}{4}=0.3\\
    p(3)&=p(X=3)=\frac{3}{5}\cdot \frac{2}{4} \cdot \frac{2}{3}=0.2\\
    p(4)&=p(X=4)=\frac{3}{5}\cdot \frac{2}{4} \cdot \frac{1}{3}\cdot 1=0.1\\
    p(X)&=0\text{ otherwise}
\end{aligned}
$$

Now that we have an exhaustive list of input-output pairs, we could write this data into a chart, line graph, or histogram for better clarity.

We can also find the value of expressions like $P(X\le 3)$ and $P(X<3)$ by summing the probabilities of the values that satisfy those constraints.

---
# Parameters of Probability Distributions
__Definition.__ Suppose the probability mass function (pmf) depends on a quantity. Each possible value of this quantity determines a different probability distrubution. We call this such a quantity a __parameter__. The collection of _all_ probability distributions corresponding to different parameters is called a __family__ of probability distrubutions.
