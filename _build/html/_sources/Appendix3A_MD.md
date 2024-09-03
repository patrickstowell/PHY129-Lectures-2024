# Examples from physics {#sec:physics}

Here are some examples that demonstrate the usefulness of matrices in
physics, and help you develop a bit of an intuition about what they are
and how to use them. The material covered in this appendix is **not
needed for the PHY129 exam**. This appendix is an "optional extra". It
is meant to give you a flavour of ways in which you will come across
techniques learnt in this module in physics you study later. In later
years you may want to come back to these examples when you encounter the
relevant physics module. Finally, if you want to find out how the matrix
methods introduced here apply to *functions* more generally, watch [this
video from
3Blue1Brown](https://www.youtube.com/watch?v=TgKwz5Ikpc8&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=15).

## Polarisation filters

Light is polarised, and the polarisation can be described by a complex
two-dimensional vector. Here we will consider linear polarisation only,
so the vectors will have only real elements. The polarisations for
horizontal and vertical polarisation can be chosen as 

$$

\begin{aligned}
 \h = \begin{pmatrix} 1 \\ 0 \end{pmatrix}
 \qquad\text{and}\qquad
 \v = \begin{pmatrix} 0 \\ 1 \end{pmatrix}\, .
\end{aligned}

$$

 We can also have polarisation at $\pm 45^\circ$ from
these directions: 

$$

\begin{aligned}
 \d = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}
 \qquad\text{and}\qquad
 \a = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix}\, ,
\end{aligned}

$$

 where $\d$ and $\a$ stand for diagonal and
anti-diagonal. Let's send the $\d$ polarisation through a polarisation
filter $F_h$ that lets only horizontal polarisation through. This filter
is described by a *projection* onto $\h$: 

$$

\begin{aligned}
 F_h=  \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}\, .
\end{aligned}

$$

 You can easily verify that $F_h^2 = F_h$. The filter
acting on the $+45^\circ$ polarisation gives 

$$

\begin{aligned}
 F_h \d =  \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}\begin{pmatrix} 1 \\ 1 \end{pmatrix} =  \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 0 \end{pmatrix}\, .
\end{aligned}

$$

 This is in fact $\h$-polarised light, but the length of
the vector has shrunk. Since the intensity of the light is given by the
length-squared of the vector, we see that the filter removed half the
light, as expected.

Next, we place a polarisation filter oriented in the vertical direction
in the beam. This filter is represented by the matrix 

$$

\begin{aligned}
 F_v=  \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix}\, .
\end{aligned}

$$

 The output after this second filter is now


$$

\begin{aligned}
 F_v F_h \d =  \frac{1}{\sqrt{2}} \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 1 \end{pmatrix} =  \frac{1}{\sqrt{2}} \begin{pmatrix} 
0 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = 0\, .
\end{aligned}

$$

 Again as expected, the second filter extinguishes all
the light, because there is no vertical polarisation component in the
light just after it passes a horizontal polarisation filter. We could
have seen this with out the input light, by looking inly at the
matrices: 

$$

\begin{aligned}
 F_v F_h = \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = 0\, .
\end{aligned}

$$

 So *any* light will be extinguished by the combination
of these two filters.

Next, what happens if we slide a third polarisation filter between $F_h$
and $F_h$ in the diagonal direction? The projector is in the direction
of $\d$, do the projector $F_d$ becomes 

$$

\begin{aligned}
 F_d = \d \d^\dagger = \frac12 \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}\, .
\end{aligned}

$$

 Now what does $F_d$ do to the incoming light? You may
expect that because there is a horizontal *and* a vertical polarisation
filter in the series of filters, all light will still be extinguished.
Let's do the matrix calculation: 

$$

\begin{aligned}
 F_v F_d F_h = \frac12 \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} =
 \frac12 \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 1 & 0 \end{pmatrix} = \frac12 \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}\, .
\end{aligned}

$$

 This is *not the zero matrix*! It means that inserting
