
# Matrix Diagonalisation

The matrix $A$ in equation
([\[eq:bgrwoeijsd\]](#eq:bgrwoeijsd){reference-type="ref"
reference="eq:bgrwoeijsd"}) can be written in a different basis such
that it has only nonzero diagonal elements. This is called *matrix
diagonalisation*. It is a type of *similarity transform*. See
appendix [9](#sec:similarity){reference-type="ref"
reference="sec:similarity"} for more on similarity transforms. Matrix
diagonalisation is a similarity transform that takes the unit vectors
$\hat{\boldsymbol{x}}$ and $\hat{\boldsymbol{y}}$ (i.e. the basis
vectors in which $A$ was written) and turns them into the two
eigenvectors. The matrix that does this similarity transform can be
constructed by taking the column vector eigenvectors to give
$S = (\boldsymbol{u}_+ ~ \boldsymbol{u}_-)$, i.e. 

$$

\begin{aligned}
 S = 
   \begin{pmatrix}
  3 & 3 \\
  3+\sqrt{15} & 3-\sqrt{15}
 \end{pmatrix}\, .
\end{aligned}

$$

 This is takes the basis states to the eigenvectors. The
eigenvalue equation can now be written in the form 

$$

AS=SA^{\prime}

$$


where $A^{\prime}$ is the diagonal matrix given in
equation [\[eq:diagonal\]](#eq:diagonal){reference-type="ref"
reference="eq:diagonal"}. Therefore to calculate the diagonal matrix we
have 

$$

A^{\prime}=S^{-1}AS

$$

 so we need to calculate the inverse of $S$
(see section [4.6](#sec:inverse){reference-type="ref"
reference="sec:inverse"}). In our example this is 

$$

\begin{aligned}
 S^{-1} = 
   \begin{pmatrix}
  \frac{-3+\sqrt{15}}{6\sqrt{15}} & \frac{1}{2\sqrt{15}} \\
  \frac{3+\sqrt{15}}{6\sqrt{15}}& -\frac{1}{2\sqrt{15}}
 \end{pmatrix}\, .
\end{aligned}

$$

 We can then verify that 
 
 $$

\begin{aligned}
 S^{-1}AS = 
 \begin{pmatrix}
  \frac{-3+\sqrt{15}}{6\sqrt{15}} & \frac{1}{2\sqrt{15}} \\
  \frac{3+\sqrt{15}}{6\sqrt{15}}& -\frac{1}{2\sqrt{15}}
 \end{pmatrix}
 \begin{pmatrix}
  1 & 3 \\ 2 & 7
 \end{pmatrix}
 \begin{pmatrix}
  3 & 3 \\
  3+\sqrt{15} & 3-\sqrt{15}
 \end{pmatrix}
 =
 \begin{pmatrix}
  4+\sqrt{15} & 0 \\ 0 & 4-\sqrt{15} 
 \end{pmatrix}
\end{aligned}

$$

 as expected.

In summary the general rule for matrix diagonalisation is to create the
similarity transform matrix $S$ by collecting the (column) eigenvectors
of $A$, and calculating $S^{-1} A S$.

