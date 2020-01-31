# STAT 400
## Fri. January 31st, 2020
---
# Applications of the Properties of Probability
__Ex.__ Suppose we have a random number generator. Each time it generates an integer between $1$ and $N$ (inclusive) with _equal probability_, that is $P(\{i\})=\frac{1}{N}$ for all integers $i$ between $1$ and $N$.
Suppose $N=100$.

1. What is the probability that it generates an even number?
$$
\begin{gathered}
    A=\{\text{even}\}=\{2,4,6...100\}\\
    P(A)=\frac{50}{100}=\frac{1}{2}
\end{gathered}
$$

2. What is the probability that it generates a multiple of $3$?
$$
\begin{gathered}
    B=\{\text{multiple of 3}\}=\{3,6,9,...99\}\\
    P(B)=\frac{33}{100}
\end{gathered}
$$

3. What is the probability that it generates a number that's even AND a multiple of $3$?
$$
\begin{gathered}
    A\cap B=\{\text{multiple of 6}\}=\{6,12,18...96\}\\
    P(A\cap B)=\frac{16}{100}
\end{gathered}
$$

4. What is the probability that it generates a number that's even OR a multiple of $3$? _(Note that we mean inclusive OR here)_
$$
\begin{gathered}
    A\cup B=\{2,3,4,6...99,100\}\\
    P(A\cup B)=P(A)+P(B)-P(A\cap B)=\frac{50}{100}+\frac{33}{100}-\frac{16}{100}=\frac{67}{100}.
\end{gathered}
$$

5. What is the probability that it generates a number that's even, a multiple of $3$, OR a multiple of $5$?

$$
\begin{gathered}
    C=\{\text{multiple of 5}\}\\
    P(A\cup B\cup C)=P(A)+P(B)+P(C)-P(A\cap B)-P(A\cap C)-P(B\cap C)+P(A\cap B\cap C)\\
    =\frac{50}{100}+\frac{33}{100}+\frac{20}{100}-\frac{16}{100}-\frac{10}{100}-\frac{6}{100}+\frac{3}{100}\\
    =\frac{64}{100}.
\end{gathered}
$$

---
# Counting Techniques
Consider a sample space $S$ that contains _finitely_ many outcomes.
Then for an event $A=\{x_1,x_2...x_n\}$ in $S$, 
$$P(A)=\sum_{i=1}^n P(E_i)$$
where $E_i=\{x_i\}$ is a simple event.

__Ex.__ Consider a train with five cars, labeled $1$ through $5$.
A passenger is twice as likely to enter $3$ as they are to enter $2$ or $4$, and is also twice as likely to enter $2$ or $4$ as they are to enter $1$ or $5$. What is the probability for each car that a passenger will enter?
$$
\begin{gathered}
    P(\{i\})=p_i\\
    p_3=2p_2=2p_4\\
    p_2=p_4=2p_1=2p_5\\
    p_1=p_5=x \rightarrow p_2=p_4=2x,\ p_3=4x\\\\
    1=P(S)=p_1+p_2+p_3+p_4+p_5\\
    =x+2x+4x+2x+x\rightarrow 1=10x \rightarrow x=\frac{1}{10}
\end{gathered}
$$
Now we can calculate the probability of a passenger entering each individual car using the value of $x$.

## Equally Likely Outcomes
If we assume the probability of each outcome to be the same, i.e. there is a $p$ such that $P(E_i)=p$ for all simple events $E_i$, then $p=\frac{1}{N}$ and $P(A)=np=\frac{n}{N},$ where $n$ is the number of elements in $A$ and $N$ is the number of elements in $S$.

---
# Tuples
__Definition.__ An _ordered_ sequence of $k$ elements is called a __k-tuple__. _(2-tuples are also called pairs, and 3-tuples may be called triplets.)_ They're usually written with parentheses around the elements, i.e. $(\text{Heads}, \text{Tails}, \text{Tails})$.

Whenever $k$ _distinguishable_ outcomes occur in an experiment, we can represent the elements in the sample space of that experiment as $k$-tuples.

For example, if we flipped a coin twice, we could represent each possible event from this experiment as a pair, where the first element is the result of the first flip and the second element is the result of the second flip. However, if we flipped two coins _simultaneously_, the two flips are _indistinguishable_, so we can't use tuples to represent the events.

## Product Rule for Tuples
Consider a sample space $S$ whose elements are $k$-tuples. Let $n_i$ be the number of ways of selecting the $i$th element of each tuple, where $1\le i\le k$. Then
$$
N(S)=n_1n_2...n_k=\prod_{i=1}^k n_i,
$$ where $N(S)$ denotes the number of elements in $S$.
We can use this rule to quickly calculate the number of elements in a sample space containing tuples.