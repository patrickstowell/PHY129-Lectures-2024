Differential Equations {ref}` <#U1>`
======================


### Introduction to Differential Equations {ref}` <#introduction-to-differential-equations>`

Differential equations are equations where variables are linked together
by differentiation, for example 

$$

\begin{aligned}
  \frac{dy}{dx}=x^2,\end{aligned}
  
  $$
  
   or, 
  
  $$
  
  \begin{aligned}
   \frac{d^2y}{dx^2}+ \sin{x} \left(\frac{dy}{dx}\right)^2+y=e^x.\end{aligned}
   
   $$

   

Differential equations are very important in physics. In many areas the
processes we are interested in are best described by differential
equations.

For example, in mechanics 

$$

\begin{aligned}
m \frac{d^2x}{dt^2}=F(x,t)\end{aligned}

$$

 describes the motion of a
particle of mass $m$ under the influence of a force $F(x,t)$.

In quantum mechanics, the central equation is the Schrödinger equation
for the wavefunction of a particle, $\psi(x,t)$, 

$$

\begin{aligned}
-\frac{\hbar^2}{2m} 
\frac{\partial^2\psi}{\partial x^2}+V(x)\psi=i \hbar \frac{\partial \psi}{\partial t}.\end{aligned}

$$



In electromagentism, Maxwell's equations, which determine the electric
and magnetic fields, are differential equations, for example


$$

\begin{aligned}
\frac{\partial E_x}{\partial x}
+\frac{\partial E_y}{\partial y}
+\frac{\partial E_z}{\partial z}=\rho\end{aligned}

$$

 where $\vec{E}=(E_x,E_y,E_z)$ is
the electric field and $\rho$ the charge density.

There are many types of differential equations and many different
mathematical and numerical tools used to solve them. We shall only cover
general concepts, and methods for solving first order ordinary
differential equations. Next year you will learn how to solve second
order ordinary differential equations and introduced to methods for
solving partial differential equations.

#### Classification of Differential Equations {ref}` <#classification-of-differential-equations>`

There are many different ways to classify differential equations and it
is important that you are able to identify the different types of
equations you will see.

#### Independent and Dependent Variables {ref}` <#independent-and-dependent-variables>`

The first thing you need to be able to determine is which variable(s)
are *independent* and which are *dependent*. For example, in


$$

\begin{aligned}
  \frac{dy}{dx}=x^2\end{aligned}
  
  $$
  
   $y$ depends on $x$, so $x$ is
independent and $y$ is dependent.

#### A brief note on partial differentiation {ref}` <#a-brief-note-on-partial-differentiation>`

When we have a function of more than one variable such as the the
displacement of a oscillating string in the $y$ direction which is
dependent on both the distance along the string in the $x$ direction and
time $t$, then we can differentiate $y(x,t)$ with respect to both $x$
and $t$. In doing so we hold one variable fixed, which means we treat it
is a constant. If we differentiate with respect to $x$, then the
notation we use for such a process is



$$

\left(\frac{\partial y}{\partial x}\right)_t \textrm{ or } \frac{\partial y}{\partial x}\bigg|_t \textrm{ or } \frac{\partial y}{\partial x}

$$



In the first two cases the subscript $t$ denotes that we perform the
differentiation, using the usual rules, whilst treating $t$ as a
constant. In the third case, perhaps the most commonly encountered in
physics, treating $t$ as a constant is implied. We will cover partial
differentiation in more detail next semester.

#### Ordinary or Partial? {ref}` <#ordinary-or-partial>`

In an ordinary differential equation, or *ODE*, there is only one
independent variable. For example, in 

$$

\begin{aligned}
  \frac{dy}{dx}=x^2,\end{aligned}
  
  $$
  
   $y$ depends only on $x$.

In a partial differential equation, or *PDE*, there are more than one
independent variables. For example, in the wave equation


$$

\begin{aligned}
\frac{\partial^2y}{\partial x^2}=\frac{1}{c^2}\frac{\partial^2y}{\partial t^2},
\end{aligned}

