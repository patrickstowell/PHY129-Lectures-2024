Integration by Parts
===========

Integration by Parts {ref}` <#integration-by-parts>`
--------------------

We start this section by thinking about differentiation rather than
integration, and particularly the **product rule** which states that


$$

\frac{d}{dx}\left(uv\right)=u\frac{dv}{dx}+v\frac{du}{dx}

$$

 Since both
sides are equal, we expect the integral of both sides to also be equal
(apart from the constants of integration) and so we can write


$$

\int\frac{d}{dx}\left(uv\right)dx=\int u\left(\frac{dv}{dx}\right)dx+\int v\left(\frac{du}{dx}\right)dx+B

$$


where *B* is a constant.

However we can see that $\int\frac{d}{dx}\left(uv\right)dx=uv$ and so by
rearrangement we have


$$

\int u\left(\frac{dv}{dx}\right)dx=uv-\int v\left(\frac{du}{dx}\right)dx+c

$$


although it is easier to write this in short-hand form


$$

\int uv'=uv-\int vu'+c

$$



It is useful to go through an example of integration by parts so that
you can see the steps and how the process is best laid out.

For the integral 

$$

\int xe^{x}dx

$$

 we start by assigning *u* and *v*.
Part of the skill of integrating by parts is assigning the right
functions to *u* and *v*, otherwise you end up making the integrand more
complicated. Let 

$$

\begin{aligned}
u=x &  & u'=1\\
v'=e^{x} &  & v=e^{x}\end{aligned}

$$

 and so we use the integration by
parts formula to get 

$$

\begin{aligned}
\int xe^{x}dx & = & xe^{x}-\int e^{x}dx+c\\
 & = & xe^{x}-e^{x}+x\\
 & = & e^{x}\left(x-1\right)+c\end{aligned}
 
 $$



Integration using Partial Fractions {ref}` <#integration-using-partial-fractions>`
-----------------------------------

The method of partial fractions can be used to simplify some integrals.
Lets take an example fraction that we want to integrate


$$

\frac{\left(3x-1\right)}{\left(x-2\right)\left(x+3\right)}

$$

 which we
can express as the sum of two partial fractions


$$

\frac{\left(3x-1\right)}{\left(x-2\right)\left(x+3\right)}=\frac{A}{\left(x-2\right)}+\frac{B}{\left(x+3\right)}

$$


Cross-multiplication and simplification gives 

$$

\begin{aligned}
\left(3x-1\right) & = & A\left(x+3\right)+B\left(x-2\right)\\
\left(3x-1\right) & = & x\left(A+B\right)+\left(3A-2B\right)\end{aligned}

$$


Equating coefficients (if you have forgotten how to do this, look back
at unit 1 notes) gives $A=1$ and $B=2$ , and so we can now rewrite the
integral of the original function as



$$

\begin{aligned}
\int\frac{\left(3x-1\right)}{\left(x-2\right)\left(x+3\right)} & = & \int\frac{1}{\left(x-2\right)}dx+\int\frac{2}{\left(x+3\right)}dx\\
 & = & \ln\left|x-2\right|+2\ln\left|x+3\right|+c\end{aligned}
 
 $$



Logarithmic integration {ref}` <#logarithmic-integration>`
-----------------------

You should already be familiar with the integral


$$

\int\frac{1}{x}\,\mathrm{d}x=\ln\left|x\right|+c

$$

 but this is in fact
a specific case of the general result


$$

\int\frac{f'\left(x\right)}{f\left(x\right)}\,\mathrm{d}x=\ln\left|f\left(x\right)\right|+c

$$


So, if the numerator is (or is related to) the first derivative of the
denominator then the result is of the form
$\ln\left|f\left(x\right)\right|$.
