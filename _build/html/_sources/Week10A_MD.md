

# Inverse of a matrix: proof of the adjoint method {#sec:adjointmethod}

For any matrix $A$, we can define the adjoint of a matrix
$\mathop{\mathrm{adj}}A$ as the matrix containing all the cofactors, and
taking the transpose: 

$$

\begin{aligned}
 A =
  \begin{pmatrix}
  a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33}
 \end{pmatrix}
 \quad\longrightarrow\quad
 \mathop{\mathrm{adj}}A =
  \begin{pmatrix}
  A_{11} & A_{21} & A_{31} \\ A_{12} & A_{22} & A_{32} \\ A_{13} & A_{23} & A_{33}
 \end{pmatrix}\, .
\end{aligned}

$$

 Note that the adjoint is not at all the same as the
Hermitian adjoint operator $\dagger$ from section
[4.4](#sec:special){reference-type="ref" reference="sec:special"}! In
fact, while the $\dagger$ is easy to calculate, the adjoint requires us
to calculate $n^2$ cofactors, which can be a lot of work.

Now consider the top left ("11") component of the matrix product
$A \mathop{\mathrm{adj}}A$: 

$$

\begin{aligned}
 (A \mathop{\mathrm{adj}}A)_{11} = a_{11} A_{11} + a_{12} A_{12} + a_{13} A_{13} = \det A\, .
\end{aligned}

$$

 This element is the determinant of $A$. Similarly, we
can calculate the "12" element of the matrix product
$A \mathop{\mathrm{adj}}A$: 

$$

\begin{aligned}
 (A \mathop{\mathrm{adj}}A)_{12} = a_{11} A_{21} + a_{12} A_{22} + a_{13} A_{23} = 0\, .
\end{aligned}

$$

 This expression is zero, because it is equal to the
determinant of $A$ with the second row replaced with the first one
(write this out for a $3\times 3$ matrix if you do not see it). Since we
now have a matrix with two identical rows, the determinant is zero.
Continuing this type of argument, you can show that therefore


$$

\begin{aligned}
 A \mathop{\mathrm{adj}}A = 
 \begin{pmatrix}
  \det A & 0 & 0 \\ 0 & \det A & 0 \\ 0 & 0 & \det A
 \end{pmatrix}
 = \det A \; I\, .
\end{aligned}

$$

 Since $\det A$ is just a number, we have that


$$

\begin{aligned}
 A \left( \frac{\mathop{\mathrm{adj}}A}{\det A} \right) = I \quad\rightarrow\quad A^{-1} = \frac{\mathop{\mathrm{adj}}A}{\det A}\, .
\end{aligned}

$$

 Calculating the cofactors and the determinant of $A$
therefore allows you to find the inverse of $A$ directly. The argument
above works for all $n\times n$ matrices.

Note that the inverse does not exist if the determinant is zero. You can
understand this from the meaning of the determinant we explored above: a
zero determinant operation maps vectors onto spaces of a lower
dimension. Since the inverse of a matrix is the transformation that
"undoes" the effect of the original matrix, it should take any vector
back to its original. However, if more than one vector gets mapped to
the same transformed vector, the reverse operation will not be able to
tell which of the possible input vectors the original matrix operated
on.

