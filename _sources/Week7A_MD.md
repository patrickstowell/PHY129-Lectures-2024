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
\label{eq:vnbgh3408woij}
 3 x + 2 y - z & = 0\, , \cr
 x - 5 y + 2 z & = 0\, , \\
 y - z & = 0\, .\nonumber
\end{aligned}

$$

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
([\[eq:vnbgh3408woij\]](#eq:vnbgh3408woij){reference-type="ref"
reference="eq:vnbgh3408woij"}) in matrix form
$A \boldsymbol{x} = \boldsymbol{b}$, with 

$$

\begin{aligned}
\label{eq:Ax=0eg}
 A = 
 \begin{pmatrix}
  3 & 2 & -1 \\ 1 & -5 & 2 \\ 0 & 1 & -1
 \end{pmatrix}\, ,
 \qquad
 \boldsymbol{x} =
 \begin{pmatrix}
  x \\ y \\ z
 \end{pmatrix}\, ,
 \qquad\text{and}\qquad
 \boldsymbol{b} =
 \begin{pmatrix}
  0 \\ 0 \\ 0
 \end{pmatrix}\, .
\end{aligned}

$$

 In this case, where $\boldsymbol{b} = 0$, we have a
*homogeneous* set of linearly coupled equations. When
$\boldsymbol{b}\neq0$, we have an *inhomogeneous* set of linearly
coupled equations.

### Homogeneous equations

We now look at the homogeneous case, where 

$$

\begin{aligned}
 A \mbox{$\mathbf{x}$}= 0\, .
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
equation [\[eq:Ax=0eg\]](#eq:Ax=0eg){reference-type="ref"
reference="eq:Ax=0eg"}: 

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
equations [\[eq:vnbgh3408woij\]](#eq:vnbgh3408woij){reference-type="ref"
reference="eq:vnbgh3408woij"}.

If we find that the determinant of a matrix $A$ in $A\boldsymbol{x}=0$
is zero, how do we find the solutions for the variables
$\boldsymbol{x}$? We will do this in the general way, for $n$ variables
$x_j$ and $n$ equations: 

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
 A\mbox{$\mathbf{x}$}= \mbox{$\mathbf{b}$}\qquad\text{with}\qquad \mbox{$\mathbf{b}$}\neq 0\, .
\end{aligned}

$$

 The rule that zero determinant indicates nontrivial
solutions is no longer true. In this case however, we can find the
solutions $\boldsymbol{x}$ by multiplying both sides with the inverse of
$A$, and the solution in vector form is 

$$

\begin{aligned}
 \boldsymbol{x} = A^{-1} \boldsymbol{b}\, .
\end{aligned}

$$

 This requires us to find the inverse of $A$, which may
be a fairly big task.

Another method, uses row reduction (similar to that used for finding the
inverse in section [4.6](#sec:inverse){reference-type="ref"
reference="sec:inverse"}). The rules of matrix row reduction are:

-   multiply any row by a nonzero constant $\lambda \neq 0$;

-   interchange rows;

-   add a multiple of one row to another.

The aim of row reduction is to get zeros in the bottom left or top right
triangle and ones for the first non zero elements. It is equivalent to
taking linear combinations of the equations to produce a simpler but
equivalent set of equations. We demonstrate it with an example. Let


$$

\begin{aligned}
\label{eq:eqinhomosimeqs}
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

$$

 where we have written the set of equations on the left
and the matrix form on the right. Now let us write just the numbers into
what we call an *augmented matrix* which is the square matrix $A$ with
an extra column of $\boldsymbol{b}$ i.e. 

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
equations [\[eq:eqinhomosimeqs\]](#eq:eqinhomosimeqs){reference-type="ref"
reference="eq:eqinhomosimeqs"}.

Linear coupled equations occur a lot in physics, and knowing these
methods will help you quickly solve them. You can even use this method
when you're trying to find the eigenvectors of a matrix.

::: appendices
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



