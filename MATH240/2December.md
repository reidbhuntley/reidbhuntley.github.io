# MATH 240
### Mon. December 2nd, 2019
---

# Least Squares _(cont.)_
_From last Monday:_
The set of least squares solutions of $Ax=b$ coincides with the _non-empty_ solution set of $A^TAx=A^Tb$.

__Theorem.__ Let $A$ be an $m\times n$ matrix. The following statements are equivalent:
* The equation $Ax=b$ has a unique solution for each $b$ in $\R^m$.
* The columns of $A$ are linearly independent.
* The matrix $A^TA$ is invertible.

_Note that we can't say for sure that $A$ is invertible because it's not necessarily a square matrix._

When these statements are true, then the least squares solution is given by $(A^TA)^{-1}A^Tb$.

---
__Theorem.__ Given an $m\times n$ matrix $A$ with linearly independent columns, let $A=QR$ be a $QR$ factorization of $A$. Then for each $b$ in $\R^m$, the equation $Ax=b$ has a least squares solution given by $\hat{x}=R^{-1}Q^Tb$.

---

# Application of Least Squares
## Line of Best Fit

If we have a set of data points $(x_1,y_1), (x_2,y_2), ... (x_n,y_n)$, we want to be able to find a __line of best fit__ for this data set of the form $y=\beta_0+\beta_1x$.
To do this, we have to solve for $\beta_0$ and $\beta_1$ so that the sum of the distances from each data point to our line is minimized.

The input of the $i$th data point is $x_i$, the predicted value from our line is $\beta_0+\beta_1x_i$, and the actual value is $y_i$. We can format this idea as a matrix equation by using the matrices

$$X=\begin{pmatrix}
    1&x_1\\1&x_2\\...&...\\1&x_n
\end{pmatrix},\ \beta=\begin{pmatrix}
    \beta_0\\ \beta_1
\end{pmatrix},\ y=\begin{pmatrix}
    y_1\\y_2\\...\\y_n
\end{pmatrix}.$$

Now we just need to find a vector $\beta$ such that $X\beta$ is as close to $y$ as possible, i.e. a __least squares solution__ to the equation $X\beta=y$.

_(Note that we could only find an exact solution to this equation if all the data points were already on one line.)_

As we showed before, this is equivalent to the exact solution $\beta$ of the equation $X^TX\beta=X^Ty$, i.e. $\beta=(X^TX)^{-1}X^Ty$.
