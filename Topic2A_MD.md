Trigonometric and Hyperbolic Functions {ref}` <#U1>`
======================================

#### Trigonometric functions {ref}` <#trigonometric-functions>`

Trigonometry functions associate the sides of a right angled triangle to
it's angles. The three basic trigonometry functions are:

-   **cosine**: ratio of adjacent to hypotenuse 

$$
\frac{y}{r}=\cos\theta
$$ (eq:cos)

-   **sine**: ratio of opposite to hypotenuse 

$$
\frac{x}{r}=\sin\theta
$$ (eq:sin)

-   **tan**: ratio of opposite to adjacent

$$
\frac{x}{y}=\tan\theta=\frac{\sin\theta}{\cos\theta}
$$ (eq:tan)

Since the input angle can be 0-360$^{\circ}$, these trig functions are
typically defined using a circle. If the radius of the circle, i.e the
hypotenuse, is set to 1 the sine and cosine ratios reduce to opposite
and adjacent respectively. As the angle increases the values of these
ratios change and repeat periodically for each cycle around the circle.
Due to their periodic nature, trigonometric functions are used
frequently in physics to describe oscillating phenomena.


```{figure} ImagesB/Sin-cos-define.png
---
width: 40%
name: fig:SinCos-Define
---
Trigonometric functions relate the ratio of two sides to an angle of a
triangle.
```




```{figure} ImagesB/SinCos.png
---
width: 50%
name: fig:SinCos
---
Cosine and sine functions are shown for a single cycle for
$x=0\rightarrow2\pi$. Notice that the functions are identical but differ
in phase by $\pi/2$.
```


```{figure} ImagesB/Tan.png
---
width: 50%
name: fig:Tan
---
The $y=\tan x$ function shown for a single cycle for
$x=0\rightarrow2\pi$. Notice the asymptotes at odd multiples of $\pi/2$
.
```


The other three possible ratios should also be noted:

$$
\begin{aligned}
\mathrm{cosec}\,\theta & =\frac{r}{y}=\frac{1}{\sin\theta}\\
\sec\theta & =\frac{r}{x}=\frac{1}{\cos\theta}\\
\cot\theta & =\frac{x}{y}=\frac{1}{\tan\theta}\end{aligned}
$$ (eg:Alternatives)


#### Trigonometric identities {ref}` <#trigonometric-identities>`

There are many standard identities which can be useful in solving
analytical problems in physics. Memory of these is of course not
required but you should be aware of their existence or even better
practice proving them!

The first set relate the squares of the functions and can be proven via
Pythagoras's Theorem: 

$$\begin{aligned}
\cos^{2}\theta+\sin^{2}\theta=1\\
1+\tan^{2}\theta=\sec^{2}\theta\\
\cot^{2}\theta+1=\mathrm{cosec}^{2}\,\theta\end{aligned}$$ 

The double
angle formula are: 

$$\begin{aligned}
{\rm sin}\;2\theta&={\rm sin}\;(\theta+\theta)={\rm sin}\;\theta\;{\rm cos}\;\theta+{\rm cos}\;\theta\;{\rm sin}\;\theta=2{\rm sin}\;\theta{\rm \,cos}\;\theta\\
{\rm cos}\;2\theta&={\rm cos}\;(\theta+\theta)={\rm cos}\;\theta\;{\rm cos}\;\theta-{\rm sin}\;\theta\;{\rm sin}\;\theta={\rm cos}^{2}\;\theta-{\rm sin}^{2}\;\theta\end{aligned}
$$

The sum formula are: 

