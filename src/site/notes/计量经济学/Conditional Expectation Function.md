---
{"dg-publish":true,"permalink":"/计量经济学/Conditional Expectation Function/"}
---




## Law of Iterated Expectations

**Theorem** 
$$
E_{X}[E_{Y}(Y\mid X)]=E[Y]
$$
**Proof**
离散型随机变量
$$
\begin{align*}
E_{X}[E_{Y}(Y\mid X)]
&=\sum\limits_{x}E_{Y}(Y\mid X=x)P(X=x)\\
&=\sum\limits_{x}\sum\limits_{y}y\cdot P(Y=y\mid X=x)P(X=x)\\
&=\sum\limits_{x}\sum\limits_{y}y\cdot P(X=x\mid Y=y)P(Y=y)\\
&=\sum\limits_{x}P(X=x\mid Y=y)\sum\limits_{y}y\cdot P(Y=y)\\
&=\sum\limits_{y}y\cdot P(Y=y)\\
&=E[Y]
\end{align*}
$$
连续型随机变量
$$
\begin{align*}
E_{X}[E_{Y}(Y\mid X)]&=\int_{x}E_{Y}(Y\mid X)p_{X}(x)\ dx\\
&=\int_{x}\int_{y}y\cdot p_{Y\mid X}(x,y)dy\ p_{X}(x)\ dx\\
&=\int_{x}\int_{y}y\cdot p_{X\mid Y}(x,y)p_{Y}(y)\ dy\ dx\\
&=\int_{x}p_{X\mid Y}(x,y)\ dx\int_{y}y\cdot p_{Y}(y)dy\\
&=\int_{y}y\cdot p_{Y}(y)dy\\
&=E[Y]
\end{align*}
$$
## Best Predictor

**Theorem**
Let $g(X)$ be any function of $X$, then
$$
E[Y|X]=\mathop{\arg\min}\limits_g E[(Y-g(X))^2]
$$
**Proof**
$$
\begin{align}
E[(Y-g(X))^2]
&=E[(Y-E[Y|X]+E[Y|X]-g(X))^2] \\
&=E[(Y-E[Y|X])^2]+E[(E[Y|X]-g(X))^2]+ \\
&+2E[(Y-E[Y|X])(E[Y|X]-g(X))]
\end{align}
$$
the first term
$$
E[(Y-E[Y|X])^2]=E\{(Y-E[Y|X])^2|X\}=E\{Var[Y|X]\}\ge0
$$
the last term
$$
\begin{align}
&2E[(Y-E[Y|X])(E[Y|X]-g(X))] \\
=&2E[E\{(Y-E[Y|X])(E[Y|X]-g(X))|X\}] \\
=&2E[(E[Y|X]-g(X))E\{Y-E[Y|X]|X\}] \\
=&2E[(E[Y|X]-g(X))\{E[Y|X]-E[Y|X]\}] \\
=&0
\end{align}
$$
therefore, take
$$
g(X)=E[Y|X]
$$