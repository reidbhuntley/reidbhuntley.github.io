# STAT 400
## Wed. February 5th, 2020
---

# Conditional Probability cont.

Recall our definition of conditional probability from the last lecture: $P(A\mid B)=\frac{P(A\cap B)}{P(B)},\ P(B)>0$.

If we know $P(A\mid B)$ and $P(B)$, we get $P(A\cap B)=P(A\mid B)\cdot P(B)$.
Applying this fact twice, $P(A\cap B\cap C)=P(A\mid B\cap C)\cdot P(B\cap C)=P(A\mid B\cap C)\cdot P(B\mid C)\cdot P(C)$.

---
__Ex.__ Using the example from last time:

$\frac{12}{100}$ customers bought diapers ($P(C)$). Among them, $\frac{10}{12}$ bought milk products ($P(B\mid C)$).
Additionally, among customers that bought both diapers and milk products, $\frac{8}{10}$ of them bought cribs ($P(A\mid B\cap C)$).

What is the probability that someone bought all three items? $$P(A\cap B\cap C)=\frac{8}{10}\cdot \frac{10}{12}\cdot \frac{12}{100}=\frac{8}{100}.$$ 

---
__Ex.__ In a store, 50% of DVDs sold are from Brand 1, 30% are from Brand 2, and 20% are from Brand 3. Among them, 25% of discs from Brand 1 will break within a year, as will 20% from Brand 2 and 10% from Brand 3.

a) What is the probability that a DVD sold from this store needs repair within a year? $$\begin{gathered}
    A_1=\{\text{Brand 1}\},\ A_2=\{\text{Brand 2}\},\ A_3=\{\text{Brand 3}\}\\
    B=\{\text{need repair in a year}\}\\
\end{gathered}$$$$
\begin{aligned}
    P(B)&=P(B\cap A_1)+P(B\cap A_2)+P(B\cap A_3)\\
    &=P(B\mid A_1)\cdot P(A_1)+P(B\mid A_2)\cdot P(A_2)+P(B\mid A_3)\cdot P(A_3)\\
    &=\frac{25}{100}\cdot \frac{50}{100}+\frac{20}{100}\cdot \frac{30}{100}+\frac{10}{100}\cdot \frac{20}{100}\\
    &=0.125+0.06+0.02\\
    &=0.205.
\end{aligned}
$$

b) Given a DVD that breaks within a year, what is the probability that it was made by each brand? $$\begin{aligned}
    P(A_1\mid B)&=\frac{P(A_1\cap B)}{P(B)}=\frac{P(B\mid A_1)\cdot P(A_1)}{P(B)}\\
    &=\frac{0.25\cdot 0.5}{0.205}\\
    &\approx 0.61.
\end{aligned}
$$ In general, $$\begin{gathered}
    P(A_j\mid B)&=\frac{P(B\mid A_j)\cdot P(A_j)}{P(B)}.
\end{gathered}$$

---
# Total Probability
__Definition.__ The event $\{A_1...A_k\}$ is __exhaustive__ if one of $A_i$ _must_ occur, i.e. $S=A_1\cup A_2...\cup A_k$.

## The Law of Total Probability
Let $\{A_1...A_k\}$ be _exhaustive_ and _exclusive_ (all of its members are disjoint with each other). Then, given another event $B$, $$\begin{aligned}
    P(B)&=P(B\mid A_1)P(A_1)+P(B\mid A_2)P(A_2)+...+P(B\mid A_k)P(A_k)\\
    &=\sum_{i=1}^k P(B\mid A_i)P(A_i).
\end{aligned}$$

We implicitly used this rule to calculate $P(B)$ in the previous example, because the three brands were _exhaustive_ (you couldn't buy any other brands of DVDs at the store) and _exclusive_ (each DVD was made by only one brand).

## Bayes's Theorem
Using the same constraints on $\{A_1...A_k\}$, Bayes's theorem states:

$$P(A_j\mid B)=\frac{P(A_j\cap B)}{P(B)}=\frac{P(B\mid A_j)P(A_j)}{\sum_{i=1}^k P(B\mid A_i)P(A_i)}.$$

Here $P(A_j)$ is called the _prior probability_ of event $A_j$, and $P(A_j\mid B)$ is called the _posterior probability_ of event $A_j$ given that $B$ occurred.

---
# Independence
__Definition.__ Two events $A$ and $B$ are __independent__ if $P(A\mid B)=P(A).$ Otherwise, we say they are __dependent__.

The intuition for this is that knowing whether $B$ did or didn't occur doesn't give you any more information about the chance of $A$ occurring.
