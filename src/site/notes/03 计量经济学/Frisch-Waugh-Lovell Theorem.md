---
{"dg-publish":true,"permalink":"/03 计量经济学/Frisch-Waugh-Lovell Theorem/","created":"2024-05-22T16:36:06.000+08:00","updated":"2024-09-09T10:37:29.950+08:00"}
---

## 分块回归
考虑回归模型
$$
\mathbf{Y}=\mathbf{X}_1\hat{{\beta}}_1+\mathbf{X}_2\hat{{\beta}}_2+\mathbf{e}
$$
根据参数估计量的定义可得
$$
\begin{align}
\mathbf{X}^{\mathsf{T}}\mathbf{X}\hat{{\beta}}&=\mathbf{X}^{\mathsf{T}}\mathbf{Y} \\
\begin{bmatrix}
\mathbf{X}_{1}^{\mathsf{T}}\mathbf{X}_{1} & \mathbf{X}_{2}^{\mathsf{T}}\mathbf{X}_{2} \\
\mathbf{X}_{2}^{\mathsf{T}}\mathbf{X}_{1} & \mathbf{X}_{2}^{\mathsf{T}}\mathbf{X}_{2}
\end{bmatrix}
\begin{bmatrix}
\hat{{\beta}}_{1} \\
\hat{{\beta}}_{2}
\end{bmatrix}
&=\begin{bmatrix}
\mathbf{X}_{1}^{\mathsf{T}}\mathbf{Y} \\
\mathbf{X}_{2}^{\mathsf{T}}\mathbf{Y}
\end{bmatrix}
\end{align}
$$
因此有
$$
\begin{gather}
\mathbf{X}_{1}^{\mathsf{T}}\mathbf{X}_{1}\hat{{\beta}}_{1}+\mathbf{X}_{2}^{\mathsf{T}}\mathbf{X}_{2}\hat{{\beta}}_{2}=\mathbf{X}_{1}^{\mathsf{T}}\mathbf{Y} \tag{1}\\
\mathbf{X}_{2}^{\mathsf{T}}\mathbf{X}_{1}\hat{{\beta}}_{1}+\mathbf{X}_{2}^{\mathsf{T}}\mathbf{X}_{2}\hat{{\beta}}_{2}=\mathbf{X}_{2}^{\mathsf{T}}\mathbf{Y} \tag{2}
\end{gather}
$$
由 $(1)$ 可得
$$
\hat{{\beta}}_{1}=(\mathbf{X}_{1}^{\mathsf{T}}\mathbf{X}_{1})^{-1}\mathbf{X}_{1}(\mathbf{Y}-\mathbf{X}_{2}\hat{{\beta}}_{2})
$$
代入 $(2)$ 可得
$$
\begin{align}
\mathbf{X}_{2}^{\mathsf{T}}\mathbf{X}_{1}(\mathbf{X}_{1}^{\mathsf{T}}\mathbf{X}_{1})^{-1}\mathbf{X}_{1}(\mathbf{Y}-\mathbf{X}_{2}\hat{{\beta}}_{2})+\mathbf{X}_{2}^{\mathsf{T}}\mathbf{X}_{2}\hat{{\beta}}_{2}&=\mathbf{X}_{2}^{\mathsf{T}}\mathbf{Y} \\
\mathbf{X}_{2}^{\mathsf{T}}\mathbf{P}_{1}\mathbf{Y}-\mathbf{X}_{2}^{\mathsf{T}}\mathbf{P}_{1}\mathbf{X}_{2}\hat{{\beta}}_{2}+\mathbf{X}_{2}^{\mathsf{T}}\mathbf{X}_{2}\hat{{\beta}}_{2}&=\mathbf{X}_{2}^{\mathsf{T}}\mathbf{Y} \\
\mathbf{X}_{2}^{\mathsf{T}}\mathbf{P}_{1}\mathbf{Y}+\mathbf{X}_{2}^{\mathsf{T}}(\mathbf{I}-\mathbf{P}_{1})\mathbf{X}_{2}\hat{{\beta}}_{2}&=\mathbf{X}_{2}^{\mathsf{T}}\mathbf{Y} \\
\mathbf{X}_{2}^{\mathsf{T}}\mathbf{M}_{1}\mathbf{X}_{2}\hat{{\beta}}_{2}&=\mathbf{X}_{2}^{\mathsf{T}}\mathbf{M}_{1}\mathbf{Y}
\end{align}
$$
类似地可以得出 $\hat{{\beta}}_{1}$，最终解得
$$
\begin{cases}
\hat{{\beta}}_1=\left(\mathbf{X_1^{\mathsf{T}} M_2 X_1}\right)^{-1}\left(\mathbf{X_1^{\mathsf{T}} M_2 Y} \right) \\
\hat{{\beta}}_2=\left(\mathbf{X_2^{\mathsf{T}} M_1 X_2}\right)^{-1} \left(\mathbf{X_2^{\mathsf{T}} M_1 Y} \right)
\end{cases}
$$
由于[[03 计量经济学/Geometry of Projection#Annihilator Matrix\|消除矩阵]]是对称幂等的，所以 $\hat{{\beta}}_1$ 可以看作 $\mathbf{M}_{2}\mathbf{Y}$ 对 $\mathbf{M}_{2}\mathbf{X}_{1}$ 回归得到的参数估计量；类似地， $\hat{{\beta}}_2$ 可以看作 $\mathbf{M}_{1}\mathbf{Y}$ 对 $\mathbf{M}_{1}\mathbf{X}_{2}$ 回归得到的参数估计量。其中
$$
\begin{cases}
\mathbf{M}_1=\mathbf{I}_n-\mathbf{X_1(X_1^{\mathsf{T}} X_1)^{-1}X_1^{\mathsf{T}}} \\
\mathbf{M}_2=\mathbf{I}_n-\mathbf{X_2(X_2^{\mathsf{T}} X_2)^{-1}X_2^{\mathsf{T}}}
\end{cases}
$$
从几何的角度， $\mathbf{M}$ 给出向量到 $span(\mathbf{X})$ 的距离向量；$\mathbf{M}_{j}$ 给出向量到 $\mathbf{X}_{j}$ 的距离向量；从信息量的角度，$\mathbf{M}_{j}$ 消去了 $\mathbf{X}_{j}$ 的信息。

特别地，如果 $\mathbf{X}_{1}$ 和 $\mathbf{X}_{2}$ 不相关，即 $\mathbf{X}_{1}^{\mathsf{T}}\mathbf{X}_{2}=0\implies \mathbf{M}_{2}\mathbf{X}_{1}=\mathbf{X}_{1}$，此时
$$
\hat{{\beta}}_{1}=\left(\mathbf{X}_{1}^{\mathsf{T}}\mathbf{X}_{1} \right)^{-1}\left(\mathbf{X}_{1}^{\mathsf{T}}\mathbf{Y} \right)
$$
说明 $\mathbf{Y}$ 对 $\mathbf{X}_{1}$ 和 $\mathbf{X}_{2}$ 回归和 $\mathbf{Y}$ 单独对 $\mathbf{X}_{1}$ 回归得到的系数一致；换言之，加入和解释变量不相关的变量不影响该变量的回归系数。

## Frisch-Waugh-Lovell Theorem

要获得 $\hat{{\beta}}_i$，可以依据以下步骤：
1. $\mathbf{Y}$ 对 $\mathbf{X}_{-i}$ 回归，获得残差 $\tilde{\mathbf{Y}}$
2. $\mathbf{X}_i$ 对 $\mathbf{X}_{-i}$ 回归，获得残差 $\tilde{\mathbf{X}}_i$
3. $\tilde{\mathbf{Y}}$ 对 $\tilde{\mathbf{X}}_i$ 回归，获得残差 $\mathbf{e}$
4. $\tilde{\mathbf{X}}_i$ 的回归系数恰为 $\hat{{\beta}}_i$ 

本质上，这就是令 $\mathbf{M}_{-i}\mathbf{Y}$ 对 $\mathbf{M}_{-i}\mathbf{X}_{i}$ 回归得到回归系数 $\hat{{\beta}}_{i}$，其中 $\mathbf{M}_{-i}$ 表示在 $\mathbf{X}$ 中去除分块 $\mathbf{X}_{i}$ 得到的矩阵对应的消除矩阵。

> [!NOTE]
> 由于 $\mathbf{M}$ 是幂等矩阵，实际上 $\mathbf{M}_{-i}\mathbf{Y}$ 对 $\mathbf{M}_{-i}\mathbf{X}$ 回归和 $\mathbf{Y}$ 对 $\mathbf{M}_{-i}\mathbf{X}$ 回归是等价的。因此第一步其实可以略去。

## 应用：中心化
若模型包含常数项，则 $\mathbf{1}_{n}\in span(\mathbf{X})$，定义
$$
\begin{align}
\mathbf{P}_{0}&=\mathbf{1}_{n}\left( \mathbf{1}_{n}^{\mathsf{T}}\mathbf{1}_{n} \right)^{-1}\mathbf{1}_{n}^{\mathsf{T}} \\
\mathbf{M}_{0}&=\mathbf{I}_{n}-\mathbf{P}_{0}=\mathbf{I}_{n}-\mathbf{1}_{n}\left( \mathbf{1}_{n}^{\mathsf{T}}\mathbf{1}_{n} \right)^{-1}\mathbf{1}_{n}^{\mathsf{T}}
\end{align}
$$
> 考虑 $\mathbf{P}_{0}$ 的定义，$(\mathbf{1}^{\mathsf{T}}_n \mathbf{1}_n)^{-1}=\frac{1}{n}$ 而 $\mathbf{1}_{n}\mathbf{1}_{n}^{\mathsf{T}}$ 是一个所有元素全为 1 的 n×n 矩阵，后者右乘任意 n×1 的列向量都得到所有元素都为 n 维求和值列向量，再乘 $\frac{1}{n}$ 就得到 n 维平均值列向量；类似地，右乘任意 n×k 的矩阵就得到 n×k 的平均值矩阵（均值在列方向上取）

对于任意（可以相乘的）矩阵 $\mathbf{Z}$，有
$$
\begin{align}
\mathbf{P}_{0}\mathbf{Z}&=\bar{\mathbf{Z}}\\
\mathbf{M}_{0}\mathbf{Z}&=\mathbf{Z}-\bar{\mathbf{Z}}
\end{align}
$$
在上述模型中，设 $\mathbf{X}_{1}$ 为常数项 $\mathbf{X}_{2}=\mathbf{X}_{s}$ 为斜率项，则**斜率项系数**为
$$
\begin{align*}
\hat{{\beta}}_s&=[(\mathbf{M}_{0}\mathbf{X}_{s})^{\mathsf{T}}(\mathbf{M}_{0}\mathbf{X}_{s})]^{-1}[(\mathbf{M}_{0}\mathbf{X}_{s})^{\mathsf{T}}(\mathbf{M}_{0}\mathbf{Y})]\\
&=[(\mathbf{X}_s-\bar{\mathbf{X}}_s)^{\mathsf{T}}(\mathbf{X}_s-\bar{\mathbf{X}}_s)]^{-1}[(\mathbf{X}_s-\bar{\mathbf{X}}_s)^{\mathsf{T}}(\mathbf{Y}-\bar{\mathbf{Y}})]
\end{align*}
$$
或者更简单地写为
$$
\hat{{\beta}}_s=\frac{\widehat{Cov}(\mathbf{X}_{s},\mathbf{Y})}{\widehat{Var}(\mathbf{X}_{s})}
$$
相应地，在单变量回归中，斜率项系数的估计值为：
$$
\hat{{\beta}}_{s}=\frac{\sum(X_i-\bar{X})(Y_i-\bar{Y})}{\sum{(X_{i}-\bar{X})^2}}
$$
## 应用：回归与匹配

考虑离散变量的饱和回归，其中 $D$ 是虚拟变量
$$
Y=\beta_{D}D+W^{\mathsf{T}}\beta_{W}+e
$$
注意到
$$
\begin{align}
\beta_{D} & =\frac{Cov(Y,\tilde{D})}{Var(\tilde{D})} \\
 & =\frac{E\{[D-E(D\mid W)]E(Y\mid D,W)\}}{E[(D-E[D\mid X])^{2}]} \\
\end{align}
$$
其中，第一个等式来自 FWL 定理，第二个等式来自 $Y$ 和 $E(Y\mid D,W)$ 线性投影的等价性。

我们定义
$$
\delta_{W}\equiv E(Y\mid D=1,W)-E(Y\mid D=0,W)
$$
从而有
$$
E(Y\mid D,W)=E(Y\mid D=0,W)+\delta_{W}D
$$
代入 $\beta_{D}$ 的分子部分可得
$$
E\{[D-E(D\mid W)]E(Y\mid D=0,W)\}+E\{[D-E(D\mid W)]\delta_{W}D\}
$$
第一项相当于 $D$ 对 $W$ 回归的误差和 $W$ 的函数的协方差，根据 [[03 计量经济学/Linear CEF Model#CEF Error\|Linear CEF Model#CEF Error]] 的性质可知等于 0，第二项（？），因此
$$
\begin{align}
\beta_{D} & =\frac{E\{[D-E(D\mid W)]^{2}\delta_{W}\}}{E\{[D-E(D\mid W)]^{2}\}} \\
 & =\frac{E\{E\left( [D-E(D\mid W)]^{2}\mid W \right) \delta_{W}\}}{E\{E\left( [D-E(D\mid W)]^{2}\mid W \right)\}} \\
 & =\frac{E[Var(D\mid W)\delta_{W}]}{E[Var(D\mid W)]}
\end{align}
$$
由此可见，回归系数 $\beta_{D}$ 是处理效应 $\delta_{W}$ 关于条件方差 $Var(D\mid W)$ 的加权平均值。