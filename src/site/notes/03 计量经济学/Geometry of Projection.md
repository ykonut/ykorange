---
{"dg-publish":true,"permalink":"/03 计量经济学/Geometry of Projection/","created":"2024-05-22T16:36:11.000+08:00","updated":"2024-09-09T10:37:15.184+08:00"}
---


矩阵形式的样本回归方程写作
$$
\mathbf{Y}=\mathbf{X}\hat{{\beta}}+\mathbf{e}
$$
考虑自变量矩阵分块 $\mathbf{X}=[\mathbf{X}_1,\cdots,\mathbf{X}_k]$ ，其中 $\mathbf{X}_j$ 为第 $j$ 个自变量向量，每个自变量向量的维数都为 $n$，因此 $\mathbf{X}b$ 可以表示 $k$ 个向量在 $n$ 维空间的张成空间，即 $span(\mathbf{X}_{1},\dots,\mathbf{X}_{k})\in \mathbb{R}^n$；Linear Projection 即在张成空间内找到一个距离 $\mathbf{Y}$ 距离最近的向量定义为 $\hat{\mathbf{Y}}$。换言之，设定 $\mathbf{Y}$ 在 $span(\mathbf{X})$ 上的投影为 $\hat{\mathbf{Y}}$（这是因为投影的距离最近），也就是向量 $\mathbf{X}\hat{{\beta}}$ ，二者的距离为 $\lvert \mathbf{e} \rvert$

根据立体几何原理，$\mathbf{e}$ 应当垂直于整个张成空间，因此
$$
\begin{align}
\mathbf{X}^{\mathsf{T}}\mathbf{e}&=\mathbf{0}_{{k\times 1}} \\
\mathbf{X}^{\mathsf{T}}(\mathbf{Y}-\mathbf{X}\hat{{\beta}})&=\mathbf{0} \\
\mathbf{X}^{\mathsf{T}}\mathbf{Y}&=\mathbf{X}^{\mathsf{T}}\mathbf{X}\hat{{\beta}} \\
\hat{{\beta}}&=\left(\mathbf{X}^{\mathsf{T}}\mathbf{X} \right)^{-1}\left(\mathbf{X}^{\mathsf{T}}\mathbf{Y} \right)
\end{align}
$$
这里相当于为 [[03 计量经济学/Moment Estimation\|Moment Estimation]] 赋予了一种几何意义。

## Projection Matrix

定义投影矩阵
$$
\mathbf{P}\equiv \mathbf{X}(\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}\mathbf{X}^{\mathsf{T}}
$$
显然，投影矩阵对 $\mathbf{X}$ 有类似×1的效果
$$
\mathbf{PX}=\mathbf{X}(\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}\mathbf{X}^{\mathsf{T}}\mathbf{X}=\mathbf{X}
$$
事实上，投影矩阵对任意 $\mathbf{Z}=\mathbf{X\Gamma}$ 有类似×1 的效果
$$
\mathbf{PZ}=\mathbf{X}(\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}\mathbf{X}^{\mathsf{T}}\mathbf{X}\boldsymbol{\Gamma}=\mathbf{Z}
$$
特别地
$$
\begin{gather}
\mathbf{PY}=\mathbf{X(X^{\mathsf{T}} X)^{-1}X^{\mathsf{T}}}\mathbf{Y}=\mathbf{X}\hat{{\beta}}=\hat{\mathbf{Y}} \\
\mathbf{Pe}=\mathbf{P}(\mathbf{Y}-\mathbf{X}\hat{{\beta}})=\hat{\mathbf{Y}}-\mathbf{X}\hat{{\beta}}=\mathbf{0}
\end{gather}
$$
总之，投影的矩阵的几何意义是给出任意一个向量在 $span(\mathbf{X})$ 的投影向量，若作用在本就处于张成空间内的向量自然就有还原效果。

投影矩阵的重要性质：对称幂等
- $\mathbf{P}$ is symmetric ($\mathbf{P^{\mathsf{T}}}=\mathbf{P}$)
- $\mathbf{P}$ is idempotent ($\mathbf{PP}=\mathbf{P}$)（幂等）

投影矩阵的迹：
$$
\begin{align}
\mathrm{Tr}(\mathbf{P})
&=\mathrm{Tr}(\mathbf{X}(\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}\mathbf{X}^{\mathsf{T}}) \\
&=\mathrm{Tr}((\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}\mathbf{X}^{\mathsf{T}}\mathbf{X}) \\
&=\mathrm{Tr}(\mathbf{I}_{k}) \\
&=k
\end{align}
$$
 (refer [[03 计量经济学/Trace Operator\|Trace Operator]])
投影矩阵的迹表示了投影的维度，大小取决于 $span(\mathbf{X})$ 的维度
## Annihilator Matrix

定义消除矩阵
$$
\mathbf{M}\equiv \mathbf{I}_n-\mathbf{P}=\mathbf{I}_n-\mathbf{X}(\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}\mathbf{X}^{\mathsf{T}}
$$
显然，消除矩阵对 $\mathbf{X}$ 有类似 ×0 的效果
$$
\mathbf{MX}=(\mathbf{I}_n-\mathbf{P})\mathbf{X}=\mathbf{X}-\mathbf{PX}=\mathbf{X}
-\mathbf{X}=\mathbf{0}$$
事实上，消除矩阵对任意 $\mathbf{Z}=\mathbf{X\Gamma}$ 有类似 ×0 的效果
$$
\mathbf{MZ}=\mathbf{Z}-\mathbf{PZ}=\mathbf{Z}-\mathbf{Z}=\mathbf{0}
$$
特别地
$$
\begin{gather}
\mathbf{MY}=\mathbf{Y}-\mathbf{PY}=\mathbf{Y}-\hat{\mathbf{Y}}=\mathbf{e} \\
\mathbf{Me}=\mathbf{M}(\mathbf{Y}-\mathbf{X}{\beta})=\mathbf{e-0}=\mathbf{e}
\end{gather}
$$
总之，消除矩阵的几何意义是给出任意一个向量到 $span(\mathbf{X})$ 的距离向量，若作用在本就处于张成空间内的向量就得到零向量。

