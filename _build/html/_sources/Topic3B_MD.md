# Matrices

The material in this topic is also covered in chapter 9 of the textbook
Martin and Shaw "Mathematics for Physicists". In Boas "Mathematical
Methods in the Physical Sciences" it is in chapter 3 sections 2,3,6 and
9.

## Introduction

Matrices are used in many areas of physics including classical and
quantum mechanics. They are an indispensable tool for solving problems
in physics.

You already know that a scalar is a single number and a vector is a list
of numbers (a column or a row). A matric is an array of numbers on a
rectangular grid. For example this matrix has three rows and four
columns: 

$$

\begin{aligned}
 A = 
 \begin{pmatrix} 
  3 & 5 & 1 & 2 \cr 
  0 & 1 & 6 & 5 \cr 
  4 & 3 & 7 & 2 
 \end{pmatrix}\, .
\end{aligned}

$$ (eq:matrixA)

 Each individual number in the matrix is called a *matrix
element*. Row vectors can be thought of as matrices with only one row
and column vecotrs can be viewed as matrices with only one column. In
general a matrix is an of numbers arranged in $n$ rows and $m$ columns,
where $n$ and $m$ are whole positive numbers. The numbers that make up
the matrix elements can be real or complex. The numbers in a matrix can
be variables (like distance $x$ or time $t$ in physics equations) or
functions of variables.

*Index notation* provides a convenient way of identifying a particular
element in a matrix. We achieve this by using subscripts---or
*indices*---that indicate the position of the element in the matrix. The
element 

$$

\begin{aligned}
\nonumber
 a_{jk}
\end{aligned}

$$

 is the number in the matrix $A$ on the $j^{\text{th}}$