$$
\begin{aligned}
{\rm sin}\;A-{\rm sin}\;B & =2{\rm cos}\;(\frac{A+B}{2}){\rm sin}\;(\frac{A-B}{2})\\
{\rm sin}\;(A\pm B)= & {\rm sin}\;A\;{\rm cos}\;B\pm{\rm cos}\;A\;{\rm sin}\;B\\
{\rm cos}\;(A\pm B)= & {\rm cos}\;A\;{\rm cos}\;B\mp{\rm sin}\;A\;{\rm sin}\;B\\
{\rm sin}\;A+{\rm sin}\;B= & 2{\rm sin}\;(\frac{A+B}{2}){\rm cos}\;(\frac{A-B}{2})\\
{\rm sin}\;A-{\rm sin}\;B= & 2{\rm cos}\;(\frac{A+B}{2}){\rm sin}\;(\frac{A-B}{2})\\
{\rm cos}\;A+{\rm cos}\;B= & 2{\rm cos}\;(\frac{A+B}{2}){\rm cos}\;(\frac{A-B}{2})\\
{\rm cos}\;A-{\rm cos}\;B= & -2{\rm sin}\;(\frac{A+B}{2}){\rm sin}\;(\frac{A-B}{2})\\
2{\rm sin}\;A\;{\rm cos}\;B= & {\rm sin}\;(A+B)-{\rm sin}\;(A-B)\\
2{\rm sin}\;A\;{\rm sin}\;B= & {\rm cos}\;(A+B)-{\rm cos}\;(A-B)\\
2{\rm cos}\;A\;{\rm cos}\;B= & {\rm cos}\;(A+B)+{\rm cos}\;(A-B)\\
{\rm tan}\;(A+B)= & \frac{{\rm tan}\;A+{\rm tan}\;B}{1+{\rm tan}\;A\;{\rm tan}\;B}
\end{aligned}
$$

Finally there is the Cosine Rule:

$$c^{2}=a^{2}+b^{2}-2ab\cos C$$

the Sine rule:

$$\frac{\sin A}{a}=\frac{\sin B}{b}=\frac{\sin C}{c}$$

and the area of a triangle:

$$\frac{1}{2}ab\sin C=\frac{1}{2}bc\sin A=\frac{1}{2}ac\sin B$$

#### Hyperbolic Functions {ref}` <#hyperbolic-functions>`

Whereas the standard trigonometric functions are based on circles
($x^{2}+y^{2}=r^{2}$), hyperbolic trigonometric functions are based on
hyperbola ($x^{2}-y^{2}=1$) as shown in
Fig. {numref}`fig:Hyperbola`. The geometry defined by hyperbolic
functions have numerous applications in physics.

```{figure} ImagesB/UnitHyperbola.png
---
width: 40%
name: fig:Hyperbola
---
The hyperbola defined by the equation $x^{2}-y^{2}=1$.
```

```{figure} ImagesB/cosh_sinh.png
---
width: 50%
name: fig:hyperbolicfuncs1
---
The main hyperbolic functions are shown for $\sinh x$ and $\cosh x$
```

```{figure} ImagesB/tanh.png
---
width: 50%
name: fig:hyperbolicfuncs2
---
The main hyperbolic functions are shown for $\tanh x$
```


The functions themselves are combinations of exponential $e^{x}$ curves
and define hyperbolic versions of the trigonometric sine, cosine etc.:

$$
\begin{aligned}
\sinh x & =\frac{1}{2}\left(e^{x}-e^{-x}\right)\\
\cosh x & =\frac{1}{2}\left(e^{x}+e^{-x}\right)\\
\tanh x & =\frac{\sinh x}{\cosh x}=\frac{\mathrm{e}^{2x}-1}{\mathrm{e}^{2x}+1}\end{aligned}
$$


The graphs of these functions are shown in Fig. {numref}`fig:hyperbolicfuncs1` and
Fig. {numref}`fig:hyperbolicfuncs2`. There are also corresponding
reciprocals: 

$$\DeclareMathOperator{\sech}{sech} \sech x = 1/\cosh x$$

$$\DeclareMathOperator{\cosech}{cosech} \cosech x =1/\sinh x $$

$$\DeclareMathOperator{\coth}{coth} \coth x = 1/\tanh x$$
