---
{"dg-publish":true,"permalink":"/03 计量经济学/Frisch-Waugh-Lovell Theorem/","created":"2024-05-22T16:36:06.000+08:00","updated":"2024-09-09T19:59:01.081+08:00"}
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

假设以下模型关于离散变量 $X$ 是饱和的，$D$ 是二元变量。
$$
Y=\beta_{D}D+X^{\mathsf{T}}\beta_{X}+e
$$
根据 F-W-L 定理，$\beta_{D}$ 相当于 $Y$ 对 $\tilde{D}$ 回归的系数，而 $\tilde{D}$ 是 $D$ 对 $X$ 回归的残差，即
$$
\tilde{D}\equiv D-E(D\mid X)
$$
> [!NOTE]
> 这里直接利用了 [[03 计量经济学/Linear CEF Model\|Linear CEF Model]] 的设定，不过并未假设 $E[D\mid X]$ 是线性的。这是因为若模型关于 $X$ 是饱和的，则 $E[D\mid X]$ 必然是线性的。

根据 [[03 计量经济学/Linear Projection Model#求解参数\|Linear Projection Model#求解参数]] 可知
$$
\beta_{D} =\frac{E[\tilde{D}Y]}{E[\tilde{D}^{2}]}=\frac{E[\tilde{D}E(Y\mid \tilde{D})]}{E[\tilde{D}^{2}]}=\frac{E[\tilde{D}E(Y\mid D,X)]}{E[\tilde{D}^{2}]}
$$
接下来，定义条件处理效应朴素估计量
$$
\Delta(X)\equiv E(Y\mid D=1,X)-E(Y\mid D=0,X)
$$
从而有
$$
E(Y\mid D,X)=E(Y\mid D=0,X)+D\Delta(X)
$$
代入 $\beta_{D}$ 的分子部分，结合期望迭代法则可得
$$
\begin{align}
\beta_{D} & =\frac{E[\tilde{D}E(Y\mid D,X)]}{E[\tilde{D}^{2}]} \\
 & =\frac{E[\tilde{D}E(Y\mid D=0,X)]}{E[\tilde{D}^{2}]}+\frac{E[\tilde{D}D\Delta(X)]}{E[\tilde{D}^{2}]} \\
 & =\frac{E[\tilde{D}D\Delta(X)]}{E[\tilde{D}^{2}]} \\
 & =\frac{E[E(\tilde{D}D\mid X)\Delta(X)]}{E[E(\tilde{D}^{2}\mid X)]}
\end{align}
$$
其中， $E(Y\mid D=0,X)$ 是关于 $X$ 的函数，根据 [[03 计量经济学/Linear CEF Model#CEF Error\|CEF Error]] 的性质可知该项为零。

引理 1
$$
E(\tilde{D}D\mid X)=E(\tilde{D}^{2}\mid X)
$$
证明：$\tilde{D}$ 定义式两边同时乘上 $\tilde{D}$ 并取期望可得
$$
\begin{align}
\tilde{D}^{2} & =\tilde{D}D-\tilde{D}E[D\mid X] \\
E[\tilde{D}^{2}] & =E[\tilde{D}D]-E[\tilde{D}E(D\mid X)] \\
E[E(\tilde{D}^{2}\mid X)] & =E[E(\tilde{D}D\mid X)]
\end{align}
$$
其中，$E(D\mid X)$ 是关于 $X$ 的函数，根据 [[03 计量经济学/Linear CEF Model#CEF Error\|CEF Error]] 的性质可知 $E[\tilde{D}E(D\mid X)]=0$ ；最后一个等式源自期望迭代法则，证毕。

引理 2：
$$
E(\tilde{D}^{2}\mid X)=E\{ [D-E(D\mid X)]^{2}\mid X \}=Var(D\mid X)
$$
证明：利用 $\tilde{D}$ 定义式即可。

**综上所述：**
$$
\beta_{D}=\frac{E[Vae(D\mid X)\Delta(X)]}{E[Var(D\mid X)]}
$$
即 $\beta_{D}$ 是条件处理效应朴素估计量关于条件方差 $Var(D\mid X)$ 的加权平均值。

结合[[03 计量经济学/因果推断/潜在结果框架\|潜在结果框架]]，如果满足强可忽略性假设，则 $\Delta(X)=ATT(X)$；进一步，如果处理效应 $TE$ 没有异质性，则 $ATT(X)=TE$ 为常数，此时 $\beta_{D}=TE$ 具有因果解释。由此可见，线性回归要具有因果解释需要强可忽略性+处理效应同质性这样困难无比的前提。
