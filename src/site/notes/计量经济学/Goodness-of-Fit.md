---
{"dg-publish":true,"permalink":"/计量经济学/Goodness-of-Fit/"}
---

## Coefficient of determination

根据 [[计量经济学/回归的几何意义#Projection Matrix\|Projection Matrix]] 和 [[计量经济学/回归的几何意义#Annihilator Matrix\|Annihilator Matrix]] 的性质
$$
\begin{align}
\hat{\mathbf{Y}}^{\mathsf{T}}\hat{\mathbf{Y}}&=(\mathbf{P}\mathbf{Y})^{\mathsf{T}}(\mathbf{P}\mathbf{Y})=\mathbf{Y}^{\mathsf{T}}\mathbf{P}\mathbf{Y} \\
&=\mathbf{Y}^{\mathsf{T}}(\mathbf{I}-\mathbf{M})\mathbf{Y}=\mathbf{Y^{\mathsf{T}}}\mathbf{Y}-(\mathbf{M}\mathbf{Y})^{\mathsf{T}}(\mathbf{M}\mathbf{Y}) \\
&=\mathbf{Y}^{\mathsf{T}}\mathbf{Y}-\mathbf{e}^{\mathsf{T}}\mathbf{e}
\end{align}
$$
由此得到平方和分解法则
$$
\mathbf{Y}^{\mathsf{T}}\mathbf{Y}=\hat{\mathbf{Y}}^{\mathsf{T}}\hat{\mathbf{Y}}+\mathbf{e}^{\mathsf{T}}\mathbf{e}
$$
回归方程中心化后应用平方和分解法则可得
$$
\begin{align}
(\mathbf{M}_{0}\mathbf{Y})^{\mathsf{T}}(\mathbf{M}_{0}\mathbf{Y})&=(\mathbf{M}_{0}\hat{\mathbf{Y}})^{\mathsf{T}}(\mathbf{M}_{0}\hat{\mathbf{Y}})+\mathbf{e}^{\mathsf{T}}\mathbf{e} \\
\mathbf{Y}^{\mathsf{T}}\mathbf{M}_{0}\mathbf{Y}&=\hat{\mathbf{Y}}\mathbf{M}_{0}\hat{\mathbf{Y}}+\mathbf{e}^{\mathsf{T}}\mathbf{e} \\
\underbrace{ (\mathbf{Y}-\bar{\mathbf{Y}})^{\mathsf{T}}(\mathbf{Y}-\bar{\mathbf{Y}}) }_{ \text{SST} }&=\underbrace{ (\hat{\mathbf{Y}}-\bar{\mathbf{Y}})^{\mathsf{T}}(\hat{\mathbf{Y}}-\bar{\mathbf{Y}}) }_{ \text{SSE} }+\underbrace{ \mathbf{e}^{\mathsf{T}}\mathbf{e} }_{ \text{SSR} }
\end{align}
$$
定义 uncenterd R-squared 为
$$
R^{2}_{u}=\frac{\hat{\mathbf{Y}}^{\mathsf{T}}\hat{\mathbf{Y}}}{\mathbf{Y}^{\mathsf{T}}\mathbf{Y}}=1-\frac{\mathbf{e}^{\mathsf{T}}\mathbf{e}}{\mathbf{Y}^{\mathsf{T}}\mathbf{Y}}
$$
定义 centered R-squared 为
$$
R^{2}=\frac{\text{SSE}}{\text{SST}}=1-\frac{\text{SSR}}{\text{SST}}
$$
> uncenterd R-quared 可以看作将模型未解释的信息和总信息（即没有模型）比较，而 centered R-squared 是将模型未解释的信息和最简模型（常数项回归）未解释的信息比较。后者更切实际也更常用。

定义 adjust R-squared 为
$$
\bar{R}^{2}=1-\frac{\text{SSR}/n-k}{\text{SST}/n-1}=1-(1-R^{2})\frac{n-1}{n-k}
$$
其中，$\text{SST}$ 的自由度相当于 $\mathbf{Y}$ 的维度减去 $\bar{\mathbf{Y}}$ 占用的一个维度；$\text{SSR}$ 的自由度相当于残差的维度，而残差的维度即在投影过程中失去的维度，恰好等于消去矩阵的迹 $\mathrm{Tr}(\mathbf{M})=n-k$，；类似地，$\text{SSE}$ 的自由度相当于投影到 $span(\mathbf{X})$ 的维度，恰好等于投影矩阵的迹 $\mathrm{Tr}(\mathbf{P})=k$

**Theorem** $R^{2}$ 相当于因变量真值 $Y$ 和拟合值 $\hat{Y}$ 的样本相关系数的平方，即
$$R^{2}=r(Y,\hat{Y})^{2}$$
Proof.
样本相关系数为
$$
r(Y,\hat{Y})=\frac{Cov(Y,\hat{Y})}{\sqrt{ Var(Y)Var(\hat{Y}) }}=\frac{(\mathbf{M}_{0}\mathbf{Y})^{\mathsf{T}}(\mathbf{M}_{0}\hat{\mathbf{Y}})}{\sqrt{ (\mathbf{Y}^{\mathsf{T}}\mathbf{M}_{0}\mathbf{Y})(\hat{\mathbf{Y}}^{\mathsf{T}}\mathbf{M}_{0}\hat{\mathbf{Y}}) }}
$$
其中 $\mathbf{M}_0\mathbf{Y}=\mathbf{M}_{0}(\mathbf{\hat{\mathbf{Y}}+\mathbf{e}})=\mathbf{M_{0}\hat{\mathbf{Y}}}$，因此
$$
r(Y,\hat{Y})^{2}=\frac{(\hat{\mathbf{Y}}^{\mathsf{T}}\mathbf{M}_{0}\hat{\mathbf{Y}})^{2}}{ (\mathbf{Y}^{\mathsf{T}}\mathbf{M}_{0}\mathbf{Y})(\hat{\mathbf{Y}}^{\mathsf{T}}\mathbf{M}_{0}\hat{\mathbf{Y}}) }=\frac{\hat{\mathbf{Y}}^{\mathsf{T}}\mathbf{M}_{0}\hat{\mathbf{Y}}}{ \mathbf{Y}^{\mathsf{T}}\mathbf{M}_{0}\mathbf{Y}}=\frac{\text{SSE}}{\text{SST}}=R^{2}
$$


---

## 附录：no matrix

总离差为
$$
Y_{i}-\bar{Y}=(Y_{i}-\hat{Y}_{i})+(\hat{Y}_{i}-\bar{Y})
$$
总离差平方和为
$$
\sum(Y_{i}-\bar{Y})^2=\sum[\hat{e}_{i}+(\hat{Y}_{i}-\bar{Y})]^{2}=\sum \hat{e}_{i}^{2}+\sum (\hat{Y}_{i}-\bar{Y})^{2}+2\sum \hat{e}_{i}(\hat{Y}_{i}-\bar{Y})
$$
其中
$$
\begin{align}
\sum \hat{e}_{i}(\hat{Y}_{i}-\bar{Y})&=
\sum \hat{e}_{i}\hat{Y}_{i}+\bar{Y}\sum \hat{e}_{i}  \\
&=\sum \hat{e}_{i}(X_{i}^{\mathsf{T}}\beta) \\
&=\beta\sum [\hat{e}_{i}X_{i1},\dots,\hat{e}_{i}X_{ik}] \\
&=0
\end{align}
$$
定义
$$
\begin{align}
\text{SST}&\equiv \sum(Y_{i}-\bar{Y})^{2} \\
\text{SSE}&\equiv \sum(\hat{Y}_{i}-\bar{\hat{Y}_{i}})^{2}=\sum(\hat{Y}_{i}-\bar{Y})^{2} \\
\text{SSR}&\equiv \sum(\hat{e}_{i}-\bar{\hat{e}_{i}})^{2}=\sum \hat{e}_{i}^2 \\ \\
\end{align}
$$
从而有
$$
\text{SST}=\text{SSE}+\text{SSR}
$$

定义
$$
R^{2}\equiv \frac{\text{SSE}}{\text{SST}}=1-\frac{\text{SSR}}{\text{SST}}=\frac{\sum(\hat{Y}_{i}-\bar{Y})^{2}}{\sum (Y_{i}-\bar{Y})^{2}}
$$
可以证明，$R^2$ 等价于 $Y$ 与 $\hat{Y}$ 相关系数的平方
