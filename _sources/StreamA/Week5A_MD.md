# Special matrices {#sec:special}

In the previous sections we covered the basic techniques of matrix
algebra. Here, we will consider some special types of matrices.

### Square matrices

When the size of a matrix is $n\times n$, we call the matrix *square*.
Since two square matrices $A$ and $B$ are of the same size, we can
multiply them in two ways $AB$ or $BA$ and obtain a matrix of the same
size as $A$ and $B$. However, in general $AB$ is not the same as $BA$.

In the special case where $AB = BA$, the matrices $A$ and $B$ are said
to *commute*. We can also construct a new matrix, called the
*commutator* of $A$ and $B$, as follows: 

$$

\begin{aligned}
= AB - BA \, .
\end{aligned}

$$

 Matrices commute if the commutator is zero. In quantum
mechanics, matrices that do not commute are related to uncertainty
relations.

The *trace* of an $n\times n$ square matrix is simply the sum of the
diagonal (top left to bottom right) elements i.e. 

$$

\begin{aligned}
 \mbox{Tr}A = \sum_{j=1}^n a_{jj}\, .
\end{aligned}

$$



### Identity matrix

The identity matrix $I$ is defined as the square matrix that when
multiplied with any other matrix of the same size returns that matrix
i.e. 

$$

\begin{aligned}
 IA = A \qquad \text{and}\qquad AI = A\, .
\end{aligned}

$$

 In matrix form, the identity matrix has zeros everywhere
and ones on the diagonal (from the top left to the bottom right). The
identity matrix is therefore the matrix multiplication equivalent to the
number 1.

For example, here are the $2\times 2$ and $3\times 3$ identity matrices:


$$

\begin{aligned}
 I_2= 
 \begin{pmatrix}
 1 & 0 \\ 0 & 1
\end{pmatrix}  
\qquad\text{and}\qquad
 I_3= 
 \begin{pmatrix}
 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 
\end{pmatrix} \, . 
\end{aligned}

$$

 The elements of the identity matrix can be denoted by
$\delta_{jk}$, which is called the *Kronecker delta*, given by


$$

\begin{aligned}
 \delta_{jk} = 
 \begin{cases}
  0 & \text{if}~ j \neq k\, , \cr
  1 & \text{if}~ j = k\, .
 \end{cases}
\end{aligned}

$$



### Real matrix

When all the elements in a matrix are real, we call the matrix a real
matrix i.e. 

$$

\begin{aligned}
 A^* = A \, .
\end{aligned}

$$

 Similarly, when the elements are complex we call the
matrix a complex matrix.

### Symmetric matrix

Symmetric matrices are matrices that are invariant (i.e., does not
change) after taking the transpose i.e. 

$$

\begin{aligned}
 A^T = A\, .
\end{aligned}

$$

 In index notation we express this as $a_{jk} = a_{kj}$.
You can recognise symmetric matrices by spotting mirror symmetry in the
diagonal.

### Hermitian matrix

When the Hermitian conjugate of a matrix is identical to that matrix,
the matrix is called Hermitian: 

$$

\begin{aligned}
 A^\dagger = A\, .
\end{aligned}

$$

 In section [4.7](#sec:eigen){reference-type="ref"
reference="sec:eigen"} we will learn about the eigenvalues of a matrix,
and Hermitian matrices always have real eigenvalues even though the
elements of Hermitian matrices are not necessarily real. This property
of having real eigenvalues makes them of special interest in physics. An
example of Hermitian matrices used in quantum mechanics are the Pauli
matrices: 

$$

\begin{aligned}
 \sigma_x = 
 \begin{pmatrix}
  0 & 1 \cr 1 & 0
 \end{pmatrix}\, ,
 \qquad
 \sigma_y = 
 \begin{pmatrix}
  0 & -i \cr i & 0
 \end{pmatrix}\, ,
 \qquad\text{and}\qquad
 \sigma_z = 
 \begin{pmatrix}
  1 & 0 \cr 0 & -1
 \end{pmatrix}\, .
\end{aligned}

$$



### Inverse matrix

The inverse of a square matrix $A$ is denoted by $A^{-1}$, and is the
matrix that when multiplied by $A$ gives the identity matrix, i.e.


