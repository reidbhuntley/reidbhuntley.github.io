# MATH 240
### Wed. August 28th, 2019
---

# Chap. 1.1 (cont.)/1.2
---
## Elementary Row Operations
1. Interchange two rows
2. Add a constant multiple of one row to another row
3. Multiply a row by a _nonzero_ constant

__Definition:__ Two matrices `A` and `B` are row-equivalent if `B` can be created by only performing elementary row operations on `A`.  
Row-equivalency follows the __transitive property__, just like equality does.

__Theorem:__ If two systems of linear equations have row-equivalent augmented matrices, then they have the _same_ solution set.

---
## Echelon Form
Requirements:
* Rows with all zeroes are below rows with nonzero entries.
* Leading entry of each row is in a column to the right of the leading entry of the row above it.
    - _(Leading entry = first nonzero entry of a row)_
* All entries in a column below a leading entry are zeroes.

Example:
* $\begin{pmatrix}
0&1&0\\1&1&0\\0&0&1
\end{pmatrix}$ IS NOT in echelon form.
* $\begin{pmatrix}
1&1&0\\0&1&0\\0&0&1
\end{pmatrix}$ IS in echelon form. _(Only differs by one row operation from previous matrix)_

---
## Reduced Echelon Form (REF)
Requirements:
* Must be in echelon form.
* All leading entries must be 1.
* Each leading entry must be the only nonzero entry in its row/column.

Example:
* $\begin{pmatrix}
1&1\\0&2
\end{pmatrix}$ IS NOT in REF.
* $\begin{pmatrix}
1&1\\0&1
\end{pmatrix}$ IS NOT in REF.
* $\begin{pmatrix}
1&0\\0&1
\end{pmatrix}$ IS in REF. _(Created from original matrix using only row operations, so they are row equivalent)_

__Theorem:__ Every matrix `A` is row-equivalent to exactly ONE reduced echelon matrix.  
This also means that the order that the row operations are performed in to create the REF matrix doesn't matter in the end.

__Definition__: A __pivot position__ in a matrix `A` is a location that corresponds to a leading entry in the reduced echelon form of `A`.  A __pivot column__ of `A` is a column that contains a pivot position.

---
## Reducing a matrix
__Step I:__ Begin with the leftmost nonzero column. This will be a pivot column. 
$$\begin{pmatrix}
0&3&-6&6&4\\
3&-7&8&-5&8\\
3&-9&12&-9&6
\end{pmatrix}$$
 
__Step II:__ Interchange rows so that zeroes are at the bottom, if necessary.
$$\begin{pmatrix}
3&-9&12&-9&6\\
3&-7&8&-5&8\\
0&3&-6&6&4
\end{pmatrix}$$

__Step III:__ Use row operations to create zeroes in all positions below the pivot.
$$\begin{pmatrix}
3&-9&12&-9&6\\
0&2&-4&4&2\\
0&3&-6&6&4
\end{pmatrix}$$

__Step IV:__ Ignore the row containing the pivot in the current column _(and any rows above it)_. Repeat steps I-IV to get an echelon matrix.
$$\begin{pmatrix}
3&-9&12&-9&6\\
0&2&-4&4&2\\
0&0&0&0&1
\end{pmatrix}$$

__Step V:__ Multiply each row by the reciprocal of its leading entry.
$$\begin{pmatrix}
1&-3&4&-3&2\\
0&1&-2&2&1\\
0&0&0&0&1
\end{pmatrix}$$

__Step VI:__ Now start at the _rightmost_ pivot and use its row to make the entries above it zeroes.
$$\begin{pmatrix}
1&-3&4&-3&0\\
0&1&-2&2&0\\
0&0&0&0&1
\end{pmatrix}$$

__Step VII:__ Repeat step VI for each pivot.
$$\begin{pmatrix}
1&0&-2&3&0\\
0&1&-2&2&0\\
0&0&0&0&1
\end{pmatrix}$$