row and the $k^{\text{th}}$ column. In these notes, I will use upper
case roman letters for matrices and their corresponding lower case for
its elements. The element $a_{jk}$ is different from the matrix element
$a_{kj}$. In the matrix $A$ above
(equation {eq}`eq:matrixA`, element $a_{12}=5$ and $a_{21}=0$, so
$a_{12} \neq a_{21}$. The convention for the order of the indices is
*row-column*. It is crucial you get this the right way around in matrix
calculations. In general, we can write an $n\times m$ (pronounced "$n$
*by* $m$") matrix as 

$$

\begin{aligned}
 A = 
 \begin{pmatrix} 
  a_{11} & a_{12} & \cdots & a_{1m} \cr 
  a_{21} & a_{22} & \cdots & a_{2m} \cr 
  \vdots & \vdots & \ddots & \vdots \cr 
  a_{n1} & a_{n2} & \cdots & a_{nm}  
 \end{pmatrix}\, .
\end{aligned}

$$

 When $n=m$, we have a *square* matrix.

## Manipulating matrices

### Transpose

The *transpose* of a matrix is obtained by swapping the rows and the
columns in the matrix. So the matrix elements become: 

$$

\begin{aligned}
 a_{jk} \xrightarrow{\rm transpose} a_{kj}
\end{aligned}

$$

 We denote the transpose of a matrix by a superscript
$T$. The transpose of the matrix $A$
(equation {eq}`eq:matrixA`) can be written as 

$$

\begin{aligned}
 A^T = 
 \begin{pmatrix} 
  3 & 0 & 4  \cr 
  5 & 1 & 3  \cr 
  1 & 6 & 7  \cr
  2 & 5 & 2  
 \end{pmatrix}\, .
\end{aligned}

$$ (eq:matrixAT)

 Note how the rows and coloumns have swapped in $A^T$
compared to $A$. We can find the transpose by reflecting the elements in
an imaginary mirrow along the diagonal from the top left element
($a_{11}$) to the bottom right element ($a_{nn}$ or $a_{mm}$, depending
on which is smaller, $n$ or $m$).

Note that the transpose of $A^T$ brings us back to $A$ again. The
transpose of a column vector gives the equivalent row vector and the
transpose of a row vector gives the equivalent coloumn vector.

### Complex conjugate

The elements of a matrix can be complex, which means that we can take
the complex conjugate of the matrix as a whole. This is achieved by
taking the complex conjugate of every element individually i.e.


$$

\begin{aligned}
 a_{jk} \xrightarrow{\rm c.c.} a_{jk}^*\, .
\end{aligned}

$$

 Since our example matrix $A$ has only real numbers, we
see that $A^* = A$. A less trivial example would be 

$$

\begin{aligned}
 B = 
 \begin{pmatrix} 
  1 & 2i & 0  \cr 
  6-i & 3 & e^{2\pi i/7} 
 \end{pmatrix}\, ,
 \qquad\text{and}\qquad
 B^* = 
 \begin{pmatrix} 
  1 & -2i & 0  \cr 
  6+i & 3 & e^{-2\pi i/7} 
 \end{pmatrix}\, .
\end{aligned}

$$ (eq:matrixB)

 Each element stays in place, but is complex conjugated:
$b_{jk} \rightarrow b_{jk}^*$. Remember that to get a complex conjugate
you reverse the sign of the imaginary parts.

### Hermitian conjugate

We can combine the transpose and the complex conjugate together to form
the *H*ermitian conjugate (sometimes called the Hermitian *adjoint*). We
denote this by a dagger: 

$$

\begin{aligned}
 B^\dagger = \left(B^*\right)^T = \left(B^T\right)^*\, .
\end{aligned}

$$

 It does not matter whether you take the transpose first,
or if you take the complex conjugate first. In terms of the indices, it
can be written as 

$$

\begin{aligned}
 b_{jk} \xrightarrow{\text{Hermitian conjugate}} b_{kj}^*\, .
\end{aligned}

$$

 The Hermitian conjugate of $B$ is 

$$

\begin{aligned}
 B^\dagger = 
 \begin{pmatrix} 
  1 & 6+i  \cr 
  -2i & 3 \cr 
  0 & e^{-2\pi i/7} 
 \end{pmatrix}\, .
\end{aligned}

$$ (eq:matrixBH)

 conjugate without the transpose, but to see why we have
wait until section {ref}`Eigenvalues`.

## Adding and multiplying matrices

### Addition

We can add two matrices, but *only when they have the same size and
shape $n\times m$*. So, for example, we cannot add $A$
(equation {eq}`eq:matrixA`) and $B$
(equation {eq}`eq:matrixB`), or $A$ and $A^T$
(equation {eq}`eq:matrixAT`), or $B$ and $B^\dagger$
(equation {eq}`eq:matrixBH`). But we can add $B$ and $B^*$
(equation {eq}`eq:matrixB`): 

$$

\begin{aligned}
 B + B^* = 
 \begin{pmatrix} 
  1 & 2i & 0  \cr 
  6-i & 3 & e^{2\pi i/7} 
 \end{pmatrix}
 +
 \begin{pmatrix} 
  1 & -2i & 0  \cr 
  6+i & 3 & e^{-2\pi i/7} 
 \end{pmatrix}
 =  
 \begin{pmatrix} 
  2 & 0 & 0  \cr 
  12 & 6 & 2\cos\left(\frac{2\pi}{7}\right) 
 \end{pmatrix}\, .
\end{aligned}

$$

 So adding two matrices is accomplished simply by adding
the matrix elements at each position. Another example is


$$

\begin{aligned}
 C = 
 \begin{pmatrix} 
  1 & 2 \cr 
  0 & 7  
 \end{pmatrix}\, ,
 \qquad
  D =
 \begin{pmatrix} 
  6 & 1 \cr 
  -3 & 2 
 \end{pmatrix}\, ,
 \qquad
 C + D=  
 \begin{pmatrix} 
  7 & 3 \cr 
  -3 & 9 
 \end{pmatrix}\, .
\end{aligned}

$$

 Addition of matrices is *commutative*, which means that
it does not matter whether you calculate $C+D$ or $D+C$. This is because
the individual elements $c_{jk}$ and $d_{jk}$---which are numbers---can
be added in any order. It is also *associative:* i.e.
$(A+B)+C = A+(B+C)$.

### Scalar multiplication

If we have a matrix $A$, we can also add it to itself to obtain
$A + A = 2A$. This implies that we can multiply a matrix by a number, or
*scalar*, $\lambda$ that multiplies each element of $A$ i.e.


$$

\begin{aligned}
 \lambda A = 
 \begin{pmatrix} 
  \lambda a_{11} & \lambda a_{12} & \cdots & \lambda a_{1m} \cr 
  \lambda a_{21} & \lambda a_{22} & \cdots & \lambda a_{2m} \cr 
  \vdots & \vdots & \ddots & \vdots \cr 
  \lambda a_{n1} & \lambda a_{n2} & \cdots & \lambda a_{nm}  
 \end{pmatrix}\, .
\end{aligned}

$$

 This is called scalar multiplication. Scalar
multiplication is *distributive:* i.e.
$\lambda(A+B) = \lambda A + \lambda B$.

elements. For example, we can say that for any two $n\times m$ matrices
$A$ and $B$ with $D=A+B$, each element of $D$ can be written as and $k$
free variables) fully describes the behaviour of the entire matrix,
because the matrix is merely the array of its elements (i.e., values and
their positions). Expressing the commutative and distributive law in
terms of the elements in equations {eq}`eq:nbt5340wi` and
{eq}`eq:b943whfi` is called *index notation*. We will be using
it here, because it is a very convenient and compact notation, and
consequently it is used extensively in physics. Even though you may not
encounter index notation much this year, we will come back to this in
modules on relativity, electromagnetism, and quantum mechanics in later
years.

### Matrix multiplication

Multiplying two vectors together is difference from addition. Let us
start with an exmple of multiplying a $1\times 2$ matrix and a
$2\times 1$ matrix. These are actually just a row vector and a column
vector. To multiply them we take the scalar (dot) product of the row
from the first matrix and column from the second e.g. for
$\vec{a}=(2\; 4)$ and $\vec{b} = \begin{pmatrix} 1 \\ 3 
\end{pmatrix}$ we get: 

$$

\begin{aligned}
 \vec{a}\cdot\vec{b} = \begin{pmatrix}
  2 & 4 
 \end{pmatrix}
 \begin{pmatrix}
  1  \\  3 
\end{pmatrix}
=2 \times 1+4 \times3 = 14\, .
\end{aligned}

$$ (eq:bg94oweisnkj)

 This is only possible if the length of the row of
$\vec{a}$ is equal to the length of the column of $\vec{b}$. The
outcome of the dot or scalar product is a $1\times1$ "matrix" with one
row and one column, i.e. just a number. This scalar product is also
called the *inner product* and is sometimes denoted
$\langle\vec{a},\vec{b}\rangle$ or $(\vec{a},\vec{b})$. The notation
$\langle\vec{a}|\vec{b}\rangle$ is also used in quantum mechanics. We
can write the scalar or inner product as


$$

\langle\vec{a},\vec{b}\rangle=\sum_{j=1}^{n}a_j^*b_j

$$

 where $n$ is
the number of dimensions, $\vec{a}$ is a row vector and $\vec{b}$ is a
column vector. Note that if we are in complex space (i.e some elements
of the vectors are complex) then we need to take the complex conjugate
of $\vec{a}$. The vector on the left ($\vec{a}$ in this case) is
sometimes called the *dual* i.e. scalar products are between a vector
and a dual vector whereby the dual vector of a column vector is found by
taking the Hermitian conjugate (i.e. the transpose to convert it to a
row vector and the complex conjugate).

The matrix multiplication $AB$ of two matrices $A$ and $B$ works in a
very similar way to the scalar product, but instead of a row vector and
a column vector, we now take a row ($j$) from matrix $A$ and a column
($k$) from matrix $B$. The resulting number (the scalar product) is the
element at the row position $j$ and the column position $k$. We repeat
this for each combination of rows and columns of matrices $A$ and $B$,
respectively. As an example, let us try to multiply the two matrices


$$

\begin{aligned}
 A = 
 \begin{pmatrix}
 8 & 3 & 2 \\ 2 & 5 & 7
\end{pmatrix}  
 \qquad\text{and}\qquad 
 B=
 \begin{pmatrix}
 12 & 0 \\ 1 & 13
\end{pmatrix}\, . 
\end{aligned}

$$

 First, there are two possibilities for how to order the
product: 

$$

\begin{aligned}
 AB =
 \begin{pmatrix}
 8 & 3 & 2 \\ 2 & 5 & 7
\end{pmatrix} 
\begin{pmatrix}
 12 & 0 \\ 1 & 13
\end{pmatrix} 
\quad\text{or}\quad
BA =
\begin{pmatrix}
 12 & 0 \\ 1 & 13
\end{pmatrix} 
 \begin{pmatrix}
 8 & 3 & 2 \\ 2 & 5 & 7
\end{pmatrix} .
\end{aligned}

$$

 The length of the rows of the first matrix must equal
the length of the columns of the second for the multiplication to be
possible, and therefore only the matrix multiplication $BA$ makes sense.
To calculate the product of these matrices you might find the following
way of visualising it helpful: 

$$

\begin{aligned}
 \phantom{
 \begin{pmatrix}
 12 &0 \\ 1 & 13
\end{pmatrix} 
}
 \begin{pmatrix}
 {8} & 3 & 2 \\ {2} & 5 & 7
\end{pmatrix} &  \cr
 \begin{pmatrix}
 12 &0 \\ 1 & 13
\end{pmatrix} 
 \color{white}{
 \begin{pmatrix}
 \phantom{\cdot} & \color{black}{\vdots} & \!\phantom{2} \\ \!\color{black}{\cdot\cdot}\!\!\!\! & \color{black}{\mathbf{68}} & \!\phantom{7}
\end{pmatrix}
}
& =
\begin{pmatrix}
 {96} & 36 & 24 \\ 34 & \mathbf{68} & 93
\end{pmatrix} .
\end{aligned}

$$



We can now multiply the two vectors $\vec{a}$ and $\vec{b}$ in the
other order i.e. 

$$

\begin{aligned}
 \vec{b}\cdot\vec{a} = 
\begin{pmatrix}
  1  \\  3 
\end{pmatrix}
\begin{pmatrix}
  2 & 4 
\end{pmatrix}
=\begin{pmatrix}
2 & 4 \\
6 & 12
\end{pmatrix}
\end{aligned}

$$

 This is the *outer product* of two vectors with the
result being a matrix.

We can also write matrix multiplication using index notation. If $AB=C$,
the element $c_{jk}$ is determined by the dot product of the
$j^{\rm th}$ row of $A$ and the $k^{\rm th}$ column of $B$. We can write
this as 

$$

\begin{aligned}
 c_{jk} = \sum_{l=1}^m a_{jl} b_{lk}\, ,
\end{aligned}

$$

 where $m$ is the number of columns in $A$ and the number
of rows in $B$ (they must be the same for matrix multiplication to be
possible).

We have already seen that the order in which we multiply matrices
matters. An interesting thing happens when we take the Hermitian
conjugate of the product of two matrices. We find that:


$$

\begin{aligned}
 (AB)^\dagger = B^\dagger A^\dagger\, .
\end{aligned}

$$

 The order of $A$ and $B$ changes! We can see this
explicitly by writing this equation in index notation: 

$$

\begin{aligned}
 (AB)^\dagger_{jk} = \left( \sum_{l=1}^n a_{jl} b_{lk} \right)^\dagger = \sum_{l=1}^n a_{jl}^* b_{lk}^* = \sum_{l=1}^n \tilde{a}_{lj} \tilde{b}_{kl} =  \sum_{l=1}^n  \tilde{b}_{kl} \tilde{a}_{lj} = 
(B^\dagger A^\dagger)_{jk}\, ,
\end{aligned}

$$

 where we have used $\tilde{a}_{jk}$ and $\tilde{b}_{jk}$
to represent the matrix elements of $A^\dagger$ and $B^\dagger$,
respectively. **I will not examine you on this proof, I am including it
here for completeness**. Pay close attention to the positions of the
indices. We can swap the order of elements because they are simply
numbers, but a matrix product must always have the same index label on
the column position of the first and the row position of the second.

You will need to practice multiplying matrices lots, until you are
comfortable with it. We use matrix multiplication a lot in different
areas of physics e.g. classical, quantum, particle etc.

physics modules in later years. You should also be able to recognise
matrix multiplication when you encounter it in index notation. Note the
sum over $l$ and the position of the indices. Matrix multiplication is
explained graphically [in this video by
3Blue1Brown](https://www.youtube.com/watch?v=XkY2DOUCWMU&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=5).

## Special matrices 

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
 \DeclareMathOperator{\Tr}{Tr} 
 \DeclareMathOperator{\a}{a}
 \DeclareMathOperator{\b}{b} 
 \DeclareMathOperator{\adj}{adj} 
 \DeclareMathOperator{\x}{x} 

 \Tr A = \sum_{j=1}^n a_{jj}\, .
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

 it may look intimidating now.

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

 In section {ref}`Eigenvalues` we will learn about the eigenvalues of a matrix,
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
inverse in section {ref}`Matrix Inversion` and identify ways to tell whether the inverse exists.

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

<!-- the transformation, the area is no longer a square, because the
horizontal length has become $3$ and the vertical length has become $2$.
The new area is therefore $6$ (see
figure [\[fig:det\]](#fig:det){reference-type="ref"
reference="fig:det"}). three dimensions the determinant is the scaling
factor for volume, and so on. When a determinant is zero, the matrix
transformation changes the area to a line or point, and a volume to an
area, line or point. In other words, the volumes get mapped to a lower
dimension. Negative determinants occur when the transformation changes
the orientation of the basis vectors (e.g., swap $\hat{\rm e}_x$ and
$\hat{\rm e}_y$) which for $2D$ can be visualised as flipping the $2D$
plane to the other side like turning over a sheet of paper. -->

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

### Matrix cofactors and minor determinants 

Calculating the determinant of a three-dimensional matrix such as;


$$

\begin{aligned}
 A =
  \begin{pmatrix}
  a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\a_{31} & a_{32} & a_{33}
 \end{pmatrix}\, ,
\end{aligned}

$$ (eq:dfb429wehuisfnj)

 is more complicated than for a $2\times 2$ matrix. Let
us first introduce two concepts that will help us find the $3\times 3$
determinant: the minor determinant and the cofactor of a matrix element.

Pick an element $a_{jk}$ of an $n\times n$ matrix. It determines a row
$j$ and a column $k$, namely its position in the matrix. If you remove
that row and column, you end up with an $(n-1)\times 
(n-1)$ matrix. The determinant of this smaller matrix is called the
*minor determinant* corresponding to the element, and we denote it by
$m_{jk}$. To obtain the cofactor of that element, we multiply the minor
determinant with a factor $(-1)^{j+k}$. This produces a positive sign
when $j+k$ is even, and a minus sign when $j+k$ is odd. This looks like
a checker (or chess) board: 

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
 C_{jk} = (-1)^{j+k} m_{jk}\, .
\end{aligned}

$$ (eq:cofactor)

 We will use the matrix cofactors, $C$, to calculate the
determinant of larger matrices.

To calculate the determinant of $A$ in equation
{eq}`eq:dfb429wehuisfnj`, we can use the so-called *Laplace
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
$\vec{a}$ and $\vec{b}$. We construct the following matrix:


$$

\begin{aligned}
  \begin{pmatrix}
  \hat{\vec{e}}_x & \hat{\vec{e}}_y & \hat{\vec{e}}_z \\ a_x & a_y & a_z \\ b_x & b_y & b_z
 \end{pmatrix}\, .
\end{aligned}

$$ (eq:b9woiersfkjn)

 Here, instead of numbers in the top row, we entered
vectors so this is not a proper matrix. However if we pick the top row
and follow the method of calculating a determinant this will give us the
cross product 

$$

\begin{aligned}
 \a\times\b =
  \begin{vmatrix}
  \hat{\vec{e}}_x & \hat{\vec{e}}_y & \hat{\vec{e}}_z \\ a_x & a_y & a_z \\ b_x & b_y & b_z
 \end{vmatrix}
 = (a_y b_z - a_z b_y)\, \hat{\vec{e}}_x - (a_x b_z - a_z b_x)\, \hat{\vec{e}}_y + (a_x b_y - a_y b_x)\, \hat{\vec{e}}_z\, .
\end{aligned}

$$

 Why is this related to the determinant? The magnitude of
$\vec{a}\times\vec{b}$ is the area of the parallelogram spanned by
$\vec{a}$ and $\vec{b}$. If we take the dot product of
$\vec{a}\times\vec{b}$ with a vector $\vec{c}$ we get a number that
is the volume of the parallelepiped formed by $\vec{a}$, $\vec{b}$,
and $\vec{c}$. We could therefore replace the unit vectors in equation {eq}`eq:b9woiersfkjn` with $c_x$, $c_y$, and $c_z$, and then the
determinant is the volume change of the transformation that takes the
unit cube to the parallelepiped. also [this video by
3Blue1Brown](https://www.youtube.com/watch?v=eu6i7WJeinw&index=11&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab)
and [its
sequel](https://www.youtube.com/watch?v=BaM7OCEm3G0&index=12&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab).

### Properties of determinants

Some important properties of the determinant are the following:

-   $\det (A^T) = \det A$

-   $\det AB = \det A \times \det B$. This implies that
    $\det AB = \det BA$, even when $A$ and $B$ do not commute

-   $\det (A^{-1}) = (\det A)^{-1}$

-   if you interchange two rows or two columns, the determinant changes
    sign

-   if two rows are identical, the determinant is zero

-   if you multiply a row or a column by a factor $\lambda$, then the
    determinant is multiplied by $\lambda$

-   from the previous two properties it follows that if two rows or
    columns are *proportional* to each other, the determinant is zero

-   adding two rows or columns, and replacing one of them with the
    resulting row or column with not change the determinant

-   the determinant of a diagonal matrix is the product of the elements
    on the diagonal.

The first three properties are very useful in algebraic manipulation,
while the remaining properties are very useful in simplifying the
calculation of determinants of large matrices.

interesting types of matrices: rotation: just calculate the determinant.
If it is $+1$ the reflections created an effective rotation, if it is
$-1$ we have a true reflection. some phase $\phi$ in the interval
$[0,2\pi)$.

## Inverse of a matrix {#sec:inverse}

In this section we learn how to calculate the inverse of a matrix.
Remember that the inverse of a matrix $A$ (if it has one) is defined as


$$

\begin{aligned}
 A A^{-1} = A^{-1} A = I
\end{aligned}

$$

 and therefore also $\det A^{-1} = (\det A)^{-1}$. From
this we can see that only square matrices have an inverse and that a
matrix which has a zero determinant does not have an inverse. An
*invertible* matrix has an inverse. If a matrix does not have an inverse
we call it *singluar*.

One way to calculate the inverse of a matrix, $A^{-1}$, is to first
calculate the matrix of cofactors, $C$, (see
section {ref}`Matrix cofactors and minor determinants`). We then caclulate the determinant of $A$
and the transpose of the matrix of cofactors, $C^T$. $C^{T}$ is
sometimes called the adjoint of the matrix i.e. $C^T=\adj A$. This is
not the same as the Hermitian adjoint operator $\dagger$ from section
{ref}`Special Matrices`.

Finding the matrix of cofactors $C$ can be a lot of work. The inverse is
then given by; 

$$

\begin{aligned}
A^{-1} = \frac{C^T}{\det A}
\end{aligned}

$$

 where $C_{ij}$ is the cofactor of $A_{ij}$ as given in
equation {eq}`eq:cofactor`. For a proof of why this method works see
Appendix {ref}`Inverse of a matrix: proof of the adjoint method`.

## Eigenvalue problems 

A matrix, $A$, changes the direction of the basis vectors
($\hat{\vec{x}}$ and $\hat{\vec{y}}$ in 2D), but there are also two
(in 2D) vectors that do not change direction under the action of $A$;
they only scale (change length) i.e. 

$$

\begin{aligned}
 A\vec{u} = \lambda_u\vec{u} \qquad\text{and}\qquad A\vec{v} =  \lambda_v \vec{v}
\end{aligned}

$$

 where $\lambda_u$ and $\lambda_v$ are scalars which we
call the *eigenvalues* of $A$ and $\vec{u}$ and $\vec{v}$ are vectors
we call the *eignevectors*. The eigenvectors are the directions along
which $A$ produces a simple scaling. if we write the matrix $A$ in the
basis that points along $\vec{u}$ and $\vec{v}$, the matrix becomes
diagonal Next we will see how we can find the eigenvectors and
eigenvalues of any matrix $A$. You will find over the coming years that
eigenvalue problems crop up in many areas of physics (e.g. classical and
quantum).

### Eigenvalues

The so-called *eigenvalue equation* for a matrix $A$ is given by


$$

\begin{aligned}
 A \vec{u} = \lambda \vec{u}\, .
\end{aligned}

$$

 In this equation, $A$ acting on an eigenvector $\vec{u}$
multiplies it by a factor $\lambda$. It does not change the direction of
$\vec{u}$. If $A$ is an $n\times n$ matrix, there will be $n$ eigenvalues,
each with a corresponding eigenvector. Note that for $n\times m$
matrices the eigenvalue problem becomes the *singular value
decomposition* which is beyond the scope of this course but is covered
in more advanced textbooks. When two eigenvalues have the same value,
these eigenvalues are said to be *degenerate*, and there is an extra
freedom in the choice of the corresponding eigenvectors.

We find the eigenvalues as follows. First we rearrange the eigenvalue
equation into the form 

$$

\begin{aligned}
 \left( A - \lambda I\right) \vec{u} = 0\, ,
\end{aligned}

$$

 where we explicitly included the identity matrix, $I$,
which needs to be there for the subtraction of $\lambda$ from $A$. If
$\vec{u}$ is not zero, the matrix $A-\lambda I$ must project $\vec{u}$
to zero, and therefore its determinant must be zero i.e.


$$

\begin{aligned}
 \det \left( A - \lambda I\right) = 0\, .
\end{aligned}

$$

 This is a polynomial in $\lambda$ whose solutions are
the eigenvalues of $A$. If $A$ is a $2\times 2$ matrix this is a
quadratic equation in $\lambda$.

As a simple example, let's calculate the eigenvalues of


$$

\begin{aligned}
 A = 
 \begin{pmatrix}
  1 & 3 \\ 2 & 7
 \end{pmatrix}\, .
\end{aligned}

$$ (eq:bgrwoeijsd)

 We need to calculate the determinant 

$$

\begin{aligned}
 \det (A - \lambda I) = 
 \begin{vmatrix}
  1-\lambda & 3 \\ 2 & 7 -\lambda
 \end{vmatrix}
 = (1-\lambda)(7-\lambda) - 6 = \lambda^2 -8\lambda + 1 = 0\, .
\end{aligned}

$$

 We can solve this for $\lambda$ using the quadratic
formula, and find 

$$

\begin{aligned}
 \lambda_{\pm} = \frac{8 \pm \sqrt{64-4}}{2} = 4 \pm \sqrt{15}\, .
\end{aligned}

$$ (eq:egevalues)

 giving the two eigenvalues of $A$ as
$\lambda_{+}= 4 + \sqrt{15}$ and $\lambda_{-}= 4 - \sqrt{15}$.

### Eigenvectors

To find the eigenvectors, we first calculate the eigenvalues. Let's call
them $\lambda_j$. We now wnat to find the $n$ eigenvectors $\vec{u}_j$.
The eigenvalue equation then becomes 

$$

\begin{aligned}
 A \vec{u}_j = \lambda_j \vec{u}_j\, .
\end{aligned}

$$ (eq:vn49woesrjd)

 Since $A$ is known and the $\lambda_j$ are known, we can
substitute these into the eigenvalue equation and solve for $\vec{u}_j$. The
eigenvectors are not completely determined by this equation, however. We
obtain the eigenvectors only up to a constant scaling factor i.e. we get
the directions but the length can be anything. If we wish we can divide
both sides of equation
{eq}`eq:vn49woesrjd` by the length of $\vec{u}_j$, in which
case we obtain the *normalised eigenvector* (i.e., it has unit length).

Let's do this for the example above in
equation {eq}`eq:bgrwoeijsd`. Starting with $\lambda_+$ given in
equation {eq}`eq:egevalues`, the eigenvalue equation becomes


$$

\begin{aligned}
 \begin{pmatrix}
  1 & 3 \\ 2 & 7
 \end{pmatrix}
 \begin{pmatrix}
  u_x \\ u_y
 \end{pmatrix}
 =
 (4 + \sqrt{15})
 \begin{pmatrix}
  u_x \\ u_y
 \end{pmatrix}\, .
\end{aligned}

$$

 Performing matrix multiplication and scalar
multiplication, and requiring that each element of the resulting 2D
vector on both sides are equal, we obtain the following two equations:


$$

\begin{aligned}
 (-3 - \sqrt{15}) u_x + 3 u_y & =  0 \cr
 2 u_x + (3 - \sqrt{15}) u_y & = 0 \, .
\end{aligned}

$$

 We do not actually need to solve these equations for
$u_x$ and $u_y$, because the two equations are not linearly independent.
We only need to look at the top equation, and set $u_x = 3$ and $u_y = 
3+\sqrt{15}$ i.e. the eigenvector is 

$$

\begin{aligned}
 \vec{u}_+ = 
  \begin{pmatrix}
  3 \\ 3+\sqrt{15}
 \end{pmatrix}\, .
\end{aligned}

$$

 We can normalise this vector if we want, and depending
on the application this may be necessary. You can check that
substituting $\vec{u}_+$ into the bottom equation also yields zero.

The second eigenvector is obtained in the same way, starting with
$\lambda_-$ 

$$

\begin{aligned}
 \begin{pmatrix}
  1 & 3 \\ 2 & 7
 \end{pmatrix}
 \begin{pmatrix}
  u_x \\ u_y
 \end{pmatrix}
 =
 (4 - \sqrt{15})
 \begin{pmatrix}
  u_x \\ u_y
 \end{pmatrix}\, ,
\end{aligned}

$$

 leading to 

$$

\begin{aligned}
 (-3 + \sqrt{15}) u_x + 3 u_y & =  0 \cr
 2 u_x + (3 + \sqrt{15}) u_y & = 0 \, ,
\end{aligned}

$$

 and eigenvector 

$$

\begin{aligned}
 \vec{u}_- = 
  \begin{pmatrix}
  3 \\ 3-\sqrt{15}
 \end{pmatrix}\, .
\end{aligned}

$$

 and eigenvectors is given [in this video by
3Blue1Brown](https://www.youtube.com/watch?v=PFDu9oVAE-g&index=14&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab).

## Linear coupled equations

Linear equations are ones that have no terms that are quadratic or
higher in the variables i.e. the variables appear in linear terms only.
Coupled equations are equations that have multiple variables. If we have
$n$ unknown variables and $n$ coupled linear equations we can solve them
to find the variables. Such equations are sometimes called simulataneous
equations or a set of equations or a system of equations. In physics we
often have more than one variable such that we need to solve such
coupled equations. Sometimes we can make approximations to the real
physical system to get linear equations. Then we can solve the coupled
linear equations using the method we outline here.

### Trivial solutions {#trivial-solutions .unnumbered}

An example of three linear coupled equations in the variables $x$, $y$
and $z$ is 

$$

\begin{aligned}
 3 x + 2 y - z & = 0\, , \cr
 x - 5 y + 2 z & = 0\, , \\
 y - z & = 0\, .\nonumber
\end{aligned}

$$ (eq:vnbgh3408woij)

 From the bottom equation we can see that $z=y$.
Substituting this into the other equations gives $3x = -y$ and $x=3y$.
These equations can only both be satisfied if $x = y = 0$ and $z = 0$.
We call a solution when all the variables are zero a *trivial* solution.
Usually we are more interested in *nontrivial* solutions.

How can we tell if we have nontrivial solutions to a set of coupled
equations? In this section we will give a simple method for answering
this question, and we will work out the solutions if we establish there
are indeed nontrivial solutions.

Note that we can write equation
{eq}`eq:vnbgh3408woij` in matrix form $A \vec{x} = \vec{b}$,
with 

$$

\begin{aligned}
 A = 
 \begin{pmatrix}
  3 & 2 & -1 \\ 1 & -5 & 2 \\ 0 & 1 & -1
 \end{pmatrix}\, ,
 \qquad
 \vec{x} =
 \begin{pmatrix}
  x \\ y \\ z
 \end{pmatrix}\, ,
 \qquad\text{and}\qquad
 \vec{b} =
 \begin{pmatrix}
  0 \\ 0 \\ 0
 \end{pmatrix}\, .
\end{aligned}

$$ (eq:Ax=0eg)

 In this case, where $\vec{b} = 0$, we have a
*homogeneous* set of linearly coupled equations. When $\vec{b}\neq0$,
we have an *inhomogeneous* set of linearly coupled equations.

### Homogeneous equations

We now look at the homogeneous case, where 

$$

\begin{aligned}
 A \x = 0\, .
\end{aligned}

$$

 To check whether there are non-trivial solutions to the
homogeneous equations, we need to check whether the equations are
linearly independent. If they are, all variables must be zero (as we
found above), due to definition of what it means to be linearly
independent. However, we know that when the rows of $A$ are linearly
dependent, the determinant of $A$ should be zero. Therefore if the
determinant is nonzero there are no nontrivial solutions. Let's
calculate the determinant of the matrix $A$ from
equation {eq}`eq:Ax=0eg`: 

$$

\begin{aligned}
  \begin{vmatrix}
  3 & 2 & -1 \\ 1 & -5 & 2 \\ 0 & 1 & -1
 \end{vmatrix}
 = -
   \begin{vmatrix}
  3 & -1 \\ 1 & 2 
 \end{vmatrix}
 +
   \begin{vmatrix}
  3 & 2 \\ 1 & -5 
 \end{vmatrix}
 =
 -7-17=-24\, .
\end{aligned}

$$

 So the determinant is not zero, and therefore $x=y=z=0$
is the only solution to
equations {eq}`eq:vnbgh3408woij`.

If we find that the determinant of a matrix $A$ in $A\vec{x}=0$ is
zero, how do we find the solutions for the variables $\vec{x}$? We will
do this in the general way, for $n$ variables $x_j$ and $n$ equations:


$$

\begin{aligned}
 a_{11} x_1 + a_{12} x_2 + \ldots a_{1n} x_n & = 0\, , \cr
 a_{21} x_1 + a_{22} x_2 + \ldots a_{2n} x_n & = 0\, , \cr
  & \vdots \cr
 a_{n1} x_1 + a_{n2} x_2 + \ldots a_{nn} x_n & = 0\, .
\end{aligned}

$$

 Notice that the top row becomes the determinant if we
replace the variables $x_k$ with the matrix cofactor $C_{1k}$. In fact,
*any* row $j$ turns into the determinant of $A$ if we replace the
variables $x_{k}$ with the cofactors $C_{jk}$. This means that the
solutions have the ratio 

$$

\begin{aligned}
 x_1 : x_2 : \cdots : x_n = C_{11} : C_{12} : \cdots : C_{1n}\, .
\end{aligned}

$$

 Therefore, finding the cofactors of one row of the
matrix $A$ gives the solutions to the linear homogeneous coupled
equations.

### Inhomogeneous equations

Next, we consider the inhomogeneous linearly coupled equations i.e.


$$

\begin{aligned}
 A\x = \b \qquad\text{with}\qquad \b\neq 0\, .
\end{aligned}

$$

 The rule that zero determinant indicates nontrivial
solutions is no longer true. In this case however, we can find the
solutions $\vec{x}$ by multiplying both sides with the inverse of $A$,
and the solution in vector form is 

$$

\begin{aligned}
 \vec{x} = A^{-1} \vec{b}\, .
\end{aligned}

$$

 This requires us to find the inverse of $A$, which may
be a fairly big task.

Another method, uses row reduction (similar to that used for finding the
inverse in section {ref}`Inverse of a matrix`. The rules of matrix row reduction are:

-   multiply any row by a nonzero constant $\lambda \neq 0$;

-   interchange rows;

-   add a multiple of one row to another.

The aim of row reduction is to get zeros in the bottom left or top right
triangle and ones for the first non zero elements. It is equivalent to
taking linear combinations of the equations to produce a simpler but
equivalent set of equations. We demonstrate it with an example. Let


$$

\begin{aligned}
   \begin{array}{ccc}
  2x + 3y &=& 2  \\
  4x+y&=&7
   \end{array}
    \quad\quad\quad
 \begin{pmatrix}
  2 & 3 \\ 4 & 1
 \end{pmatrix}
 \begin{pmatrix}
  x \\ y
 \end{pmatrix}
 =
 \begin{pmatrix}
  2 \\ 7
 \end{pmatrix}\, .
\end{aligned}

$$ (eq:eqinhomosimeqs)

 where we have written the set of equations on the left
and the matrix form on the right. Now let us write just the numbers into
what we call an *augmented matrix* which is the square matrix $A$ with
an extra column of $\vec{b}$ i.e. 

$$

\begin{aligned}
  \begin{array}{ccc}
  2x + 3y &=& 2  \\
  4x+y&=&7
   \end{array}
  \quad\quad\quad
  \left (
 \begin{array}{cc|c}
   2 & 3 & 2 \\
   4 & 1 & 7
 \end{array}
 \right )
\end{aligned}

$$

 where the vertical line is just to remind us that the
final colomn is from the right hand side of the original equation. Now
we apply row reduction (Gaussian elimination) to this augmented matrix.
First, we substract the top row twice from the bottom row:


$$

\begin{aligned}
     \begin{array}{ccc}
  2x + 3y &=& 2  \\
  -5y&=&3
   \end{array}
    \quad\quad\quad
   \left (
 \begin{array}{cc|c}
   2 & 3 & 2 \\
   0 & -5 & 3
 \end{array}
 \right ).
\end{aligned}

$$

 From the second row we can already find that $y = -3/5$
by dividing the bottom row by $-5$ to get; 

$$

\begin{aligned}
     \begin{array}{ccc}
  2x + 3y &=& 2  \\
  y&=&-3/5
   \end{array}
    \quad\quad\quad
   \left (
 \begin{array}{cc|c}
   2 & 3 & 2 \\
   0 & 1 & -3/5
 \end{array}
 \right ).
\end{aligned}

$$

 Substituting $y = -3/5$ back into either starting
equations gives $x = 19/10$. Or we can continue the row reduction method
by subtracting three times the bottom row from the top row;


$$

\begin{aligned}
     \begin{array}{ccc}
  2x  &=& 2+9/5  \\
  y&=&-3/5
   \end{array}
    \quad\quad\quad
   \left (
 \begin{array}{cc|c}
   2 & 0 & 2+9/5 \\
   0 & 1 & -3/5
 \end{array}
 \right ).
\end{aligned}

$$

 Finally dividing the top row by two gives;


$$

\begin{aligned}
     \begin{array}{ccc}
  x  &=& 19/10  \\
  y&=&-3/5
   \end{array}
    \quad\quad\quad
   \left (
 \begin{array}{cc|c}
   1 & 0 & 19/10 \\
   0 & 1 & -3/5
 \end{array}
 \right )
\end{aligned}

$$

 from which we can read off $x = 19/10$ and $y = -3/5$ as
the solutions to the inhomogeneous
equations {eq}`eq:eqinhomosimeqs`.

Linear coupled equations occur a lot in physics, and knowing these
methods will help you quickly solve them. You can even use this method
when you're trying to find the eigenvectors of a matrix.
