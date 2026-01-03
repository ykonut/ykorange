---
{"dg-publish":true,"permalink":"/计量经济学/LATE/","tags":["因果推断"],"created":"2025-09-12 19:18","updated":"2025-12-30 10:52"}
---


For unit $i$, we have a binary instrument variable $Z_{i}$, a binary treatment indicator $D_{i}$, and an observed outcome $Y_{i}$.

**Definition** Potential outcome of $Y$

$$
Y=\begin{cases}
Y(1, 1),  & \text{if } D=1, \ Z=1\\
Y(1, 0),  &  \text{if } D=1, \ Z=0\\
Y(0, 1),  &  \text{if } D=0, \ Z=1\\
Y(0, 0),  &  \text{if } D=0, \ Z=0\\
\end{cases}
$$

**Definition** Potential outcome of $D$

$$
D=\begin{cases}
D(1), & \text{if } Z=1 \\
D(0), & \text{if } Z=0 
\end{cases}
$$

Assumption 1 (independence)

$$
\begin{align}
\{ D(0),D(1) \} \perp \!\!\! \perp Z  \\
\{ Y(D(1),1),Y(D(0),0) \} \perp \!\!\! \perp Z
\end{align}
$$

这要求 $Z$ 和 $D$ 之间、$Z$ 和 $Y$ 之间不存在 confounders。

Assumption 2 (exclusion)

$$
\begin{align}
Y(1,1)=Y(1,0)\equiv Y(1) \\
Y(0,1)=Y(0,0)\equiv Y(0)
\end{align}
$$

给定 $D$ 的结果，$Z$ 与 $Y$ 的潜在结果无关。换言之，$Z$ 仅通过 $D$ 作用于 $Y$。

Assumption 3 (relavance)

$$
E[D(1)-D(0)]\neq 0
$$

$Z$ 的确作用于 $D$。

Assumption 4 (monotonicity)

$$
D(1)\geq D(0)
$$

## Wald Estimator

Wald estimator 定义为

$$
\frac{E[Y\mid Z=1]-E[Y\mid Z=0]}{E[D\mid Z=1]-E[D\mid Z=0]}
$$

其中，根据 independence 假设可知

$$
\begin{align}
E[Y\mid Z=1] & =E\{ Y(0)+D(1)[Y(1)-Y(0)]\mid Z=1 \} \\
 & =E\{ Y(0)+D(1)[Y(1)-Y(0)]\}
\end{align}
$$

类似地

$$
E[Y\mid Z=0]=E\{ Y(0)+D(0)[Y(1)-Y(0)]\}
$$

Wald estimator 化简为

$$
\begin{align}
 & =\frac{E\{ [D(1)-D(0)]\times[Y(1)-Y(0)] \}}{E[D(1)-D(0)]} \\
 & =\frac{E[Y(1)-Y(0)\mid D(1)>D(0)]\times P(D(1)>D(0))+0 }{1\times P(D(1)>D(0))+0} \\
 & =E[Y(1)-Y(0)\mid D(1)>D(0)]
\end{align}
$$

其中，根据 monotonicity 可知 $D(1)-D(0)$ 等于 1 或零，这取决于前者究竟大于还是等于后者。将这一结果和 $ATE\equiv E[Y(1)-Y(0)]$ 对比可知，Wald estimator 仅仅估计满足 $D(1)-D(0)$ 部分的处理效应，即所谓的 LATE(Local Average Treatment Effect)。

## LATE

那么，LATE 所说的“局部”（Local）究竟是符合哪些特征的个体？

借鉴医学术语，我们将人群划分为四类：

1. Always Takers
2. Never Takers
3. Compliers
4. Defiers
利用 $D$ 的潜在结果可以清晰地刻画其特征。

$$
\begin{align}
D_{a} & =D(1)=D(0)=1 \\

D_{n} & =D(1)=D(0)=0 \\

D_{c} &=\begin{cases}
D(1)=1, & \text{if } Z=1 \\
D(0)=0, & \text{if } Z=0 
\end{cases} \\
 
D_{d} & =\begin{cases}
D(1)=0, & \text{if } Z=1 \\
D(0)=1, & \text{if } Z=0 
\end{cases} \\
\end{align}
$$

举个例子（来自 [这里](https://www.zhihu.com/question/32199571/answer/109676571)），假设 $Z$ 是兵役抽签，$D$ 是参军情况，考虑四种人：

1. 坚定的爱国主义者：抽中了，自然要当兵；抽不中，依然主动要当兵。
2. 坚定的反战主义者：抽不中，自然不去当兵；抽中了，宁可坐牢也不当兵。
3. 普通人：抽中了，就去当兵；抽不中，就不去当兵。
4. 疯子：抽中了，宁可坐牢也不去当兵；抽不中，却死也要去当兵。

单调性假设 $D(1)\geq D(0)$ 本质上就是在假设不存在这种疯子，相关性假设又排除了 Always Takers 和 Never Takers 两种人。因此，工具变量方法估计的只是 Compliers 的处理效应。
