# STAT 400
### Mon. January 27th, 2020
---

## Homework
* Homework is from the textbook (9th edition) -- required
* Homework is assigned every Friday on ELMS
    - Due during discussion on the next Thursday
* __No curve__ on _any_ grades

---
## Tentative Schedule
__Midterm Exams:__
* Week of Feb. 24th (Week 5)
* Week of April 6th (Week 11)

---

# Course Overview
This course is about __probability theory__ (2/3rds) and __statistics__ (1/3rd):
1. Sample space and events
2. Discrete random variables
3. Continuous random variables
4. Joint distributions and random samples
5. Advanced topics in probability
6. Point estimators and confidence intervals

These topics correspond to __Chapters 2 through 7__ in the textbook.

---
# Probability Theory
Probability theory is the study of randomness and uncertainty _quantitatively_.

__Ex.__ What's the probability that...
* ...you toss a coin and it lands on Heads?
* ...you roll a die and it lands on an odd number?
* ...the S&P 500 index will be above 3400 tomorrow?
* ...the highest temperature today is higher than the day after tomorrow?

Each of these is referred to as an __event__.
We assign a value to an event, called the __probability__ of the event.

---
## Events
We can represent events by the set of all outcomes that fulfill that event.

__Ex.__
* $\{\text{Heads}\}$
* $\{\text{odd numbers}\}$ or $\{1, 3, 5\}$
* $\{I>3400\}$
* $\{T_1>T_2\}$

(Note that there are _infinitely many_ outcomes that satisfy the 3rd and 4th events above, but only _finitely many_ outcomes that satisfy the 1st and 2nd.)

---
## Sample Space
__Definition.__ The collection of all _possible_ outcomes for an experiment is called the __sample space__ $S$ of the experiment.

__Ex.__
* $S=\{\text{Heads},\text{Tails}\}$
* $S=\{1,2,3,4,5,6\}$
* $S=(0,\infin)$
* $S=(a,\infin )\times (a,\infin )$ _(Cartesian product)_

With this definition, events are simply __subspaces__ of the sample space of the experiment they arise form.

An event is called __simple__ if it contains one outcome. _(ex. $\{\text{Heads}\}$)_
Likewise, an event is called __compound__ if it contains more than one outcome. _(ex. $\{1,3,5\}$)_

The probability of an event $A$ is then denoted as $P(A)$. _(ex. $P(\{\text{Heads}\})=\frac{1}{2}$)_