
# Similarity transformations {#sec:similarity}

In section [\[sec:linear\]](#sec:linear){reference-type="ref"
reference="sec:linear"}, we saw that matrices can be viewed as taking a
set of basis vectors to another set of basis vectors. This means that
the actual numbers in a matrix are intimately connected to the initial
basis. For example, a matrix 

$$

\begin{aligned}
 A = 
 \begin{pmatrix}
  2 & 1 \cr 5 & 3
 \end{pmatrix}
\end{aligned}

$$

 takes the unit vector
$\hat{\rm e}_x = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$ to the vector
$\begin{pmatrix} 2 \\ 5 \end{pmatrix}$, and it takes the unit vector
$\hat{\rm e}_y = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$ to the vector
$\begin{pmatrix} 1 \\ 3 \end{pmatrix}$. The numbers in the matrix tell
us directly what is the destination of $\hat{\rm e}_x$ and
$\hat{\rm e}_y$. So now what do we do if we want to express the matrix
$A$ in different coordinates, let's say 

$$

\begin{aligned}
 \hat{\rm e}_u = \frac{1}{\sqrt{2}}
 \begin{pmatrix}
  1 \cr 1
 \end{pmatrix}
 \qquad\text{and}\qquad
  \hat{\rm e}_v = \frac{1}{\sqrt{2}}
 \begin{pmatrix}
  1 \cr -1
 \end{pmatrix}\, .
\end{aligned}

$$

 Clearly the numerical values of the matrix elements of
$A$ much change in some way. To answer this question, we first note that
given the basis vectors $\hat{\rm e}_j$ we can find the matrix element
$a_{jk}$ via 

$$

\begin{aligned}
 a_{jk} = (\hat{\rm e}_j,A\hat{\rm e}_k)\, ,
\end{aligned}

$$

 where in the example above $j,k = x,y$. You should
verify that you can reproduce the values 

$$

\begin{aligned}
 a_{11} = (\hat{\rm e}_x,A\hat{\rm e}_x) = 2\, , \quad
 a_{12} = (\hat{\rm e}_x,A\hat{\rm e}_y) = 1\, , \quad
 a_{21} = (\hat{\rm e}_y,A\hat{\rm e}_x) = 5\, , \quad
 a_{22} = (\hat{\rm e}_y,A\hat{\rm e}_y) = 3\, .
\end{aligned}

$$

 So if the matrix elements of $A$ with respect to the
