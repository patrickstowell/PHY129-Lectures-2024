# EigenValues and EigenVectors
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
section [4.5.1](#sec:cofactors){reference-type="ref"
reference="sec:cofactors"}). We then caclulate the determinant of $A$
and the transpose of the matrix of cofactors, $C^T$. $C^{T}$ is
sometimes called the adjoint of the matrix i.e.
$C^T=\mathop{\mathrm{adj}}A$. This is not the same as the Hermitian
adjoint operator $\dagger$ from section
[4.4](#sec:special){reference-type="ref" reference="sec:special"}.
Finding the matrix of cofactors $C$ can be a lot of work. The inverse is
then given by; 

$$

\begin{aligned}
A^{-1} = \frac{C^T}{\det A}
\end{aligned}

$$

 where $C_{ij}$ is the cofactor of $A_{ij}$ as given in
equation [\[eq:cofactor\]](#eq:cofactor){reference-type="ref"
reference="eq:cofactor"}. For a proof of why this method works see
Appendix [8](#sec:adjointmethod){reference-type="ref"
reference="sec:adjointmethod"}.

## Eigenvalue problems {#sec:eigen}

A matrix, $A$, changes the direction of the basis vectors
($\hat{\boldsymbol{x}}$ and $\hat{\boldsymbol{y}}$ in 2D), but there are
also two (in 2D) vectors that do not change direction under the action
of $A$; they only scale (change length) i.e. 

$$

\begin{aligned}
 A\boldsymbol{u} = \lambda_u\boldsymbol{u} \qquad\text{and}\qquad A\boldsymbol{v} =  \lambda_v \boldsymbol{v}
\end{aligned}

$$

 where $\lambda_u$ and $\lambda_v$ are scalars which we
call the *eigenvalues* of $A$ and $\boldsymbol{u}$ and $\boldsymbol{v}$
are vectors we call the *eignevectors*. The eigenvectors are the
directions along which $A$ produces a simple scaling. Next we will see
how we can find the eigenvectors and eigenvalues of any matrix $A$. You
will find over the coming years that eigenvalue problems crop up in many
areas of physics (e.g. classical and quantum).

### Eigenvalues

The so-called *eigenvalue equation* for a matrix $A$ is given by


$$

\begin{aligned}
 A \mbox{$\mathbf{u}$}= \lambda \mbox{$\mathbf{u}$}\, .
\end{aligned}

$$

 In this equation, $A$ acting on an eigenvector
$\mbox{$\mathbf{u}$}$ multiplies it by a factor $\lambda$. It does not
change the direction of $\mbox{$\mathbf{u}$}$. If $A$ is an $n\times n$
matrix, there will be $n$ eigenvalues, each with a corresponding
eigenvector. Note that for $n\times m$ matrices the eigenvalue problem
becomes the *singular value decomposition* which is beyond the scope of
this course but is covered in more advanced textbooks. When two
eigenvalues have the same value, these eigenvalues are said to be
*degenerate*, and there is an extra freedom in the choice of the
corresponding eigenvectors.

We find the eigenvalues as follows. First we rearrange the eigenvalue
equation into the form 

$$

\begin{aligned}
 \left( A - \lambda I\right) \boldsymbol{u} = 0\, ,
\end{aligned}

$$

 where we explicitly included the identity matrix, $I$,
which needs to be there for the subtraction of $\lambda$ from $A$. If
$\boldsymbol{u}$ is not zero, the matrix $A-\lambda I$ must project
$\boldsymbol{u}$ to zero, and therefore its determinant must be zero
i.e. 

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
\label{eq:bgrwoeijsd}
 A = 
 \begin{pmatrix}
  1 & 3 \\ 2 & 7
 \end{pmatrix}\, .
\end{aligned}

$$

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
\label{eq:egevalues}
 \lambda_{\pm} = \frac{8 \pm \sqrt{64-4}}{2} = 4 \pm \sqrt{15}\, .
\end{aligned}

$$

 giving the two eigenvalues of $A$ as
$\lambda_{+}= 4 + \sqrt{15}$ and $\lambda_{-}= 4 - \sqrt{15}$.

### Eigenvectors

To find the eigenvectors, we first calculate the eigenvalues. Let's call
them $\lambda_j$. We now wnat to find the $n$ eigenvectors
$\boldsymbol{u}_j$. The eigenvalue equation then becomes


$$

\begin{aligned}
\label{eq:vn49woesrjd}
 A \boldsymbol{u}_j = \lambda_j \boldsymbol{u}_j\, .
\end{aligned}

$$

 Since $A$ is known and the $\lambda_j$ are known, we can
substitute these into the eigenvalue equation and solve for
$\mbox{$\mathbf{u}$}_j$. The eigenvectors are not completely determined
by this equation, however. We obtain the eigenvectors only up to a
constant scaling factor i.e. we get the directions but the length can be
anything. If we wish we can divide both sides of equation
([\[eq:vn49woesrjd\]](#eq:vn49woesrjd){reference-type="ref"
reference="eq:vn49woesrjd"}) by the length of $\boldsymbol{u}_j$, in
which case we obtain the *normalised eigenvector* (i.e., it has unit
length).

Let's do this for the example above in
equation [\[eq:bgrwoeijsd\]](#eq:bgrwoeijsd){reference-type="ref"
reference="eq:bgrwoeijsd"}. Starting with $\lambda_+$ given in
equation [\[eq:egevalues\]](#eq:egevalues){reference-type="ref"
reference="eq:egevalues"}, the eigenvalue equation becomes


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
We only need to look at the top equation, and set $u_x = 3$ and
$u_y = 3+\sqrt{15}$ i.e. the eigenvector is 

$$

\begin{aligned}
 \boldsymbol{u}_+ = 
  \begin{pmatrix}
  3 \\ 3+\sqrt{15}
 \end{pmatrix}\, .
\end{aligned}

$$

 We can normalise this vector if we want, and depending
on the application this may be necessary. You can check that
substituting $\boldsymbol{u}_+$ into the bottom equation also yields
zero.

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
 \boldsymbol{u}_- = 
  \begin{pmatrix}
  3 \\ 3-\sqrt{15}
 \end{pmatrix}\, .
\end{aligned}

$$


