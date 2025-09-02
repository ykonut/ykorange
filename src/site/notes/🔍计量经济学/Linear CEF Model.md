---
{"dg-publish":true,"permalink":"/🔍计量经济学/Linear CEF Model/","created":"2025-08-20T11:56:57.000+08:00","updated":"2025-08-20T11:56:57.000+08:00"}
---

> [!ABSTRACT]
> 根据 [[🔍计量经济学/Conditional Expectation Function\|Conditional Expectation Function]] 的定义可知，$E[Y\mid X]$ is the best predictor of $Y$，但条件期望函数的形式仍然是未知的，这一结论只是套套逻辑。因此，我们需要对 CEF 的具体形式做出进一步假设。
## Setup

Linear CEF Model 设定如下：
1. 定义 CEF Error；
2. 假设 CEF 是线性的。
$$
\begin{cases}
e\equiv Y-E(Y|X) \\
E(Y|X)=X^{\mathsf{T}}{\beta} \\
\end{cases}
$$
注意到
$$
E(e|X)=E(Y-X^{\mathsf{T}}{\beta}\mid X)=E(Y|X)-X^{\mathsf{T}} {\beta}=0
$$
因此 Linear CEF Model 也常常表示为：
1. 线性模型假设；
2. 均值独立假设。
$$
\begin{cases}
Y=X^{\mathsf{T}}{\beta}+e\\
E(e|X)=0
\end{cases}
$$
> [!ATTENTION]
> 均值独立实际上是一个过于理想化的假设，相当于要求 $X$ 和 $e$ 线性无关。详见：[[🔍计量经济学/间奏：独立、均值独立与不相关\|间奏：独立、均值独立与不相关]]
## CEF Error
$$
\begin{align*}
E[e|X]=0 \tag{1} \\
E[e]=0 \tag{2} \\
E[h(X)e]=0 \tag{3}
\end{align*}
$$
**Proof**
$$
\begin{align*}
E[e|X]&=E[Y-E(Y|X)|X]=E[Y|X]-E(Y|X)=0 \tag{1} \\
E[e]&=E[E(e|X)]=0 \tag{2} \\
E[h(X)e]&=E[E(h(X)e|X)]=E[h(X)E(e|X)]=0 \tag{3}
\end{align*}
$$