the filter $F_d$ rekindles the light that passes the polarisation
filters. In particular, it transfers a quarter of the original
horizontally polarised light into vertically polarised light (that's
what the location of the 1 and the factor $\frac12$ indicate). The
effect is demonstrated [in this
video](https://www.youtube.com/watch?v=KIHM37ePFYg).

Note that the order of the matrices is crucial here: the filter $F_d$
really must separate $F_h$ and $F_v$, otherwise we still have the full
light extinction. In technical terms, $F_d$ commutes with neither $F_h$,
nor $F_v$. Otherwise we would be able to rearrange the product so that
$F_h$ and $F_v$ multiply each other and give the zero matrix. Also note
that we can discuss the effect of the filters without worrying about the
incoming light by considering only the matrices. Even though matrices
are defined by the vectors they act upon, often we can draw physics
conclusions using matrices without getting vectors involved at all.

## Coupled harmonic oscillators

Consider the one-dimensional problem of two masses $m$, each connected
to opposite walls by springs with spring constant $k$. The masses are
connected by a spring with spring constant $k'$:

::: center
:::

The displacement from the equilibrium position of the two masses is
$x_1$ and $x_2$.

We set up a force balance using Hooke's law, where $a_1=\ddot{x}_1$ and
$a_2=\ddot{x}_2$ are the accelerations of the first and second mass,
respectively: 

$$

\begin{aligned}
\label{eq:028y4rehiudfs}
 - k x_1 + k' (x_2 - x_1) = m a_1
 \qquad\text{and}\qquad
 - k x_1 - k' (x_2 - x_1) = m a_2\, .
\end{aligned}

$$

 Make sure you understand how the signs come about in
these equations. Next, we make the assumption[^1] that the solutions to
these equations are given by 

$$

\begin{aligned}
 x_1 = \alpha_1 \cos(\omega t + \phi)
 \qquad\text{and}\qquad
 x_2 = \alpha_2 \cos(\omega t + \phi)\, .
\end{aligned}

$$

 for some $\omega$, $\phi$, and amplitudes $\alpha_1$ and
$\alpha_2$. The expressions in equation
([\[eq:028y4rehiudfs\]](#eq:028y4rehiudfs){reference-type="ref"
reference="eq:028y4rehiudfs"}) then become 

$$

\begin{aligned}
\label{eq:204yigrweh}
  - k \alpha_1 + k' (\alpha_2 - \alpha_1) = -m \omega^2 \alpha_1
 \qquad\text{and}\qquad
 - k \alpha_1 - k' (\alpha_2 - \alpha_1) = -m \omega^2 \alpha_2\, .
\end{aligned}

$$

 In matrix form with $\bm\alpha = (\alpha_1,\alpha_2)^T$,
we can write this as 

$$

\begin{aligned}
 A\bm\alpha = 
 \begin{pmatrix}
  k+k'-m\omega^2 & -k' \\ -k' & k+k'-m\omega^2 & -k'
 \end{pmatrix}
 \begin{pmatrix}
  \alpha_1 \\ \alpha_2
 \end{pmatrix} 
 = 0\, .
\end{aligned}

$$

 Note that this is independent of the phase $\phi$. To
see whether our assumption was valid, and these equations have
nontrivial solutions, we verify that $\det A = 0$: 

$$

\begin{aligned}
 \det A = 
 \begin{vmatrix}
  k+k'-m\omega^2 & -k' \\ -k' & k+k'-m\omega^2 & -k'
 \end{vmatrix}
 = (k+k'-m\omega^2)^2-{k'}^2 = 0\, .
\end{aligned}

$$

 This is satisfied for the positive angular frequencies


$$

\begin{aligned}
 \omega_1 = \sqrt{\frac{k}{m}} 
 \qquad\text{and}\qquad
 \omega_2 = \sqrt{\frac{k+2k'}{m}} \, .
\end{aligned}

$$

 Substituting these values back into equation
([\[eq:204yigrweh\]](#eq:204yigrweh){reference-type="ref"
reference="eq:204yigrweh"}), we find that 

$$

\begin{aligned}
 \omega_1 :\quad \alpha_1 = \alpha_2
 \qquad\text{and}\qquad
 \omega_2 :\quad \alpha_1 = -\alpha_2\, .
\end{aligned}

$$

 In other words, either the two masses can oscillate in
phase with the same amplitude, where the spring with constant $k'$ is
not compressed or extended during the oscillation, or the two masses
oscillate opposite to each other: 

$$

\begin{aligned}
 \omega_1 : & \qquad x_1 = \alpha \cos(\omega_1 t + \phi_1) \qquad\text{and}\qquad x_2 = \alpha \cos(\omega_1 t + \phi_1) \cr
 \omega_2 : & \qquad x_1 = \beta \cos(\omega_2 t + \phi_2) \qquad\text{and}\qquad x_2 = -\beta \cos(\omega_2 t + \phi_2)\, ,
\end{aligned}

$$

 where I keep the possibility open that the two
frequencies may have different amplitudes $\alpha$ and $\beta$. These
are called the *normal modes* of the two oscillating masses. Since this
is a linear system, superpositions of these normal modes will also be
solutions to the original equations of motion. Therefore


$$

\begin{aligned}
 x_1 & = \alpha \cos(\omega_1 t + \phi_1) + \beta \cos(\omega_2 t + \phi_2) \cr
 x_2 & = \alpha \cos(\omega_1 t + \phi_1) - \beta \cos(\omega_2 t + \phi_2)\, .
\end{aligned}

$$

 So with some fairly straightforward matrix techniques we
can find the solutions to the equations of motion of a pretty complex
system!

It is instructive to see how the normal modes of the system relate to
the eigenvalues and eigenvectors of $A$. The two eigenvalues of $A$ are
$k-m\omega^2$ and $k+2k' -m\omega^2$. So our choice of $\omega$ makes
one of the eigenvalues zero, which is sufficient to make the determinant
of $A$ zero. The eigenvectors of $A$ are 

$$

\begin{aligned}
 \v_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix} \qquad\text{and}\qquad \v_1 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}\, .
\end{aligned}

$$

 The top entry is proportional to the amplitude of the
first mass, and the bottom entry to the amplitude of the second mass.
You see that they have either the same amplitude or opposite amplitude.
Because of this connection to the eigenvalues and eigenvectors, the
normal modes are sometimes also called the *eigenmodes*. [Here is a
practical demonstration of the
effect](https://www.youtube.com/watch?v=CguKKl9mX2s).

## Moment of inertia tensor

The moment of inertia of a body depends on the axis of rotation. A disk
that is lying flat in the $xy$-plane with its centre of mass located at
the origin, and rotating around the $z$-axis will have a different
moment of inertia than if the same disk rotates around the $x$-axis. To
find the moment of inertia of a body rotating around an arbitrary axis
through its centre of mass therefore requires several numbers. However,
it turns out that we can solve this very elegantly using matrices.

From first year mechanics you know that the moment of inertia $I$ plays
the role of mass in rotations, and relates to the angular momentum $L$
as 

$$

\begin{aligned}
\label{eq:294iruhef}
 L = I \omega\, .
\end{aligned}

$$

 However, angular momentum is a three-dimensional vector
($\L$), and so is the angular rotation $\bm\omega$ if we take into
account the rotation axis. So equation
([\[eq:294iruhef\]](#eq:294iruhef){reference-type="ref"
reference="eq:294iruhef"}) must be fixed. Given that the moment of
inertia is axis-dependent, $I$ must be a $3\times 3$ matrix:


$$

\begin{aligned}
 \L = I\, \bm\omega = 
 \begin{pmatrix}
  L_x \\ L_y \\ L_z
 \end{pmatrix}
 =
 \begin{pmatrix}
  I_{xx} & I_{xy} & I_{xz} \\ I_{yx} & I_{yy} & I_{yz} \\ I_{zx} & I_{zy} & I_{zz}
 \end{pmatrix}
 \begin{pmatrix}
  \omega_x \\ \omega_y \\ \omega_z
 \end{pmatrix}
\end{aligned}

$$

 Note that for the purposes of this example, $I$ is no
longer the identity matrix! The matrix describing the momentum of
inertia is called a *tensor*, because it has some special transformation
properties that are not important right now. Also, $I$ is a real
symmetric matrix, so $I_{jk} = I_{kj}$ and $I_{jk}^* = I_{jk}$. The
off-diagonal elements are called the product of inertia. You can
calculate the elements of $I$ using the integrals 

$$

\begin{aligned}
 I_{xx} = \int  \left(y^2 + z^2 \right)\, dm\, ,\quad & I_{yy} = \int  \left(x^2 + z^2 \right)\, dm\, ,\quad I_{xx} = \int  \left(x^2 + y^2 \right)\, dm\, ,\cr  
 I_{xy} = - \int xy\, dm , \quad & I_{xz} = - \int xz\,dm , \quad  I_{yz} = - \int yz\, dm\, .
\end{aligned}

$$

 The diagonal elements are the normal moments of inertia
for rotations around the axis corresponding to the element's position in
the matrix.

A nice application of this is the situation where the moment of inertia
tensor has non-zero off-diagonal terms due to an asymmetry in the
rotating body. In that case the angular momentum does not line up with
the rotation vector. For example, 

$$

\begin{aligned}
 \L = I\, \bm\omega =
 \begin{pmatrix}
  J & - 0.2 J & 0 \\ -0.2 J & J & 0 \\ 0 & 0 & J
 \end{pmatrix}
 \begin{pmatrix}
  \omega \\ 0 \\ 0
 \end{pmatrix}
 = J\omega
 \begin{pmatrix}
  1 \\ -0.2 \\ 0 
 \end{pmatrix} \, .
\end{aligned}

$$

 The angular momentum $\L$ clearly does not point in the
direction of $\bm\omega$. This produces a torque $\bm\tau = d\L/dt$,
which can be substantial if $\bm\omega$ and $\L$ are large. An example
of this can be found in [this
video](https://www.youtube.com/watch?v=1TqBSI8ZBzQ).

## Generators of rotations

Let's define a matrix 

$$

\begin{aligned}
 L_z = \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}\, .
\end{aligned}

$$

 For reasons that will become clear in a minute we
exponentiate the matrix $L_z$ multiplied by an angle $\theta$:


$$

\begin{aligned}
 \exp\left( \theta L_z \right) = \exp\left[\theta \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}  \right]\, .
\end{aligned}

$$

 How do we exponentiate a matrix? We know we can multiply
matrices, so we can take the series expansion of the exponential and
calculate the result that way: 

$$

\begin{aligned}
  \exp\left( \theta L_z \right) = 1 + \theta L_z + \frac{\theta^2}{2!} L_z^2 + \frac{\theta^3}{3!} L_z^3 + \frac{\theta^4}{4!} L_z^4 + \ldots
\end{aligned}

$$

 Next, we calculate the powers of $L_z$:


$$

\begin{aligned}
 L_z^2 & = \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} = \begin{pmatrix} -1 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 