消除矩阵的重要性质：对称幂等
- $\mathbf{M}$ is symmetric ($\mathbf{M^{\mathsf{T}}}=\mathbf{M}$)
- $\mathbf{M}$ is idempotent ($\mathbf{MM}=\mathbf{M}$)（幂等）

消除矩阵的迹：
$$
\begin{align}
\mathrm{Tr}(\mathbf{M})&=\mathrm{Tr}(\mathbf{I}_{n}-\mathbf{P}) \\
&=\mathrm{Tr}(\mathbf{I}_{n})-\mathrm{Tr}(\mathbf{X}(\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}\mathbf{X}^{\mathsf{T}}) \\
&=\mathrm{Tr}(\mathbf{I}_{n})-\mathrm{Tr}((\mathbf{X}^{\mathsf{T}}\mathbf{X})^{-1}\mathbf{X}^{\mathsf{T}}\mathbf{X}) \\
&=\mathrm{Tr}(\mathbf{I}_{n})-\mathrm{Tr}(\mathbf{I}_{k}) \\
&=n-k
\end{align}
$$
 (refer [[03 计量经济学/Trace Operator\|Trace Operator]])

消除矩阵的迹表示了消除的维度，大小取决于到底消除了多数信息。一般地，若不存在完全共线性，消去 $m$ 个自变量信息的消除矩阵的迹为
$$
\mathrm{Tr}(\mathbf{M}_{\setminus m})=n-m
$$

## P/M Matrix of Constant

特别地，令 $\mathbf{X}=\mathbf{1}_{n}$ ，投影矩阵和消除矩阵为
$$
\begin{align}
\mathbf{P}_{0}&=\mathbf{1}_{n}\left( \mathbf{1}_{n}^{\mathsf{T}}\mathbf{1}_{n} \right)^{-1}\mathbf{1}_{n}^{\mathsf{T}} \\
\mathbf{M}_{0}&=\mathbf{I}_{n}-\mathbf{P}_{0}=\mathbf{I}_{n}-\mathbf{1}_{n}\left( \mathbf{1}_{n}^{\mathsf{T}}\mathbf{1}_{n} \right)^{-1}\mathbf{1}_{n}^{\mathsf{T}}
\end{align}
$$
> 考虑 $\mathbf{P}_{0}$ 的定义，$(\mathbf{1}^{\mathsf{T}}_n \mathbf{1}_n)^{-1}=\frac{1}{n}$ 而 $\mathbf{1}_{n}\mathbf{1}_{n}^{\mathsf{T}}$ 是一个所有元素全为 1 的 n×n 矩阵，后者右乘任意 n×1 的列向量都得到所有元素都为 n 维求和值列向量，再乘 $\frac{1}{n}$ 就得到 n 维平均值列向量；类似地，右乘任意 n×k 的矩阵就得到 n×k 的平均值矩阵（均值在列方向上取）。因此，$\mathbf{M}_{0}$ 矩阵右乘任意 n×k 矩阵得到 n×k 的去均值矩阵。

定义 $\bar{\mathbf{X}}_{i}=\mathbf{1}_{n}\bar{X}_{i}$ ，则有
$$
\begin{align}
\mathbf{P}_{0}\mathbf{X}&=
\begin{bmatrix}
\bar{\mathbf{X}}_{1}&\dots&\bar{\mathbf{X}}_{k}
\end{bmatrix} \\
\mathbf{M}_{0}\mathbf{X}&=\begin{bmatrix}
(\mathbf{X}_{1}-\bar{\mathbf{X}}_{1})&\dots&(\mathbf{X}_{k}-\bar{\mathbf{X}}_{k})
\end{bmatrix} \\
\mathbf{P}_{0}\mathbf{e}&=\bar{\mathbf{e}}=\mathbf{0} \\
\mathbf{M}_{0}\mathbf{e}&=\mathbf{e}
\end{align}
$$
由此可以证明均值点在回归线上
$$
\bar{\mathbf{Y}}=\mathbf{P}_{0}\mathbf{Y}=\mathbf{P}_{0}(\mathbf{X}{\beta}+\mathbf{e})=\bar{\mathbf{X}}{\beta}\implies \bar{Y}=\begin{bmatrix}
\bar{X}_{1}&\dots&\bar{X}_{k}
\end{bmatrix}{\beta}
$$
以及拟合值均值等于真值均值
$$
\bar{\mathbf{Y}}=\mathbf{P}_{0}\mathbf{Y}=\mathbf{P}_{0}(\hat{\mathbf{Y}}+\mathbf{e})=\mathbf{P}_{0}\hat{\mathbf{Y}}\implies \bar{Y}=\bar{\hat{Y}}
$$
投影矩阵和消除矩阵的迹为
$$
\begin{align}
\mathrm{Tr}(\mathbf{P}_{0})&=\mathrm{Tr}(1)=1 \\
\mathrm{Tr}(\mathbf{M}_{0})&=\mathrm{Tr}(\mathbf{I}_{n})-\mathrm{Tr}(1)=n-1
\end{align}
$$
