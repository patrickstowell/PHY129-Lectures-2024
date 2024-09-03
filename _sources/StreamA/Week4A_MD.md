# Matrix Maths



## Adding and multiplying matrices

### Addition

We can add two matrices, but *only when they have the same size and
shape $n\times m$*. So, for example, we cannot add $A$
(equation [\[eq:matrixA\]](#eq:matrixA){reference-type="ref"
reference="eq:matrixA"}) and $B$
(equation [\[eq:matrixB\]](#eq:matrixB){reference-type="ref"
reference="eq:matrixB"}), or $A$ and $A^T$
(equation [\[eq:matrixAT\]](#eq:matrixAT){reference-type="ref"
reference="eq:matrixAT"}), or $B$ and $B^\dagger$
(equation [\[eq:matrixBH\]](#eq:matrixBH){reference-type="ref"
reference="eq:matrixBH"}). But we can add $B$ and $B^*$
(equation [\[eq:matrixB\]](#eq:matrixB){reference-type="ref"
reference="eq:matrixB"}): 

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

### Matrix multiplication

Multiplying two vectors together is difference from addition. Let us
start with an exmple of multiplying a $1\times 2$ matrix and a
$2\times 1$ matrix. These are actually just a row vector and a column
vector. To multiply them we take the scalar (dot) product of the row
from the first matrix and column from the second e.g. for
$\boldsymbol{a}=(2\; 4)$ and
$\boldsymbol{b} = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$ we get:


$$

\begin{aligned}
\label{eq:bg94oweisnkj}
 \boldsymbol{a}\cdot\boldsymbol{b} = \begin{pmatrix}
  2 & 4 
 \end{pmatrix}
 \begin{pmatrix}
  1  \\  3 
\end{pmatrix}
=2 \times 1+4 \times3 = 14\, .
\end{aligned}

$$

 This is only possible if the length of the row of
$\boldsymbol{a}$ is equal to the length of the column of
$\boldsymbol{b}$. The outcome of the dot or scalar product is a
$1\times1$ "matrix" with one row and one column, i.e. just a number.
This scalar product is also called the *inner product* and is sometimes
denoted $\langle\boldsymbol{a},\boldsymbol{b}\rangle$ or
$(\boldsymbol{a},\boldsymbol{b})$. The notation
$\langle\boldsymbol{a}|\boldsymbol{b}\rangle$ is also used in quantum
mechanics. We can write the scalar or inner product as


$$

\langle\boldsymbol{a},\boldsymbol{b}\rangle=\sum_{j=1}^{n}a_j^*b_j

$$


where $n$ is the number of dimensions, $\boldsymbol{a}$ is a row vector
and $\boldsymbol{b}$ is a column vector. Note that if we are in complex
space (i.e some elements of the vectors are complex) then we need to
take the complex conjugate of $\boldsymbol{a}$. The vector on the left
($\boldsymbol{a}$ in this case) is sometimes called the *dual* i.e.
scalar products are between a vector and a dual vector whereby the dual
vector of a column vector is found by taking the Hermitian conjugate
(i.e. the transpose to convert it to a row vector and the complex
conjugate).

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



We can now multiply the two vectors $\boldsymbol{a}$ and
$\boldsymbol{b}$ in the other order i.e. 

$$

\begin{aligned}
 \boldsymbol{b}\cdot\boldsymbol{a} = 
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