0 \end{pmatrix}\, ,\cr
 L_z^3 & = - L_z\, , \cr 
 L_z^4 & = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}\, .
\end{aligned}

$$

 You see that $L_z^5 = L_z$, and we repeat the cycle. The
intermediate matrices $-L_z^2$ and $L_z^2$ are not quite the identity
matrix, but they are close. Let's call it $I'$. The series expansion of
the exponential then splits into two series of even and odd powers:


$$

\begin{aligned}
  \exp\left( \theta L_z \right) = 1 +  \left( \frac{\theta^2}{2!}  + \frac{\theta^4}{4!} + \ldots \right) I' + \left( \theta \frac{\theta^3}{4!} + \ldots \right) L_z\, .
\end{aligned}

$$

 We have to be careful about the first term, denoted here
by 1. Since the sum in the series expansion is over terms that are
$3\times 3$ matrices, and we can add only matrices of the same size, the
first term must be in fact the proper identity matrix $I$. Next, we see
that the terms in brackets are familiar: the last term is $\sin\theta$,
while the first series in brackets is close to $\cos\theta$. We can add
and subtract 1 inside the brackets in the first series to obtain


$$

\begin{aligned}
  \exp\left( \theta L_z \right) = I - I' + \cos\theta I'  + \sin\theta L_z = \begin{pmatrix} \cos\theta & -\sin\theta & 0 \\ \sin\theta & \cos\theta & 0 \\ 0 & 0 & 1 \end{pmatrix}\, .