$$

 $y$
depends on $x$ and $t$.

PDEs are written in terms of partial derivatives. Generally, they are
harder to solve than ODEs.

#### Linear or Non-linear? {ref}` <#linear-or-non-linear>`

An equation is *linear* if the highest power of the dependent variable
or any of its derivatives is one. For example, 

$$

\begin{aligned}
  \frac{dy}{dx}=x^2\end{aligned}
  
  $$
  
   contyains only the first power of
$dy/dx$. Note that the higher power of the independent variable does not
matter for this definition.

A *nonlinear* equation contains higher powers. For example


$$

\begin{aligned}
  \frac{dy}{dx}=y^2\end{aligned}
  
  $$
  
   contains the second power of the
dependent variable $y$.

Note that 

$$

\begin{aligned}
  \frac{dy}{dx}=\sin{y}\end{aligned}
  
  $$
  
   is also nonlinear; you can think
of expanding $\sin{y}$ as a power series containing higher powers of
$y$. We shall see a more formal definition oflinearity later.

Generally, non-linear equations are harder to solve than linear ones,
though some methods work for both. Often, nonlinear equations can only
be solved numerically.

#### Order of an Equation {ref}` <#order-of-an-equation>`

The order of an equation is given by the highest derivative it contains.
For example 

$$

\begin{aligned}
  \frac{dy}{dx}=x^2\end{aligned}
  
  $$
  
   is a first order equation, because it
contains the first derivative of $y$. However 

$$

\begin{aligned}
  \frac{d^2y}{dx^2}+\frac{dy}{dx}+y=0,\end{aligned}
  
  $$
  
   is second order,
because of the second derivative.

Generally, lower order differential equations are easier to solve than
higher order ones.

#### Homogeneous or Inhomogeneous? {ref}` <#homogeneous-or-inhomogeneous>`

A linear differential equation is said to be *homogeneous* if all the
terms contain the dependent variable. Thus 

$$

\begin{aligned}
  \frac{d^2y}{dx^2}+\frac{dy}{dx}+y=0\end{aligned}
  
  $$
  
   is homogeneous,
while 

$$

\begin{aligned}
  \frac{dy}{dx}=x^2\end{aligned}
  
  $$
  
   is inhomegeneous because the $x^2$
term on the right hand side is independent of $y$. Another way to see
this is to realise that a homogeneous linear equation will always have a
solution with the dependent variable equal to zero.

#### Showing a Function Satisfies a Differential Equation {ref}` <#showing-a-function-satisfies-a-differential-equation>`

With experience, we are sometimes able to guess the solution, and then
just demonstrate that it satisfies the differential equation, which
might also lead to relationships between constants. Suppose that you are
asked to show that the function 

$$

\begin{aligned}
 y=\sin{\omega t} \, \cos{\alpha x}\end{aligned}
 
 $$
 
  satisfies the wave
equation 

$$

\begin{aligned}
\frac{\partial^2y}{\partial x^2}=\frac{1}{c^2}\frac{\partial^2y}{\partial t^2}.\end{aligned}

$$



Start with the left hand side of the equation 

$$

\begin{aligned}
\frac{\partial^2y}{\partial x^2}
&=\frac{\partial^2}{\partial x^2}\left[ \sin{\omega t} \, \cos{\alpha x}\right]\\
&=-\alpha^2 \sin{\omega t} \, \cos{\alpha x}.\end{aligned}

$$

 Then, for
the right hand side 

$$

\begin{aligned}
\frac{1}{c^2} \frac{\partial ^2y}{\partial t^2}
&=\frac{1}{c^2}
\frac{\partial^2}{\partial t^2}\left[\sin{\omega t} \, \cos{(\omega/c)x}\right]\\
&=-\frac{1}{c^2}
\omega^2 \sin{\omega t} \, \cos{(\omega/c)x}.\end{aligned}

$$

 Hence the
left hand side equals the right hand side with $\alpha = \omega/c$, so
the equation is satisfied.
