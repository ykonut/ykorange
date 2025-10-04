---
{"dg-publish":true,"permalink":"/计量经济学/Linear Regression Model/","tags":["线性模型"],"created":"2025-01-18T15:45:20.000+08:00","updated":"2025-08-20T16:22:47.511+08:00"}
---

## 模型设定

结合 [[计量经济学/线性CEF模型\|线性CEF模型]] 和 [[计量经济学/Linear Projection Model\|Linear Projection Model]] 的技术性条件得到 Linear Regression Model
$$
\begin{cases}
Y=X^{\mathsf{T}}{\beta}+e\\
E(e\mid X)=0
\end{cases}
\tag{1}
$$
$$
\begin{cases}
E(Y^2)<\infty \\
E(\|X\|
{ #2}
)<\infty \\
E(XX^{\mathsf{T}}) \text{ is positive definite.}
\end{cases}
\tag{2}
$$
## 求解参数

详见 [[计量经济学/Linear Projection Model#求解参数\|Linear Projection Model#求解参数]]

此时
$$
\begin{align*}
{\beta}_{p}&=E(XX^{\mathsf{T}})^{-1}E(XY)\\
&=E(XX^{\mathsf{T}})^{-1}E[X(X^{\mathsf{T}}{\beta}+e)]\\
&={\beta}+E(XX^{\mathsf{T}})^{-1}E[Xe]
\end{align*}
$$
根据 [[计量经济学/线性CEF模型#CEF Error\|线性CEF模型#CEF Error]] 可知
$$
E[Xe]=0\implies {\beta}_{p}={\beta}
$$
换言之，如果 $E[Xe]=0$ 不成立，${\beta}_{p}$ 就和 ${\beta}$ 不一致。

## 内生性问题

若 $E[Xe]\neq 0$，则称线性回归模型存在内生性问题。

$E[e|X]=0$ 是比 $E[Xe]=0$ 更强的假设，详见[[计量经济学/附录：独立、均值独立与不相关\|附录：独立、均值独立与不相关]]，也就是说不需要违背均值独立，只需要违背线性不相关就会出现内生性问题。

使用存在内生性问题的线性回归模型本质上就是在使用线性投影模型，而线性投影模型本质上只提供 estimand 不保证 identification 准确。此外，线性回归模型还具有超越线性投影模型的优良性质(BLUE)，因此有必要抢救一下。

使用工具变量法修复内生性问题，就是将线性投影模型修复为线性回归模型。

## Best Linear Predictor

详见 [[计量经济学/Linear Projection Model#Best Linear Predictor\|Linear Projection Model#Best Linear Predictor]]