$$

\begin{aligned}
 A^{-1} A = A A^{-1} = I \, .
\end{aligned}

$$

 It is the matrix generalisation of multiplying a number
$\lambda$ with its reciprocal value $\lambda^{-1} = 1/\lambda$. We write
the inverse with the superscript $-1$ to avoid ambiguity in the order of
the matrices. If we were to write $B/A$, it would be unclear whether we
meant $A^{-1} B$ or $B A^{-1}$. Both are valid expressions, but in
general give different results. If we take the inverse of an inverse, we
get the original matrix again: $(A^{-1})^{-1} = A$.

Sometimes the inverse of a matrix does not exist, just like the inverse
of $\lambda = 0$ does not exist. We will study ways to calculate the
inverse in section [4.6](#sec:inverse){reference-type="ref"
reference="sec:inverse"} and identify ways to tell whether the inverse
exists.

### Unitary matrix

A unitary matrix is defined by the property 

$$

\begin{aligned}
 A^{-1} = A^\dagger \, .
\end{aligned}

$$

 These types of matrices play a central role in
coordinate transformations that preserve the angles between unit
vectors. Real-valued unitary matrices describe rotations and
reflections, while complex unitary matrices are used to describe the
evolution of quantum systems.

## The determinant {#sec:det}

The *determinant* is like the magnitude of the matrix. The determinant
is useful because it helps us to find the inverse of a matrix. A matrix
has to be square to be able to calculate it's determinant e.g. (a 2x2,
3x3 matrix).

To calculate the determinant of a (2x2) matrix, we use the following
formula 

$$

\begin{aligned}
 \det 
  \begin{pmatrix}
  a_{11} & a_{12} \\ a_{21} & a_{22}
 \end{pmatrix}
 \equiv
  \begin{vmatrix}
  a_{11} & a_{12} \\ a_{21} & a_{22}
 \end{vmatrix}
 = a_{11}a_{22} - a_{12}a_{21}\, .
\end{aligned}

$$

 You should memorise this formula, because you will use
it a lot.