\end{aligned}

$$

 This is the rotation matrix $R_z(\theta)$ around the
$z$-axis.

We can also define matrices $L_x$ and $L_y$ that, when exponentiated,
create rotations around the $x$- and $y$-axis: 

$$

\begin{aligned}
 L_x = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & -1 \\ 0 & 1 & 0 \end{pmatrix} 
 \qquad\text{and}\qquad
 L_y = \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ -1 & 0 & 0 \end{pmatrix} \, .
\end{aligned}

$$

 The three matrices obey the commutation relations


$$

\begin{aligned}
\label{eq:vjhg49820uwoeij}
 [L_i,L_j] = \sum_k \epsilon_{ijk} L_k\, , 
\end{aligned}

$$

 where $i$, $j$, and $k$ take on the values $x$, $y$, and
$z$, and the special symbol $\epsilon_{ijk}$ is the *Levi-Civita* symbol
that takes on the values 

$$

\begin{aligned}
 \epsilon_{ijk} = 
 \begin{cases}
  1 &\quad\text{if $(i,j,k)$ is an even permutation of $(x,y,z)$,} \cr
  -1 &\quad\text{if $(i,j,k)$ is an odd permutation of $(x,y,z)$,} \cr
  0 &\quad\text{if and $i,j,k$ are the same.} \cr
 \end{cases}
