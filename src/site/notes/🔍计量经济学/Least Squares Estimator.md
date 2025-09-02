---
{"dg-publish":true,"permalink":"/🔍计量经济学/Least Squares Estimator/","created":"2025-08-20T11:56:55.000+08:00","updated":"2025-08-20T11:56:55.000+08:00"}
---

## Definition

根据 [[🔍计量经济学/Linear Projection Model#求解参数\|Linear Projection Model#求解参数]] 可知
$$S(b)=E[(Y-X^{\mathsf{T}} b^2)]$$
The **moment estimator** of $S(b)$ is
$$
\hat{S}(b)=\frac{1}{n}\sum\limits_{i=1}^n(Y_i-X_i^{\mathsf{T}}b)^2
$$
define $\hat{\beta}$ as the minimizer of $\hat{S}(b)$
$$
\hat{\beta}\equiv\mathop{\arg\min}\limits_{b \in \mathbb{R}^k}\hat{S}(b)
$$
and call $\hat{\beta}$ as the **least squares estimator** of $\beta$

> 注意，$\beta$ 是总体参数，是一个数；$\hat{\beta}$ 是一个样本估计量，是一个随机变量，其随机性来源于抽样。

## Solution

定义 Sum of Squared Risiduals 为 $SSR(b)\equiv n\hat{S}(b)=\sum\limits_{i=1}^n(Y_i-X_i^{\mathsf{T}}\beta)^2$，易知
$$
\hat{{\beta}}\equiv\mathop{\arg\min}\limits_{b \in \mathbb{R}^k}\hat{S}(b)=\mathop{\arg\min}\limits_{b \in \mathbb{R}^k}SSR(b)
$$
写作矩阵形式
$$
\hat{{\beta}}\equiv \mathop{\arg\min}\limits_{\mathbf{b} \in \mathbb{R}^k}SSR(\mathbf{b})=\mathop{\arg\min}\limits_{\mathbf{b} \in \mathbb{R}^k} \mathbf{e}^{\mathsf{T}}\mathbf{e}
$$
先展开再求导：
$$
\begin{align}
\mathbf{e}^{\mathsf{T}}\mathbf{e}
&=(\mathbf{Y}-\mathbf{X}\mathbf{b})^{\mathsf{T}} (\mathbf{Y}-\mathbf{X}\mathbf{b}) \\
&=\mathbf{Y}^{\mathsf{T}}\mathbf{Y}-\mathbf{Y}^{\mathsf{T}}\mathbf{X}\mathbf{b}-\mathbf{b}^{\mathsf{T}}\mathbf{X}^{\mathsf{T}}\mathbf{Y}+\mathbf{b}^{\mathsf{T}}\mathbf{X}^{\mathsf{T}}\mathbf{X}\mathbf{b} \\
&=\mathbf{Y}^{\mathsf{T}}\mathbf{Y}-2\mathbf{b}^{\mathsf{T}}\mathbf{X}^{\mathsf{T}}\mathbf{Y}+\mathbf{b}^{\mathsf{T}}\mathbf{X}^{\mathsf{T}}\mathbf{X}\mathbf{b}
\end{align}
$$
F.O.C.（称之为正规方程组）
$$
\frac{\partial SSR(\mathbf{b})}{\partial \mathbf{b}}=-2\mathbf{X}^{\mathsf{T}}\mathbf{Y}+2\mathbf{X^{\mathsf{T}}}\mathbf{X}\mathbf{b}=0
$$
therefore
$$
\hat{\beta}\equiv\left(\mathbf{X}^{\mathsf{T}}\mathbf{X} \right)^{-1}\left(\mathbf{X}^{\mathsf{T}}\mathbf{Y} \right)
$$
S.O.C.
$$
\frac{ \partial^{2} SSR(\mathbf{b}) }{ \partial \mathbf{b}\partial \mathbf{b}^{\mathsf{T}}} =2\mathbf{X}^{\mathsf{T}}\mathbf{X}
$$
这要求 $\mathbf{X}^{\mathsf{T}}\mathbf{X}$ 是正定矩阵。

也可以先求导再展开：
F.O.C. （前导不变，后导转置）
$$
\begin{align}
\frac{ \partial SSR(\mathbf{b}) }{ \partial \mathbf{b} }&=\frac{ \partial \mathbf{e}^{\mathsf{T}}(\mathbf{b})\mathbf{e}(\mathbf{b}) }{ \partial \mathbf{b} }  \\
&=\frac{ \partial \mathbf{e}^{\mathsf{T}}(\mathbf{b}) }{ \partial \mathbf{b} }\mathbf{e}(\mathbf{b})+\left[ \mathbf{e}^{\mathsf{T}}(\mathbf{b})\frac{ \partial \mathbf{e}(\mathbf{b}) }{ \partial \mathbf{b} }  \right]^{\mathsf{T}} \\
&=2\frac{ \partial \mathbf{e}^{\mathsf{T}}(\mathbf{b}) }{ \partial \mathbf{b} }\mathbf{e}(\mathbf{b})=0 \tag{※}\\
&=-2\mathbf{X}^{\mathsf{T}}(\mathbf{Y}-\mathbf{X}\mathbf{b})=0
\end{align}
$$
其中
$$
\frac{ \partial \mathbf{e}^{\mathsf{T}}(\mathbf{b}) }{ \partial \mathbf{b} }=\frac{ \partial (\mathbf{Y-\mathbf{X}\mathbf{b}})^{\mathsf{T}} }{ \partial \mathbf{b} }=-\mathbf{X}^{\mathsf{T}}
$$
## Residual Properties

根据前面的（※）可知
$$
\mathbf{X}^{\mathsf{T}}\mathbf{e}=\mathbf{0}_{k\times 1}
$$
若自变量包含常数项，则有
$$
\begin{bmatrix}
\mathbf{1}_{n}^{\mathsf{T}} \\
\mathbf{X}_{1}^{\mathsf{T}} \\
\vdots \\
\mathbf{X}_{k-1}^{\mathsf{T}}
\end{bmatrix}\mathbf{e}=\mathbf{0}\implies \mathbf{1}_{n}^{\mathsf{T}}\mathbf{e}=0\implies \bar{e}=0
$$
若自变量包含虚拟变量，则残差的分组均值为零。

---

## 附录：no-matrix calculus
### 单变量回归的情形

$$
SSR(b)=\sum\limits_{i=1}^n(Y_i-X_ib)^2=\left(\sum\limits_{i=1}^nY_i^2 \right)+2b\left(\sum\limits_{i=1}^nX_iY_i \right)+b^2\left(\sum\limits_{i=1}^nX_i^2 \right)
$$
F.O.C
$$
\frac{d SSR(b)}{d b}=2\left(\sum\limits_{i=1}^nX_iY_i \right)+2b\left(\sum\limits_{i=1}^n X_i^2 \right)=0
$$
therefore
$$
\hat{\beta}\equiv\frac{\sum\limits_{i=1}^nX_iY_i}{\sum\limits_{i=1}^nX_i^2}
$$
### 多变量回归的情形

$$
\begin{align}
SSR(b)=&\sum\limits_{i=1}^n(Y_i-X_i^{\mathsf{T}}b)(Y_i-X_i^{\mathsf{T}}b) \\
=&\sum\limits_{i=1}^nY_i^2-2\sum\limits_{i=1}^nY_iX_i^{\mathsf{T}}b+\sum\limits_{i=1}^nX_i^{\mathsf{T}}b X_i^{\mathsf{T}}b \\
=&\sum\limits_{i=1}^nY_i^2-2b^{\mathsf{T}} \sum\limits_{i=1}^nX_iY_i+b^{\mathsf{T}} \sum\limits_{i=1}^nX_iX_i^{\mathsf{T}} b
\end{align}
$$
> 注意：$X_i^{\mathsf{T}}b$ 是一个数因此转置后不变，即 $X_i^{\mathsf{T}} b=b^{\mathsf{T}} X_i$，这样变换将有助于后续应用[[🔍计量经济学/矩阵求导\|矩阵求导]]公式。

F.O.C.
$$
\begin{align}
\frac{d SSR(b)}{d b}
&=-2\sum\limits_{i=1}^nX_iY_i+\left[\left( \sum\limits_{i=1}^nX_iX_i^{\mathsf{T}}\right)+\left( \sum\limits_{i=1}^nX_iX_i^{\mathsf{T}}\right)^{\mathsf{T}}\right]b \\
&=-2\sum\limits_{i=1}^nX_iY_i+2\sum\limits_{i=1}^nX_iX_i^{\mathsf{T}} b \\
&=0
\end{align}
$$
> 注意：$\sum\limits_{i=1}^nX_iX_i^{\mathsf{T}}$ 是一个对称矩阵所以转置后不变。

therefore

$$
\hat{\beta}\equiv\left(\sum\limits_{i=1}^nX_iX_i^{\mathsf{T}} \right)^{-1}\left(\sum\limits_{i=1}^nX_iY_i \right)
$$
S.O.C
$$
\frac{\partial SSR(b)}{\partial b \partial b^{\mathsf{T}}}=2\sum\limits_{i=1}^nX_iX_i^{\mathsf{T}}
$$
which is a positive semi-definite matrix
> 二阶条件对应总体模型的假设 $E(XX^{\mathsf{T}})\succ O$


