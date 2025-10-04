---
{"dg-publish":true,"permalink":"/计量经济学/Homoskedasticity and Heteroskedasticity/","created":"2025-01-08T17:29:14.000+08:00","updated":"2025-01-08T17:29:14.000+08:00"}
---

## Estimate Conditional Variance of Error

在同方差假设下，估计 $\boldsymbol{\Omega}$ 相当于要估计 $\sigma^{2}$，一个朴素（naive）估计量是残差的平方均值：
$$
\tilde{\sigma}^{2}=\frac{\mathbf{e}^{\mathsf{T}}\mathbf{e}}{n}
$$
然而，这个估计量是有偏的。

变换表达式为：
$$
\tilde{\sigma}^2=\frac{\mathbf{e}^{\mathsf{T}}\mathbf{e}}{n}=\frac{1}{n}\mathbf{e}^{\mathsf{T}}\mathbf{Me}=\frac{1}{n}\mathrm{Tr}(\mathbf{e}^{\mathsf{T}}\mathbf{M}\mathbf{e})=\frac{1}{n}\mathrm{Tr}(\mathbf{M}\mathbf{e}\mathbf{e}^{\mathsf{T}})
$$
这是因为① [[计量经济学/回归的几何意义#Annihilator Matrix\|Annihilator Matrix]] 的性质 ② $\mathbf{e}^{\mathsf{T}}\mathbf{M}\mathbf{e}$ 是一个二次型，也就是一个数（1×1 矩阵），根据 [[计量经济学/Trace Operator\|Trace Operator]] 的定义，数的迹等于自己。

朴素估计量的条件期望为
$$
\begin{align}
E[\tilde{\sigma}^{2}\mid \mathbf{X}]&=\frac{1}{n}\mathrm{Tr}(E[\mathbf{M}\mathbf{e}^{\mathsf{T}}\mathbf{e}\mid \mathbf{X}]) \\
&=\frac{1}{n}\mathrm{Tr}(\mathbf{M}E[\mathbf{e}^{\mathsf{T}}\mathbf{e}\mid \mathbf{X}]) \\
&=\frac{\sigma^{2}}{n}\mathrm{Tr}(\mathbf{M}) \\
&=\sigma^{2} \frac{n-k}{n}\neq \sigma^{2}
\end{align}
$$
其中，$\mathrm{Tr}(\mathbf{M})=n-k$ 表示线性投影后剩余的维度，见 [[计量经济学/回归的几何意义#Annihilator Matrix\|Annihilator Matrix]]

因此，需要经过一些调整得到无偏估计量
$$
\hat{\sigma}^{2}\equiv \frac{n}{n-k} \frac{\mathbf{e}^{\mathsf{T}}\mathbf{e}}{n}=\frac{\mathbf{e}^{\mathsf{T}}\mathbf{e}}{n-k}\implies E[\hat{\sigma}^{2}\mid \mathbf{X}]=\sigma^{2}
$$
从而得到同方差假设下的参数估计量条件方差估计值为
$$
\hat{V}=(\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1} \frac{\mathbf{e}^{\mathsf{T}}\mathbf{e}}{n-k}
$$
相应的，第 $j$ 个自变量的标准差为
$$
\widehat{Se}(\hat{\beta}_{j}\mid \mathbf{X})=\frac{\frac{\mathbf{e}^{\mathsf{T}}\mathbf{e}}{n-k}}{\sqrt{ (\mathbf{X}_{j}-\bar{\mathbf{X}}_{j})^{\mathsf{T}}(\mathbf{X}_{j}-\bar{\mathbf{X}}_{j})}}
$$

## Robust Standard Variance of LS Estimator

在异方差假设下，估计 $\boldsymbol{\Omega}$ 相当于要估计 $\sigma_{i}^{2}$，一个朴素（naive）估计量是残差的平方：
$$
\tilde{\sigma}_{i}=e_{i}^{2}
$$
从而得到异方差假设下的参数估计量条件方差估计量为
$$
\hat{V}^{HC 0}=(\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}\mathbf{X}^{\mathsf{T}}\begin{bmatrix}
e_1^2 & \cdots & 0\\
\vdots & \ddots & \vdots\\
0 & \cdots & e_n^2
\end{bmatrix}
\mathbf{X}(\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}
$$
然而朴素估计量是有偏的，无偏估计量为
$$
\hat{\sigma}_{i}^{2}\equiv\frac{n}{n-k} e_{i}^{2}
$$
从而得到异方差假设下的参数估计量条件方差估计量为
$$
\hat{V}^{HC 1}=\frac{n}{n-k}\hat{V}^{HC 0}
$$
相应的，第 $j$ 个自变量所谓稳健标准差为
$$
\widehat{Se}(\hat{\beta}_{j}\mid \mathbf{X})=\sqrt{\hat{V}^{HC1}_{j}}
$$
其中，$\hat{V}_{j}^{HC 1}$ 表示 $\hat{V}^{HC 1}$ 主对角线上第 $j$ 个元素。
> 这也是 stata 当中使用 `robust` 选项默认使用的估计量

## Cluster Robust