\end{aligned}

$$

 The matrices $L_x$, $L_y$, and $L_z$ are called the
*generators* of rotations. Any three matrices of size $n\times n$ (with
$n\geq 3$) that obey the commutation relations in equation
([\[eq:vjhg49820uwoeij\]](#eq:vjhg49820uwoeij){reference-type="ref"
reference="eq:vjhg49820uwoeij"}) generate rotation matrices in a space
of dimension $n$.

Finally, we can see how the matrices $L_j$ are related to angular
momentum. Recall that angular momentum is defined by $\L = \r\times \p$
with $\r$ and $\p$ the position and momentum vectors, respectively. The
components of $\L$ are 

$$

\begin{aligned}
 \mathcal{L}_x = y p_z - z p_y\, , \qquad \mathcal{L}_y = z p_x - x p_z\, , \qquad\text{and}\qquad \mathcal{L}_z = x p_y - y p_x\, .
\end{aligned}

$$

 Now we can see the connection: the $j^{\rm th}$
component of the angular momentum is related to the matrix ${L}_j$ via
the relation $\mathcal{L}_j = \r\cdot (L_j \p)$: 

$$

\begin{aligned}
 L_x & = \begin{pmatrix} x & y & z \end{pmatrix} \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & -1 \\ 0 & 1 & 0 \end{pmatrix} \begin{pmatrix} p_x \\ p_y \\ p_z \end{pmatrix}\, ,\cr
 L_y & = \begin{pmatrix} x & y & z \end{pmatrix} \begin{pmatrix} 0 & 0 & 1 \\ 0 & 0 & 0 \\ -1 & 0 & 0 \end{pmatrix} \begin{pmatrix} p_x \\ p_y \\ p_z \end{pmatrix}\, ,\cr
 L_z & = \begin{pmatrix} x & y & z \end{pmatrix} \begin{pmatrix} 0 & -1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} \begin{pmatrix} p_x \\ p_y \\ p_z \end{pmatrix}\, ,
\end{aligned}

$$

 We say that angular momentum is the generator of
rotations.

## Lorentz boosts

Matrices play a central role in both special and general relativity. As
a simple example, consider a particle in one dimension with a position
coordinate $x$ and time coordinate $t$, as measured relative to a
reference frame. The values for these coordinates specify where the
particle is at what time in that reference frame. Not all combinations
of $x$ and $t$ will occur for a given particle; there will be a
relationship between position and time, $x(t)$, which is the particle's
trajectory. However, any possible trajectory can be captured by these
two numbers, and we collect them in a vector $\s$: 

$$

\begin{aligned}
 \s = \begin{pmatrix} x \\ t \end{pmatrix}\, .
\end{aligned}

$$

 Next, we want to know how to express $\s$ in a different