An intuitive explanation of the concept of the determinant is given [in
this video by 3Blue1Brown](https://www.youtube.com/watch?v=Ip3X9LOh2dk).

### Matrix cofactors and minor determinants {#sec:cofactors}

Calculating the determinant of a three-dimensional matrix such as;


$$

\begin{aligned}
\label{eq:dfb429wehuisfnj}
 A =
  \begin{pmatrix}
  a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\a_{31} & a_{32} & a_{33}
 \end{pmatrix}\, ,
\end{aligned}

$$

 is more complicated than for a $2\times 2$ matrix. Let
us first introduce two concepts that will help us find the $3\times 3$
determinant: the minor determinant and the cofactor of a matrix element.

Pick an element $a_{jk}$ of an $n\times n$ matrix. It determines a row
$j$ and a column $k$, namely its position in the matrix. If you remove
that row and column, you end up with an $(n-1)\times (n-1)$ matrix. The
determinant of this smaller matrix is called the *minor determinant*
corresponding to the element, and we denote it by $m_{jk}$. To obtain
the cofactor of that element, we multiply the minor determinant with a
factor $(-1)^{j+k}$. This produces a positive sign when $j+k$ is even,
and a minus sign when $j+k$ is odd. This looks like a checker (or chess)
board: 

$$

\begin{aligned}
\nonumber
 (-1)^{j+k}:\quad
 \begin{pmatrix}
  +&-&+ \\ -&+&- \\ +&-&+
 \end{pmatrix}\, .
\end{aligned}

$$

 We can therefore write the cofactor of $a_{jk}$ as


$$

\begin{aligned}
\label{eq:cofactor}
 C_{jk} = (-1)^{j+k} m_{jk}\, .
\end{aligned}

$$

 We will use the matrix cofactors, $C$, to calculate the
determinant of larger matrices.

To calculate the determinant of $A$ in equation
([\[eq:dfb429wehuisfnj\]](#eq:dfb429wehuisfnj){reference-type="ref"
reference="eq:dfb429wehuisfnj"}), we can use the so-called *Laplace
rule*: We start by picking a row or a column (it does not matter which
one we pick). Then we multiply each element in that row or column by its
cofactor. The determinant is the sum of these products. For example,
let's pick the top row of matrix $A$ to calculate the determinant:


$$

\begin{aligned}
 \det A 
 & = a_{11} A_{11} + a_{12} A_{12} + a_{13} A_{13} \cr 
 & = a_{11} 
  \begin{vmatrix}
  a_{22} & a_{23} \\ a_{32} & a_{33}
 \end{vmatrix}
 - a_{12} 
  \begin{vmatrix}
  a_{21} & a_{23} \\ a_{31} & a_{33}
 \end{vmatrix}
 + a_{13}
  \begin{vmatrix}
  a_{21} & a_{22} \\ a_{31} & a_{32}
 \end{vmatrix}\, .
\end{aligned}

$$

 As a numerical example, consider 
 
 $$

\begin{aligned}
 \det A = 
  \begin{vmatrix}
  1 & 2 & 4 \\ 0 & 1 & 3 \\ 2 & 5 & 1
 \end{vmatrix}\, .
\end{aligned}

$$

 Since there is a zero in the matrix, it is useful to
pick a row or column that includes it, since it will reduce the number
of determinants we need to calculate. Let's pick the second row. The
determinant is then 

$$

\begin{aligned}
 \det A = 
 0 \times X - 1 \times 
  \begin{vmatrix}
  1 & 4 \\ 2 & 1
 \end{vmatrix}
 + 3 \times
  \begin{vmatrix}
  1 & 2 \\ 2 & 5
 \end{vmatrix} 
 = -1\times (-7) + 3 \times 1= 10\, .
\end{aligned}

$$

 We do not bother to calculate the determinant $X$
because it gets multiplied by zero anyway. Calculating determinants is
one of those things, along with matrix multiplication, that you should
practice lots so you become comfortable with it.

We can use the determinant to calculate the cross product of two vectors
$\boldsymbol{a}$ and $\boldsymbol{b}$. We construct the following
matrix: 

$$

\begin{aligned}
\label{eq:b9woiersfkjn}
  \begin{pmatrix}
  \hat{\boldsymbol{e}}_x & \hat{\boldsymbol{e}}_y & \hat{\boldsymbol{e}}_z \\ a_x & a_y & a_z \\ b_x & b_y & b_z
 \end{pmatrix}\, .
\end{aligned}

$$

 Here, instead of numbers in the top row, we entered
vectors so this is not a proper matrix. However if we pick the top row
and follow the method of calculating a determinant this will give us the
cross product 

$$

\begin{aligned}
 \mbox{$\mathbf{a}$}\times\mbox{$\mathbf{b}$}=
  \begin{vmatrix}
  \hat{\boldsymbol{e}}_x & \hat{\boldsymbol{e}}_y & \hat{\boldsymbol{e}}_z \\ a_x & a_y & a_z \\ b_x & b_y & b_z
 \end{vmatrix}
 = (a_y b_z - a_z b_y)\, \hat{\boldsymbol{e}}_x - (a_x b_z - a_z b_x)\, \hat{\boldsymbol{e}}_y + (a_x b_y - a_y b_x)\, \hat{\boldsymbol{e}}_z\, .
\end{aligned}

$$

 Why is this related to the determinant? The magnitude of
$\boldsymbol{a}\times\boldsymbol{b}$ is the area of the parallelogram
spanned by $\boldsymbol{a}$ and $\boldsymbol{b}$. If we take the dot
product of $\boldsymbol{a}\times\boldsymbol{b}$ with a vector
$\boldsymbol{c}$ we get a number that is the volume of the
parallelepiped formed by $\boldsymbol{a}$, $\boldsymbol{b}$, and
$\boldsymbol{c}$. We could therefore replace the unit vectors in
equation ([\[eq:b9woiersfkjn\]](#eq:b9woiersfkjn){reference-type="ref"
reference="eq:b9woiersfkjn"}) with $c_x$, $c_y$, and $c_z$, and then the
determinant is the volume change of the transformation that takes the
unit cube to the parallelepiped.

