# STAT 400
## Mon. February 3rd, 2020
---

# Permutations vs. Combinations

There's an important distinction between the experiments "Toss a coin three times" and "Toss three identical coins at once".

For the first, the outcomes are _distinct_, so we can use tuples to represent the events (thus _ordering_ the outcomes) and use the product rule to count the sample space: $$S=\{HHH,\ HHT,\ HTH,\ HTT,\ THH,\ THT,\ TTH,\ TTT\}$$

For the second, the outcomes are _not distinct_, so our sample space is different: $$S=\{HHH,\ HHT,\ HTT,\ TTT\}$$

__Definition.__ An _ordered_ sequence is called a __permutation.__ An _unordered_ subset is called a __combination.__
We denote by $P_{k,n}$ the number of permutations of size $k$ that can be made with $n$ objects, and likewise by $C_{k,n}$ (or ${n \choose k}$) the number of combinations.

---
__Ex.__ A match between two teams has 5 rounds. Each round is one-on-one. The coach needs to pick 5 players out of 9 team members to play. How many choices do they have in total?

The rounds are ordered, so we need to count _permutations_: $N(S)=P_{5,9}$. $$P_{5,9}=9\cdot 8\cdot 7\cdot 6\cdot 5=\frac{9!}{4!}.$$
By this logic, we see that in general, $$P_{k,n}=n(n-1)(n-2)...(n-k+1)=\frac{n!}{(n-k)!}.$$

---
__Ex.__ Draw four cards from a standard deck of cards, including two jokers (54 cards in total). What is the probability that all four cards are the same rank?

$$
\begin{gathered}
    A=\{\text{four of the same rank}\}\\
    N(A)=13\ \text{(since there's 13 ranks)}
\end{gathered}
$$

The order of the cards doesn't matter, so to find the size of the whole sample space we need to count _combinations_: $N(S)=C_{4,54}$. 
For each combination of $4$ elements, there are $4\cdot 3\cdot 2\cdot 1$ permutations that represent it. $$P_{4,54}=C_{4,54}\cdot 4!\rightarrow C_{4,54}=\frac{P_{4,54}}{4!}=\frac{54!}{50!\ 4!}$$
By this logic, we see that in general, $$C_{k,n}=\frac{P_{k,n}}{k!}=\frac{n!}{(n-k)!\ k!}.$$

Returning to the problem, since each rank is equally likely to be selected, our final probability is simply $$P(A)=\frac{N(A)}{N(S)}=\frac{13\cdot 50!\cdot 4!}{54!}.$$

---
__Ex.__ Suppose a music playlist contains 100 songs. Ten of them are by The Cranberries. Songs are selected randomly from the list and played. What is the probability that the first Cranberries song played is the sixth song played?

We can represent the playlist as an ordered sequence. Since we only care about the songs up to and including the sixth, we can ignore the rest of the list, giving us a sequence of length 6. Thus, $N(S)=P_{6,100}$.

In order for our event to succeed, the first five songs need to be _not_ by The Cranberries, and the sixth one does. Thus, $N(A)=P_{5,90}\cdot 10$. _(Note that even though the order of these songs doesn't matter, we've represented our sample space with permutations, so we must represent the event with permutations as well. Otherwise we're comparing apples to oranges.)_

Finally, $$P(A)=\frac{N(A)}{N(S)}=\frac{P_{5,90}\cdot 10}{P_{6,100}}.$$

---
# Conditional Probability
If you want to know the probability that some event $A$ occurred, and you already know that another event $B$ occurred in the same experiment, then you can shrink your sample size to accommadate for this extra information, which affects the probability.

__Definition.__ For any two events $A$ and $B$ with $P(B)\gt 0$, the __conditional probability__ of $A$, given that $B$ occurred, is defined by $$P(A\mid B)=\frac{P(A\cap B)}{P(B)}.$$

__Ex.__ A store is analyzing the behavior of its shoppers, focusing on the purchase of milk products and diapers. They sampled 100 customers:
* 10 customers bought both milk products and diapers.
* 8 customers bought only milk products.
* 2 customers bought only diapers.
* 80 customers bought neither.

1. What is the probability that a customer bought milk products ($A$)?
    - $P(A)=\frac{18}{100}$.
2. What is the probability that a customer bought diapers ($B$)?
    - $P(B)=\frac{12}{100}$.
3. _If a customer bought diapers_, what is the probability that they will buy milk products?
    - $P(A\mid B)=\frac{P(A\cap B)}{P(B)}=\frac{10}{12}$.