reference frame (denote the vector by $\s'$), moving at velocity $v$ in
the positive $x$-direction as seen from the original reference frame.
For a non-relativistic (Galilean) transformation, the coordinates in
this new reference frame will be 

$$

\begin{aligned}
 x' = x - vt \qquad\text{and}\qquad t' = t\, . 
\end{aligned}

$$

 As the primed frame moves in the positive direction with
respect to the original frame, the position $x$ in the original frame
moves in opposite direction in the primed frame (try to visualise this).
The time in each frame remains unchanged, i.e., clock readings are not
effected by this transformation. We can capture these two equations
neatly in a matrix equation: 

$$

\begin{aligned}
 \s' = \begin{pmatrix} x' \\ t' \end{pmatrix} = G \s = \begin{pmatrix} 1 & -v \\ 0 & 1 \end{pmatrix} \begin{pmatrix} x \\ t \end{pmatrix} = \begin{pmatrix} x-vt \\ t \end{pmatrix}\, ,
\end{aligned}

$$

 where we defined the Galilean transformation matrix $G$
as the matrix that changes between the original reference frame and the
primed frame. You should verify yourself the neat property that


$$

\begin{aligned}
 G(u) G(v) = G(u+v)\, ,
\end{aligned}

$$

 where we explicitly included the velocity dependence of
the matrix $G$. So the combination of two Galilean transformations is
again a Galilean transformation.

Now consider Lorentz transformations of the same system. Instead of the
time coordinate $t$, for convenience we consider the scaled coordinate
$ct$ with $c$ the speed of light in vacuum: 

$$

\begin{aligned}
 x' = \gamma x - \gamma\beta ct \qquad\text{and}\qquad ct' = \gamma ct - \gamma\beta x\, ,
\end{aligned}

$$

 with $\beta = v/c$ and
$\gamma = (1-\beta^2)^{-\frac12}$. In matrix notation, this becomes


$$

\begin{aligned}
 \s' = \begin{pmatrix} x' \\ ct' \end{pmatrix} = L \s = \begin{pmatrix} \gamma & -\beta\gamma \\ -\beta\gamma & \gamma \end{pmatrix} \begin{pmatrix} x \\ ct \end{pmatrix}\, ,
\end{aligned}

$$

 where the matrix $L$ is called the *Lorentz boost*.

We now want to show that two boosts in the same direction[^2] again
produce a boost. To achieve this, we note that 

$$

\begin{aligned}
 \gamma^2 - \beta^2 \gamma^s = 1\, .
\end{aligned}

$$

 This allows us to parametrise $\gamma$ and $\beta\gamma$
in terms of $\cosh r$ and $\sinh r$ as follows: 

$$

\begin{aligned}
 \gamma = \cosh r \qquad\text{and}\qquad \beta \gamma = \sinh r\, ,
\end{aligned}

$$

 where the parameter $r$ is called the *rapidity*. Try to
derive the relationship between the boost $v$ and the rapidity $r$:


$$

\begin{aligned}
 v = c \tanh r\, .
\end{aligned}

$$

 The Lorentz boost now takes the simple form


$$

\begin{aligned}
 L = \begin{pmatrix}  \cosh r & -\sinh r \\ -\sinh r &  \cosh r \end{pmatrix}\, ,
\end{aligned}

$$

 Two boosts with rapidities $r_1$ and $r_2$ then produce
a new boost given by 

$$

\begin{aligned}
\label{eq:gh304woeijrs}
 L (r_2) L(r_1) & = \begin{pmatrix}  \cosh r_2 & -\sinh r_2 \\ -\sinh r_2 &  \cosh r_2 \end{pmatrix} \begin{pmatrix}  \cosh r_1 & -\sinh r_1 \\ -\sinh r_1 &  \cosh r_1 \end{pmatrix} \cr
 & =  \begin{pmatrix}  \cosh r_1 \cosh r_2 + \sinh r_1 \sinh r_2 &  -\cosh r_1 \sinh r_2 - \cosh r_2 \sinh r_1 \\  -\cosh r_1 \sinh r_2 - \cosh r_2 \sinh r_1 &  \cosh r_1 \cosh r_2 + \sinh r_1 \sinh 
r_2 \end{pmatrix} \cr
 & = L(r_1+r_2) \, .
\end{aligned}

$$

 The last equality can be found by using the addition
formulas 

$$

\begin{aligned}
\label{eq:gry4y928woesd}
 \cosh r_1 \cosh r_2 + \sinh r_1 \sinh r_2 & = \cosh (r_1 + r_2)\, , \cr
 \cosh r_1 \sinh r_2 + \sinh r_1 \cosh r_2 & = \sinh (r_1 + r_2)\, .
\end{aligned}

$$

 The addition formula in special relativity is


$$

\begin{aligned}
 u = \frac{v_1 + v_2}{1 + \frac{v_1 v_2}{c^2}}\, .
\end{aligned}

$$

 Can you derive this from equations
([\[eq:gh304woeijrs\]](#eq:gh304woeijrs){reference-type="ref"
reference="eq:gh304woeijrs"}) and
([\[eq:gry4y928woesd\]](#eq:gry4y928woesd){reference-type="ref"
reference="eq:gry4y928woesd"})?

## Energy levels in a two-level atom

In quantum mechanics, measurable properties are represented by Hermitian
matrices. For example, the energy of a system is a matrix called the
Hamiltonian. As an example, consider a two-level atom with a ground
state $|g\rangle$ and an excited state $|e\rangle$. Despite the strange
notation, these are just vectors: 

$$

\begin{aligned}
 |g\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}
 \qquad\text{and}\qquad
 |e\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}\, .
