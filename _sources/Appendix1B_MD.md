# Calculating the inverse of a matrix through row reduction

Another way to calculate the inverse of a matrix is to use row reduction
(also called Gaussian elimination). The rules of row reduction are

-   multiply any row by a nonzero constant $\lambda \neq 0$;

-   interchange rows;

-   add a multiple of one row to another.

To find the inverse of $A$, we set up a new matrix made up of $A$ and
$I$ next to each other with a line between them just to remind us where
the separation is between the orignal matrices i.e. we write a
rectangular matrix of the form $(A|I)$. Then we apply rules of row
reduction until we obtain the form $(I|B)$. Then $B = A^{-1}$. An
example will make this method clearer. Suppose we have a matrix $A$ with


$$
\begin{aligned}
 A = 
 \begin{pmatrix}
  1 & 3 \\ 2 & 7
 \end{pmatrix}\, .
\end{aligned}
$$

 Row reduction proceeds as follows: first we remove twice
the first row from the second row and then we remove three times the
second row from the first row i.e. 

$$
\begin{aligned}
 \left(
 \begin{matrix}
   1 & 3 \\ 2 & 7
 \end{matrix}
 \left\vert
 \begin{matrix}
   1 & 0 \\ 0 & 1
 \end{matrix}
 \right.
 \right)
 \xrightarrow{r_2 \to r_2 - 2 r_1}
  \left(
 \begin{matrix}
   1 & 3 \\ 0 & 1
 \end{matrix}
 \left\vert
 \begin{matrix}
   1 & 0 \\ -2 & 1
 \end{matrix}
 \right.
 \right)
 \xrightarrow{r_1 \to r_1 - 3 r_2}
  \left(
 \begin{matrix}
   1 & 0 \\ 0 & 1
 \end{matrix}
 \left\vert
 \begin{matrix}
   7 & -3 \\ -2 & 1
 \end{matrix}
 \right.
 \right)
\end{aligned}
$$

 where $r_j$ denotes the $j^{\rm th}$ row. The inverse of
$A$ is therefore 

$$
\begin{aligned}
 A^{-1} =
  \begin{pmatrix}
   7 & -3 \\ -2 & 1
 \end{pmatrix}\, .
\end{aligned}
$$

 You can check that indeed $A^{-1} A = I$.