basis $\{ \hat{\rm e}_j \}$ are given by
$(\hat{\rm e}_j,A\hat{\rm e}_k)$, then the same matrix, but in different
coordinates, i.e., a basis $\{ \hat{\rm e}_j' \}$, will be given by
$a_{jk}' = (\hat{\rm e}_j',A\hat{\rm e}_k')$. We can denote the matrix
in the primed basis by $A'$.

Next, we define the primed basis $\{ \hat{\rm e}_j' \}$ in terms of a
transformation $S$ that has an inverse $S^{-1}$, acting on the basis
$\{ \hat{\rm e}_j \}$: 

$$

\begin{aligned}
 \hat{\rm e}_j' = S \hat{\rm e}_j\, .
\end{aligned}

$$

 We can then write 
 
 $$

\begin{aligned}
 (\hat{\rm e}_j,A\hat{\rm e}_k) = \left(S^{-1}\hat{\rm e}_j',A S^{-1}\hat{\rm e}_k'\right) = \left(\hat{\rm e}_j',S A S^{-1}\hat{\rm e}_k'\right) \equiv (\hat{\rm e}_j',A' \hat{\rm e}_k')\, ,
\end{aligned}

$$

 where we used
$(S^{-1}\mbox{$\mathbf{a}$},\mbox{$\mathbf{b}$}) = (\mbox{$\mathbf{a}$},S\mbox{$\mathbf{b}$})$.
You can see this by noting that changing $\mbox{$\mathbf{b}$}$ in the
scalar product is equivalent to changing $\mbox{$\mathbf{a}$}$ in the
opposite way. Therefore the matrix elements of $A$ in the
$\{ \hat{\rm e}_j \}$ basis are the same as the matrix elements of $A'$
in the $\{ \hat{\rm e}_j' \}$ basis, and we can write 

$$

\begin{aligned}
 A' = SAS^{-1}\, .
\end{aligned}

$$

 This is called a *similarity transformation* of $A$. It
allows us to write matrices in different coordinate systems, among other
things.

Returning to our example above, we note that the transformation $S$ that
takes $\hat{\rm e}_x$ and $\hat{\rm e}_y$ to $\hat{\rm e}_u$ and
$\hat{\rm e}_v$ is 

$$

\begin{aligned}
 S = \frac{1}{\sqrt{2}} 
 \begin{pmatrix}
  1 & 1 \\ 1 & -1
 \end{pmatrix}
 \qquad\text{and} \qquad
 S^{-1} = S\, .
\end{aligned}

$$

 The matrix $A'$ is then 
 
 $$

\begin{aligned}
 A' = SAS = \frac12
 \begin{pmatrix}
  1 & 1 \\ 1 & -1
 \end{pmatrix}
 \begin{pmatrix}
  2 & 1 \\ 5 & 3
 \end{pmatrix}
 \begin{pmatrix}
  1 & 1 \\ 1 & -1
 \end{pmatrix}
 = \frac12
 \begin{pmatrix}
  11 & 3 \\ -5 & -1
 \end{pmatrix}\, .
\end{aligned}

$$

 Again, you should verify this.

The main subtlety of similarity transformations is to figure out which
operation is $S$ and which one is $S^{-1}$. It requires careful thought
about what the basis vectors are doing. In that sense similarity
transforms are the trickiest part of this course on matrices.

## Rotations around an arbitrary axis

We left a question in section
[\[sec:linear\]](#sec:linear){reference-type="ref"
reference="sec:linear"} about how we can construct a matrix around an
arbitrary axis in three dimensions. Consider the 3D rotation matrix
around the $x$-axis: 

$$

\begin{aligned}
 R_x(\theta) =
 \begin{pmatrix}
  1 & 0 & 0 \\
  0 & \cos\theta & -\sin\theta \\
  0 & \sin\theta & \cos\theta
 \end{pmatrix}\, .
\end{aligned}

$$

 Suppose we want to rotate around the axis that lies
45$^\circ$ rotated towards the $z$axis. This axis rotation is


$$

\begin{aligned}
 R_y(\pi/4) =
 \begin{pmatrix}
  \cos\pi/4 & 0 & -\sin\pi/4 \\
  0 & 1 & 0 \\
  \sin\pi/4 & 0 & \cos\pi/4
 \end{pmatrix}
 = \frac{1}{\sqrt{2}}
 \begin{pmatrix}
  1 & 0 & -1 \\
  0 & \sqrt{2} & 0 \\
  1 & 0 & 1
 \end{pmatrix}\, .
\end{aligned}

$$

 This rotation takes the unit in the $x$ direction to the
rotation axis. However, the similarity transform $S$ above is actually
the opposite (inverse) of this, because $S$ is the matrix that changes
the basis vectors and $\hat{\rm e}_x$ rotates away from the rotation
axis towards the *negative* $z$-axis. The rotation matrix around an axis
midway between the $x$ and $z$-axis is therefore 

$$

\begin{aligned}
 R_{45}(\theta) & = R_y(-\pi/4) R_x(\theta) R_y(\pi/4) \cr & = \frac12
 \begin{pmatrix}
  1 & 0 & 1 \\
  0 & \sqrt{2} & 0 \\
  -1 & 0 & 1
 \end{pmatrix}
 \begin{pmatrix}
  1 & 0 & 0 \\
  0 & \cos\theta & -\sin\theta \\
  0 & \sin\theta & \cos\theta
 \end{pmatrix}
 \begin{pmatrix}
  1 & 0 & -1 \\
  0 & \sqrt{2} & 0 \\
  1 & 0 & 1
 \end{pmatrix} \cr
 & = 
 \begin{pmatrix}
  \cos^2\frac{\theta}{2} & \sin\theta / \sqrt{2} & \sin^2\frac{\theta}{2} \\
  -\sin\theta / \sqrt{2} & \cos\theta & -\sin\theta / \sqrt{2} \\
  \sin^2\frac{\theta}{2} & \sin\theta / \sqrt{2} & \cos^2\frac{\theta}{2}
 \end{pmatrix} \, .
\end{aligned}

$$

 We used that the inverse of a rotation matrix
$R(\theta)$ is rotating by the same amount in the opposite direction
$R(-\theta)$. We can obtain other rotation axes using suitable
rotations, and this technique also works if one wants to reflect in some
arbitrary axis or plane.

## Invariants under similarity transformations

Similarity transforms preserve some aspects of a matrix. From the
properties of the determinant in section
[4.5](#sec:det){reference-type="ref" reference="sec:det"} you can see
that the determinant of a matrix after a similarity transform remains
unchanged: 

$$

\begin{aligned}
 \det A' = \det(SAS^{-1}) = \det S \det A \det S^{-1} = \det S \det A (\det S)^{-1} = \det A\, .
\end{aligned}

$$

 This makes sense, because a similarity transform takes a
matrix to a matrix that has the same effect on vectors, but in a
different coordinate system.

Another important quantity that remains invariant under similarity
transformations is the trace. The idea is simple: add up all the
elements along the diagonal: 

$$

\begin{aligned}
 \mbox{Tr}A = \sum_{j=1}^n a_{jj} = \sum_{j=1}^n (\hat{\rm e}_j, A \hat{\rm e}_j)\, .
\end{aligned}

$$

 Without proof we state that the trace has the so-called
*cyclic property*: 

$$

\begin{aligned}
 \mbox{Tr}(ABC) = \mbox{Tr}(CAB)\, .
\end{aligned}

$$

 Using this property, we can show that the trace of a
matrix is invariant under similarity transformations: 

$$

\begin{aligned}
 \mbox{Tr}(A') = \mbox{Tr}(SAS^{-1}) = \mbox{Tr}(AS^{-1}S) = \mbox{Tr}(A)\, .
\end{aligned}

$$

 The trace will play a key role in the calculation of
probabilities in quantum mechanics.
:::

[^1]: There is no guarantee that this will work, but if it does, we
    should be getting the right answer.

[^2]: This argument does not apply to two boosts in arbitrary
    directions; for that we need to include rotations, which is beyond
    the scope of this simple example.

