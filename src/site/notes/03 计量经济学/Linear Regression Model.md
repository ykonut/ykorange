---
{"dg-publish":true,"permalink":"/03 计量经济学/Linear Regression Model/","created":"2024-05-22T16:36:10.000+08:00","updated":"2024-09-09T10:34:07.637+08:00"}
---

## 模型设定

结合 [[03 计量经济学/Linear CEF Model\|Linear CEF Model]] 和 [[03 计量经济学/Linear Projection Model\|Linear Projection Model]] 的技术性条件得到 Linear Regression Model
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

详见 [[03 计量经济学/Linear Projection Model#求解参数\|Linear Projection Model#求解参数]]

此时
$$
\begin{align*}
{\beta}_{p}&=E(XX^{\mathsf{T}})^{-1}E(XY)\\
&=E(XX^{\mathsf{T}})^{-1}E[X(X^{\mathsf{T}}{\beta}+e)]\\
&={\beta}+E(XX^{\mathsf{T}})^{-1}E[Xe]
\end{align*}
$$
根据 [[03 计量经济学/Linear CEF Model#CEF Error\|Linear CEF Model#CEF Error]] 可知
$$
E[Xe]=0\implies {\beta}_{p}={\beta}
$$
换言之，如果 $E[Xe]=0$ 不成立，${\beta}_{p}$ 就和 ${\beta}$ 不一致。

## 内生性问题

若 $E[Xe]\neq 0$，则称线性回归模型存在内生性问题。

$E[e|X]=0$ 是比 $E[Xe]=0$ 更强的假设，详见[[03 计量经济学/间奏：独立、均值独立与不相关\|间奏：独立、均值独立与不相关]]，也就是说不需要违背均值独立，只需要违背线性不相关就会出现内生性问题。

使用存在内生性问题的线性回归模型本质上就是在使用线性投影模型，而线性投影模型本质上只提供 estimand 不保证 identification 准确。此外，线性回归模型还具有超越线性投影模型的优良性质(BLUE)，因此有必要抢救一下。

使用工具变量法修复内生性问题，就是将线性投影模型修复为线性回归模型。

## Best Linear Predictor

详见 [[03 计量经济学/Linear Projection Model#Best Linear Predictor\|Linear Projection Model#Best Linear Predictor]]
