# STAT 400
## Wed. January 29th, 2020
----

# Sample Space & Events

In our example of a coin flip, where $S=\{H,T\}$, we can list out _all possible events_ (all subsets of $S$):
* $\{H\}$
* $\{T\}$
* $\{H,T\}$
* $\empty$ (null set/null event)

We can do the same with our die roll example, $S=\{1,2,3,4,5,6\}$:
* $\empty$
* $\{1\}, \{2\}, \{3\}...\{6\}$
* $\{1,2\}, \{1,3\}... \{1,6\},\{2,3\}...\{6,6\}$
* $...$
* $\{1,2,3,4,5,6\}$

All of these events can be assigned probability values, as we previously discussed.

The key thing to remember about probability values is that they represents __frequency over the long run__ -- in other words, it's the average amount of times that an event will occur if an experiment is repeated many times.

---
# Operations on Events
What is the probability that...
1. ...event $A$ _doesn't_ happen?
2. ..._both_ event $A$ and event $B$ happen?
3. ..._either_ event $A$ or $B$ happens?

These questions represent _new_ events that are generated from information about other events.

__Definition 1.__ $A'$ or $A^C$ is called the __complement__ of $A$ -- the event where $A$ _doesn't_ happen.

__Definition 2.__ $A\cap B$ is called the __intersection__ of $A$ and $B$ -- the event where _both_ $A$ and $B$ happen.

__Definition 3.__ $A\cup B$ is called the __union__ of $A$ and $B$ -- the event where _either_ $A$ or $B$ happens.

Thus our three questions can be represented by $P(A')$, $P(A\cap B)$, and $P(A\cup B)$.

Because these operations give new events, we can chain multiple of them together: $P(A\cap B\cap C)$ is the probability that $A$, $B$, _and_ $C$ all occur.

---
## Mutually Exclusive/Disjoint Events
__Definition.__ When $A\cap B=\empty$, $A$ and $B$ are said to be __mutually exclusive__ (or __disjoint__) events. This implies that it is not possible for $A$ and $B$ to both occur in a given experiment.

---
# Properties of Probability

## Axioms of Probability
1. $P(A)\ge 0$ for all events $A$.
2. $P(S)=1$ for all sample spaces $S$.
3. If $A_1,A_2,...$ is an infinite sequence of disjoint events, then $P(A_1\cup A_2\cup ...)=\sum_{i=1}^\infin P(A_i)$.

We can derive all other properties of probability from these three axioms.

## Properties
1. $P(\empty)=0$.
2. If $A_1,A_2...A_n$ is a finite sequence of disjoint events, then $P(A_1\cup A_2\cup ...\cup A_n)=\sum_{i=1}^n P(A_i)$. _(Finite version of 3rd axiom)_
3. $P(A)+P(A')=1$.
    * $A\cap A'=\empty$
    * $A\cup A'=S$
4. $P(A) \le 1$.
5. $P(A\cup B)=P(A)+P(B)-P(A\cap B)$. _(You need to subtract away the probability of events in $A$ AND $B$ so they don't get double counted)_
6. $P(A\cup B\cup C)=P(A)+P(B)+P(C)-P(A\cap B)-P(B\cap C)-P(A\cap C)+P(A\cap B\cap C)$. _(Same reasoning as above)_