\end{aligned}

$$

 For an isolated two-level atom, the ground state energy
$E_g$ and the excited state energy $E_e$ are eigenvalues of the
Hamiltonian, so that 

$$

\begin{aligned}
 H|g\rangle = E_g |g\rangle & =  \begin{pmatrix} E_g & 0 \\ 0 & E_e \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = E_g |g\rangle \cr
 H|e\rangle = E_e |e\rangle & =  \begin{pmatrix} E_g & 0 \\ 0 & E_e \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = E_e |e\rangle\, .
\end{aligned}

$$

 Next, imagine a laser interacting with the atom. If the
atom is in the ground state, the laser can excite it to the excited
state, and vice versa. In terms of matrices, this becomes


$$

\begin{aligned}
 |g\rangle \rightarrow |e\rangle = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 0 \end{pmatrix} 
  \qquad\text{and}\qquad
 |e\rangle \rightarrow |g\rangle =  \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} 0 \\ 1 \end{pmatrix}\, .
\end{aligned}

$$

 So the off-diagonal elements are responsible for the
transitions. The values of these elements represent the strength of the
interaction. A general Hamiltonian can then be written as


$$

\begin{aligned}
\label{eq:buhg9834owr}
 H = \begin{pmatrix} E_g & \hbar\Omega^* \\ \hbar\Omega & E_e \end{pmatrix}\, ,
\end{aligned}

$$

 where $\hbar\Omega$ is the interaction strength. It is
generally a complex number because it includes the phase of the laser
(this is not important right now). You can prove that $H$ is Hermitian,
which means that its eigenvalues are real.

The energy levels of the two-level system interacting with a laser
change. To find the new energy levels, we must find the eigenvalues of
$H$ in equation
([\[eq:buhg9834owr\]](#eq:buhg9834owr){reference-type="ref"
reference="eq:buhg9834owr"}). Let $E_g = 0$, $E_e 
= 1.2$ eV, and $\hbar\Omega = 0.3 i$ eV. We find the eigenvalues by
calculating 

$$

\begin{aligned}
 \det(H - \lambda I) = \begin{vmatrix} -\lambda & -0.30i \\ 0.30i & 1.2-\lambda \end{vmatrix} = \lambda^2 - 1.2\lambda - 0.09 = 0\, .
\end{aligned}

$$

 Therefore, the new eigenvalues are 

$$

\begin{aligned}
 \frac{1.2 \pm \sqrt{1.44 + 0.36}}{2} = 0.60 \pm \sqrt{0.45} = 0.60 \pm 0.67 = 
 \begin{cases}
  E_g' & = -0.07~\text{eV}\, , \cr
  E_e' & = 1.27~\text{eV}\, .
 \end{cases}
\end{aligned}

$$

 These are the new energy values of the two-level atom
interacting with a laser. You can see that the interaction drives the
two energy states apart, and the ground state energy becomes negative.
This is not a problem, because only energy *differences* are physically
meaningful.

Note also that the Hamiltonian must be Hermitian, because the
eigenvalues are physical quantities, and should therefore be real
numbers.

[^1]: There is no guarantee that this will work, but if it does, we
    should be getting the right answer.

[^2]: This argument does not apply to two boosts in arbitrary
    directions; for that we need to include rotations, which is beyond
    the scope of this simple example.
